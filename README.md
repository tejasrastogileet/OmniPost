
<div align="center">

# OmniPost

<img src="https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js 16" />
<img src="https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
<img src="https://img.shields.io/badge/Tailwind_CSS-4.x-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
<img src="https://img.shields.io/badge/tRPC-11-2596BE?style=for-the-badge&logo=trpc&logoColor=white" alt="tRPC" />
<img src="https://img.shields.io/badge/Drizzle-ORM-C5F74F?style=for-the-badge&logo=drizzle&logoColor=black" alt="Drizzle ORM" />
<img src="https://img.shields.io/badge/PostgreSQL-Neon-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />

**AI-Powered Social Media Management & Omnichannel Publishing Platform**

<p align="center">
  Transform a single prompt into tailored, high-converting posts across LinkedIn, Facebook, X, Instagram, Pinterest, and TikTok — complete with automated scheduling, live analytics, and resilient offline-first demo fallbacks.
</p>

<img width="1898" height="1433" alt="landing-page" src="https://github.com/user-attachments/assets/6949dc33-c634-446b-88e0-1e5be1279d8d" />
<img width="2073" height="1440" alt="dashboard-index" src="https://github.com/user-attachments/assets/ae5a6840-783b-4f4e-acdb-45468236f90b" />

[Live Demo](https://github.com/tejasrastogileet/OmniPost) · [Project Repository](https://github.com/tejasrastogileet/OmniPost) · [Report Bug](https://github.com/tejasrastogileet/OmniPost/issues)

</div>

---

## Key Highlights & Architecture

* **End-to-End Type Safety:** Fully typed API boundary using **tRPC v11** and **Zod** schema inference between client components and backend procedures.
* **Resilient Offline / Demo Mode:** Built-in seed data architecture renders full dashboard metrics, calendar events, and media libraries even without active `DATABASE_URL` or third-party API connections.
* **Modern Data Layer:** Database schemas modeled in **Drizzle ORM** with relational queries targeting **PostgreSQL (Neon)**.
* **Enterprise State Hydration:** Synchronized state management utilizing **TanStack Query** for server caching and **Zustand** for client workflows.

---

## Features

### Content Transformation Engine
* **One Input, Six Outputs** — Automatically generates platform-specific copy adjusted for character counts, audience tone, and hashtag density.
* **Platform-Aware Constraints** — Custom formatting boundaries for LinkedIn thought leadership, short-form X threads, and visual captions.
* **AI Image Generation** — Automated visual prompt engineering tailored to platform-specific aspect ratios (1:1, 16:9, 9:16).

### Smart Scheduling & Pipeline
* **Drag-and-Drop Calendar** — Visual scheduling interface managing cross-channel distribution queues.
* **Engagement-Driven Timing** — Algorithmic recommendation for optimal audience activity windows.
* **Batch Pipeline Management** — Stage, edit, and queue posts in bulk across workspace accounts.

### Unified Analytics & Reporting
* **Multi-Channel Telemetry** — Centralized dashboard aggregating impressions, engagement rates, click-throughs, and follower velocity.
* **Content Performance Scoring** — Automated attribution highlighting high-performing creative hooks and themes.

### Workspace & Team Collaboration
* **Role-Based Access Control (RBAC)** — Segmented administrative, creator, and reviewer permissions.
* **Central Brand Kit** — Global repository for typography standards, brand tone, hex palettes, and reusable assets.

---

## Tech Stack

| Layer | Technologies |
| :--- | :--- |
| **Framework** | Next.js 16 (App Router, Server Actions) |
| **Language** | TypeScript 5.x (Strict Mode) |
| **Styling** | Tailwind CSS 4, Radix UI Primitives, Lucide Icons, CVA |
| **API & Validation** | tRPC v11, Zod |
| **Database & ORM** | PostgreSQL (Neon Serverless), Drizzle ORM |
| **Auth & Billing** | Clerk Auth, Stripe Checkout & Webhooks |
| **State & Fetching**| TanStack Query v5, Zustand |
| **AI Integration** | OpenAI GPT-4o, DALL-E 3 |

---

## Getting Started

### Prerequisites

* **Node.js**: `20.x` or later
* **Package Manager**: `pnpm` (v9+)
* **PostgreSQL** *(Optional for Demo Mode)*: Local Postgres or [Neon](https://neon.tech)

---

### Installation & Quick Start

1. **Clone the repository**
   ```bash
   git clone [https://github.com/tejasrastogileet/OmniPost.git](https://github.com/tejasrastogileet/OmniPost.git)
   cd OmniPost

```

2. **Install dependencies**
```bash
pnpm install

```


3. **Environment Configuration**
```bash
cp .env.example .env.local

```


> **Note on Demo Mode:** You can start the app immediately without adding API keys. The application automatically detects missing credentials and gracefully falls back to structured mock data.


4. **Database Migration (Production / Persistence Mode)**
*If connecting to a live database, apply the Drizzle schema:*
```bash
pnpm db:push

```


5. **Run Development Server**
```bash
pnpm dev

```


Open [http://localhost:3000](http://localhost:3000) to view the application.

---

## Project Structure

```text
src/
├── app/
│   ├── (auth)/                 # Authentication views (Clerk integration)
│   ├── (dashboard)/            # Authenticated application shell
│   │   └── dashboard/
│   │       ├── analytics/      # Cross-platform telemetry charts
│   │       ├── calendar/       # Visual scheduling engine
│   │       ├── content/        # Asset & content library
│   │       ├── create/         # Omnichannel creation wizard
│   │       └── settings/       # Workspace & account configuration
│   ├── api/                    # tRPC router HTTP handlers & webhooks
│   ├── layout.tsx              # Root HTML layout & font configurations
│   └── page.tsx                # Marketing landing page
├── components/
│   ├── auth/                   # Identity & session UI
│   ├── content/                # Post cards, preview modals, rich text tools
│   ├── landing/                # Conversion-optimized marketing blocks
│   ├── layout/                 # Sidebar navigation & header bars
│   └── ui/                     # Atomic design primitives (buttons, dialogs)
└── lib/
    ├── ai/                     # OpenAI orchestration & prompt templates
    ├── db/                     # Drizzle PostgreSQL schemas & client instances
    ├── seed-data.ts            # High-fidelity mock datasets for offline evaluation
    ├── stripe/                 # Subscription & payment verification handlers
    └── trpc/                   # Routers, procedures, and context setup

```

---

## Available Scripts

| Command | Action |
| --- | --- |
| `pnpm dev` | Starts Next.js development server with Turbopack |
| `pnpm build` | Compiles optimized production bundle |
| `pnpm start` | Runs built production server |
| `pnpm type-check` | Executes TypeScript type checking across workspace |
| `pnpm lint` | Runs ESLint analysis |
| `pnpm format` | Formats codebase using Prettier |
| `pnpm db:push` | Pushes Drizzle schemas directly to PostgreSQL database |
| `pnpm db:studio` | Launches interactive local Drizzle Studio GUI |

---

## Platform Support & Target Dimensions

| Platform | Character Ceiling | Feed Aspect Ratio | Stories/Vertical Video |
| --- | --- | --- | --- |
| **LinkedIn** | 3,000 | 1200 × 627 (1.91:1) | 1080 × 1920 (9:16) |
| **Facebook** | 63,206 | 1200 × 630 (1.91:1) | 1080 × 1920 (9:16) |
| **Twitter / X** | 280 | 1600 × 900 (16:9) | 1080 × 1920 (9:16) |
| **Instagram** | 2,200 | 1080 × 1080 (1:1) | 1080 × 1920 (9:16) |
| **Pinterest** | 500 | 1000 × 1500 (2:3) | 1080 × 1920 (9:16) |
| **TikTok** | 2,200 | 1080 × 1080 (1:1) | 1080 × 1920 (9:16) |

---

## License

Distributed under the MIT License. See [`LICENSE`](https://www.google.com/search?q=LICENSE) for more details.

---

## Developed By

### **Tejas Rastogi**

**OmniPost · Engineered with Next.js, tRPC, Drizzle ORM, and OpenAI · © 2026**


