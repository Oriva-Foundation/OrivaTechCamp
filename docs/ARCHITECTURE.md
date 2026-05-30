# Architecture — Oriva Tech Camp (OTC)

This document provides a high-level overview of the OTC architecture, how the Next.js App Router communicates with Supabase, and the key data models used in the system.

## System Overview

- Frontend: Next.js (App Router) using Server & Client components.
- Styling: Tailwind CSS for utility-first, responsive UI.
- Backend (BaaS): Supabase providing Postgres DB, Auth, Realtime, Storage, and Functions.
- Deployment: Vercel for static and server rendering.

## How Next.js and Supabase interact

- Server-side rendering and server components fetch private data on the server using Supabase service keys (kept out of client bundles).
- Client components use `@supabase/supabase-js` with `NEXT_PUBLIC_SUPABASE_ANON_KEY` for realtime features (presence, subscriptions) and user-driven actions.
- Secure operations (e.g., administrative updates, leaderboard point grants) are executed via server actions or API routes that authenticate using the Supabase service role key.

Example patterns:

1. Server Component data fetch (SSR):

```ts
// app/dashboard/page.tsx (server component)
import { createServerSupabase } from '../lib/supabase-server';
export default async function Dashboard() {
  const supabase = createServerSupabase();
  const { data } = await supabase.from('tasks').select('*');
  return <DashboardShell tasks={data} />;
}
```

2. Client Component with realtime (attendance / countdown):

```ts
// components/LiveSession.tsx (client)
import { createClientComponentClient } from '@supabase/auth-helpers-nextjs'
const supabase = createClientComponentClient();
useEffect(() => {
  const sub = supabase
    .channel('public:live_sessions')
    .on('postgres_changes', { event: '*', schema: 'public', table: 'sessions' }, payload => {
      // update local state
    })
    .subscribe();
  return () => { supabase.removeChannel(sub); }
}, []);
```

## Key Conceptual Database Models

Note: This is a conceptual schema for maintainers and contributors.

- `users` / `profiles` (auth + profile):
  - `id` (uuid) — primary key
  - `email`, `full_name`, `avatar_url`
  - `role` — enum: `student`, `instructor`, `admin`

- `sessions` (live classes / events):
  - `id`, `title`, `starts_at`, `ends_at`, `instructor_id`
  - `conference_link`, `recording_url`, `capacity`
  - `status` — enum: `scheduled`, `live`, `ended`, `cancelled`

- `tasks` (assignments):
  - `id`, `title`, `description`, `due_at`, `points`
  - `created_by` (instructor id), `track` (frontend/backend/testing/video)

- `submissions` (student work):
  - `id`, `task_id`, `student_id`, `submitted_at`
  - `type` — `github_link` | `file` | `text`
  - `artifact_url` (storage or external link), `grade`, `feedback`

- `points` / `leaderboard`:
  - Aggregated from task grades, attendance, quizzes.
  - `user_id`, `total_points`, `level` (calculated)

## Auth and Roles

- Supabase Auth manages sign-up and login. After sign-up, a `profiles` row is created to store role and metadata.
- Role-based access is enforced in server code and via RLS (Row-Level Security) policies where appropriate.

## Realtime & Attendance

- Realtime subscriptions (Supabase Realtime) track session state and attendance presence.
- When a session goes `live`, server-side logic can record attendees automatically by checking active connections or via a short-lived token flow.

## Storage & File Uploads

- Student upload artifacts (videos, ZIPs, images) are stored in Supabase Storage buckets with per-file ACLs and signed URLs for downloads.

## Automation & Server Functions

- Use Supabase Edge Functions or Next.js server actions to handle scheduled jobs (e.g., post-session attendance processing, nightly leaderboard recalculation).

## Observability & Deploy

- Deploy to Vercel. Keep service role keys out of client bundles and use environment variables in the Vercel dashboard.
- Add logging and error reporting (Sentry or similar) for production monitoring.

## Further reading
- Supabase Docs: https://supabase.com/docs
- Next.js App Router: https://nextjs.org/docs/app
