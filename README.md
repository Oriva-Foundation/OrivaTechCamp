# 🚀 Oriva Tech Camp (OTC)

**The Open-Source Learning Management System for Real-World Tech Education**

![OTC-banner](https://img.shields.io/badge/Oriva%20Tech%20Camp-v1.0.0-blue?style=for-the-badge&logo=nextdotjs&logoColor=white)
![license](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![contributions](https://img.shields.io/badge/Contributions-Welcome-brightgreen?style=for-the-badge)
![status](https://img.shields.io/badge/Status-Active%20Development-yellow?style=for-the-badge)

---

## 📚 What is Oriva Tech Camp?

Oriva Tech Camp (OTC) is a **full-stack, open-source Learning Management System** designed to simulate real-world tech industry workflows. We host a 3-month intensive bootcamp with specialized tracks in:

- 🎨 **Frontend Development** — React, Next.js, Tailwind CSS
- ⚙️ **Backend Engineering** — Node.js, APIs, Databases
- 🧪 **Software Testing** — QA automation, test strategies
- 🎬 **Video Editing** — Production & post-production skills

**Our Mission:** Prepare learners for the job market with hands-on experience, real instructor feedback, gamification, and peer collaboration.

---

## ✨ Key Features

| Feature | Description | Impact |
|---------|-------------|--------|
| 👥 **Role-Based Dashboards** | Customized views for Students, Instructors, and Admins | Personalized workflows for each user |
| 🎯 **Live Sessions** | Real-time classes with countdown timers & automated attendance | Engagement & attendance tracking |
| 🏆 **Gamification** | Points system, leaderboards, and achievement badges | Motivates learners to excel |
| 📝 **Task Portal** | GitHub link submissions + file uploads with instructor review | Collaborative learning |
| 📊 **Analytics & Progress** | Real-time progress tracking and performance insights | Data-driven learning paths |
| 💬 **Peer Feedback** | Community discussions and instructor-led reviews | Supportive learning environment |

---

## 🛠️ Tech Stack

```
┌─────────────────────────────────────────┐
│         🌐 Frontend (Next.js 14+)       │
│   ✨ React | Tailwind CSS | TypeScript  │
└────────────┬────────────────────────────┘
             │
             ↓
┌─────────────────────────────────────────┐
│      🔐 Authentication & Backend        │
│        Supabase (PostgreSQL)            │
│    Auth | Realtime | Storage | Edge Fn │
└────────────┬────────────────────────────┘
             │
             ↓
┌─────────────────────────────────────────┐
│    ☁️ Deployment (Vercel + Supabase)    │
│  Edge Functions | CDN | Auto-scaling    │
└─────────────────────────────────────────┘
```

### Tech Stack Details

- **Framework:** [Next.js](https://nextjs.org) (App Router)
- **Styling:** [Tailwind CSS](https://tailwindcss.com) — utility-first, responsive design
- **Language:** TypeScript for type safety
- **Backend:** [Supabase](https://supabase.com) — PostgreSQL, Auth, Realtime, Storage
- **Deployment:** [Vercel](https://vercel.com) for serverless hosting & edge computing

---

## 🚀 Quick Start

### Prerequisites

Ensure you have the following installed:
- [Node.js](https://nodejs.org) 18.x or higher
- [npm](https://www.npmjs.com) or [pnpm](https://pnpm.io)
- A [Supabase](https://supabase.com) account

### Installation

1. **Clone the repository:**

```bash
git clone https://github.com/your-org/oriva-tech-camp.git
cd oriva-tech-camp
```

2. **Install dependencies:**

```bash
npm install
# or
pnpm install
```

3. **Set up environment variables:**

```bash
cp .env.example .env.local
```

Then fill in your Supabase credentials from [supabase.com](https://supabase.com).

4. **Start the development server:**

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser. 🎉

---

## 📂 Project Structure

```
oriva-tech-camp/
├── app/                      # Next.js App Router
│   ├── dashboard/           # Role-based dashboard routes
│   ├── sessions/            # Live session management
│   ├── tasks/               # Task portal
│   ├── leaderboard/         # Gamification leaderboard
│   └── layout.tsx           # Root layout
│
├── components/              # Reusable React components
│   ├── ui/                  # Base UI primitives
│   ├── dashboard/           # Dashboard-specific components
│   └── common/              # Shared components
│
├── lib/                     # Utility functions & configs
│   ├── supabase/           # Supabase clients & helpers
│   ├── auth.ts             # Authentication logic
│   └── hooks/              # Custom React hooks
│
├── public/                  # Static assets
│
├── docs/                    # Project documentation
│   └── ARCHITECTURE.md      # System architecture
│
├── .env.example             # Environment variables template
├── next.config.ts           # Next.js configuration
├── tsconfig.json            # TypeScript configuration
└── tailwind.config.ts       # Tailwind CSS configuration
```

---

## 🎯 User Roles & Features

### 👨‍🎓 Student
- View personalized dashboard with progress tracking
- Join live sessions with real-time attendance
- Submit tasks (GitHub links, files, or text)
- Track points and compete on leaderboards
- Access instructor feedback and peer discussions

### 👨‍🏫 Instructor
- Create and schedule live sessions
- Design and post tasks for students
- Review submissions with inline feedback
- Award points and manage leaderboards
- Monitor classroom attendance and engagement

### 👨‍💼 Admin
- Manage users (students, instructors, admins)
- Configure course tracks and session schedules
- View system analytics and reports
- Manage platform settings and integrations
- Monitor platform health and performance

---

## 🔐 Architecture Overview

Our system follows a **client-server architecture** with strong separation of concerns:

```
Client (Browser)
      ↓
   Next.js (App Router)
   ├─ Server Components (SSR)
   ├─ Client Components (Interactivity)
   └─ API Routes (Server Actions)
      ↓
   Supabase Backend
   ├─ PostgreSQL Database
   ├─ Auth & RLS (Row-Level Security)
   ├─ Realtime Subscriptions
   ├─ File Storage
   └─ Edge Functions
```

**Key Principles:**
- ✅ Server components for data fetching (privacy & performance)
- ✅ Client components for interactivity (UI state)
- ✅ RLS policies for database-level security
- ✅ Realtime subscriptions for live updates

For more details, see [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

---

## 📖 Getting Help

### Documentation
- [Contributing Guide](CONTRIBUTING.md) — How to contribute code & docs
- [Architecture Overview](docs/ARCHITECTURE.md) — System design & database schema
- [Code of Conduct](CODE_OF_CONDUCT.md) — Community standards

### Support
- 💬 [GitHub Discussions](https://github.com/your-org/oriva-tech-camp/discussions) — Ask questions
- 🐛 [GitHub Issues](https://github.com/your-org/oriva-tech-camp/issues) — Report bugs
- 📧 **Email:** contact@orivatechcamp.org

---

## 🤝 Contributing

We ❤️ contributions! Whether you're fixing bugs, adding features, or improving docs, your help matters.

### Ways to Contribute

1. **Code & Features** — Submit PRs for new features or bug fixes
2. **Documentation** — Improve guides, examples, and architecture docs
3. **Design & UX** — Enhance UI/UX and accessibility
4. **Testing** — Write tests and improve coverage
5. **Volunteer** — Become an instructor or community mentor
6. **Sponsorship** — Support the project financially

### Quick Start for Contributors

```bash
# 1. Fork and clone
git clone https://github.com/<your-username>/oriva-tech-camp.git
cd oriva-tech-camp

# 2. Create a feature branch
git checkout -b feat/your-feature-name

# 3. Install & develop
npm install
npm run dev

# 4. Commit with conventional messages
git commit -m "feat(dashboard): add student progress widget"

# 5. Push and open a PR
git push origin feat/your-feature-name
```

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

## 🗺️ Roadmap

### Current Version (v1.0)
- ✅ Role-based dashboards (Student, Instructor, Admin)
- ✅ Live session scheduling & attendance
- ✅ Task submission & feedback system
- ✅ Points & leaderboard system

### Planned (v1.1 - v2.0)
- 🔄 Mobile app (React Native)
- 🔄 AI-powered assistant for code review
- 🔄 Advanced analytics & performance insights
- 🔄 Community forum & knowledge base
- 🔄 Integrations (Slack, Discord, Gmail)
- 🔄 Certification program

---

## 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/your-org/oriva-tech-camp?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/your-org/oriva-tech-camp?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/your-org/oriva-tech-camp?style=flat-square)
![GitHub PRs](https://img.shields.io/github/issues-pr/your-org/oriva-tech-camp?style=flat-square)

---

## 💖 Supporters & Sponsors

OTC is made possible by the contributions of our amazing community and sponsors.

### 🌟 Core Contributors
- [Add your name here!](CONTRIBUTING.md)

### 💰 Sponsors
- Looking for sponsors to support open-source education

If you'd like to sponsor OTC, please reach out to [sponsors@orivatechcamp.org](mailto:sponsors@orivatechcamp.org).

---

## 📜 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

### Summary
✅ Free to use, modify, and distribute  
✅ Commercial use permitted  
✅ Attribution required  
✅ Patent indemnification  

---

## 🔗 Useful Links

| Resource | Link |
|----------|------|
| 📖 Docs | [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) |
| 🤝 Contributing | [CONTRIBUTING.md](CONTRIBUTING.md) |
| 📋 Code of Conduct | [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) |
| 🐛 Report a Bug | [GitHub Issues](https://github.com/your-org/oriva-tech-camp/issues/new?template=bug_report.md) |
| 💡 Request a Feature | [GitHub Issues](https://github.com/your-org/oriva-tech-camp/issues/new?template=feature_request.md) |
| 💬 Discussions | [GitHub Discussions](https://github.com/your-org/oriva-tech-camp/discussions) |

---

## 🌟 Show Your Support

If you find OTC helpful, please consider:

- ⭐ **Star this repository** on GitHub
- 🐦 **Share** on social media ([Twitter](https://twitter.com), LinkedIn)
- 📢 **Tell a friend** about the project
- 💬 **Join discussions** and help the community
- 🤝 **Contribute** code, docs, or ideas

---

<div align="center">

**Made with ❤️ by the Oriva Tech Camp Community**

© 2026 Oriva Tech Camp. All rights reserved.

[**🚀 Get Started Now**](#-quick-start) • [**📖 Read the Docs**](docs/ARCHITECTURE.md) • [**🤝 Contribute**](CONTRIBUTING.md)

</div>
