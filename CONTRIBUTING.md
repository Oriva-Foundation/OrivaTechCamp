# Contributing to Oriva Tech Camp (OTC) 🚀

Thank you for your interest in contributing to Oriva Tech Camp! This project aims to provide a professional, real-world LMS for learners and volunteer educators. We welcome code, docs, design work, mentorship, and sponsorships.

![contribute-badge](https://img.shields.io/badge/contribute-welcome-brightgreen)
![issues](https://img.shields.io/github/issues/ORGANIZATION/REPO)
![prs](https://img.shields.io/github/issues-pr/ORGANIZATION/REPO)

---

## Table of Contents
- Why contribute?
- Ways to contribute
- Getting started (local setup)
- Code standards
- Branching & PR process
- Commit messages
- PR checklist
- Communication & support

---

## Why contribute?
OTC is an open-source learning platform designed to simulate real-world product and engineering workflows. Your contributions help students, volunteer instructors, and sponsors get more value from the project.

## Ways to contribute
- Report bugs or request features via GitHub Issues.
- Submit code or docs improvements via Pull Requests.
- Volunteer as an instructor or reviewer.
- Sponsor or advocate for the project.
- Improve UI/UX, accessibility, or content.

## Getting started (local setup)
Follow these steps to get a working development environment:

1. Fork the repository and clone your fork:

```bash
git clone https://github.com/<your-username>/oriva-tech-camp.git
cd oriva-tech-camp
```

2. Install dependencies:

```bash
npm install
# or
pnpm install
```

3. Copy the environment example and fill in credentials:

```bash
cp .env.example .env.local
```

- Create a Supabase project at https://supabase.com and populate the variables in `.env.local`.

4. Run the development server:

```bash
npm run dev
```

5. Optional: Run the database migrations and seeders (if present):

```bash
# Example (if using supabase migrations or prisma)
# npm run db:migrate
```

## Code standards
We aim for a consistent, modern codebase:
- Language: TypeScript (preferred) for new code.
- Framework: Next.js (App Router) — use server components when possible for data fetching and privacy.
- Styling: Tailwind CSS utility-first approach. Keep styles composable and responsive.
- Linting & Formatting: ESLint + Prettier. Run `npm run lint` and `npm run format` before committing.
- Accessibility: Use semantic HTML, ARIA when needed, and follow WCAG basics.

### File structure conventions
- Keep components small and focused.
- `app/` contains route-driven folders and server components.
- `components/` holds reusable UI primitives.

## Branching & PR process
- Work on feature branches off `main` named like `feat/<short-desc>` or `fix/<short-desc>`.
- Rebase or merge `main` into your branch frequently to avoid drift.
- Open a Pull Request to `main` when your feature is ready.

## Commit message guidelines
Use Conventional Commits to keep history readable. Examples:

- `feat(auth): add Google OAuth provider`
- `fix(tasks): validate submission file type`
- `docs: update CONTRIBUTING.md`

Start with one of: `feat`, `fix`, `chore`, `docs`, `refactor`, `style`, `test`.

## Pull Request checklist
Before requesting review, ensure the following:
- [ ] The PR has a clear title and description.
- [ ] Related issue is linked (if any).
- [ ] The code builds and passes linting.
- [ ] Tests added or updated for new behavior.
- [ ] UI/UX changes include screenshots or a short demo video.
- [ ] No sensitive data in the diff (tokens, keys).

## Running tests
We welcome tests. Run the test suite with:

```bash
npm test
# or
npm run test:watch
```

## Communication & support
- Ask questions in GitHub Discussions or open an issue with the `question` label.
- For escalation or sensitive reports, contact the maintainers at contact@orivatechcamp.org

---

Thanks for helping make OTC accessible and delightful for learners! 🎓✨