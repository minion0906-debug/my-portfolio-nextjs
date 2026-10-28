# My Portfolio — Next.js 16 + TypeScript

A modern portfolio and personal brand website built with Next.js, TypeScript, Tailwind CSS, Prisma, and PostgreSQL. It includes a polished marketing homepage, project showcases, case study pages, admin dashboard, and an AI-powered portfolio assistant.

## Overview

This project is designed to serve as a professional portfolio platform for showcasing:

- work experience and skills
- featured projects and case studies
- AI-assisted portfolio interaction
- admin-managed content updates
- production-ready deployment configuration

## Tech Stack

- Next.js 16
- React 19
- TypeScript
- Tailwind CSS
- Prisma ORM
- PostgreSQL / Neon
- NextAuth / Auth.js
- Docker support

## Features

- Responsive portfolio landing page
- Premium hero section and product-style presentation
- Project showcase pages and case study detail views
- Light and dark mode support
- Admin authentication and content management
- Skills, projects, profile, and experience management
- AI portfolio assistant with chat experience
- PostgreSQL-backed data layer
- Deployment-ready Docker configuration

## Project Structure

```text
.
├── app/                  # App router pages and API routes
├── components/           # Reusable UI components
├── lib/                  # Shared utilities and helpers
├── prisma/               # Prisma schema and seed data
├── public/               # Static assets
├── scripts/              # Utility scripts
├── .env.example          # Environment variable template
├── Dockerfile            # Docker image definition
├── docker-compose.yml    # Local container setup
├── DEPLOYMENT.md         # Deployment notes
├── package.json          # Scripts and dependency configuration
├── next.config.ts        # Next.js configuration
├── tsconfig.json         # TypeScript config
└── README.md             # Project documentation
```

## Prerequisites

Before you begin, make sure you have:

- Node.js 20+
- npm 10+
- A PostgreSQL-compatible database (local or hosted, such as Neon, Supabase, Railway, or a managed Postgres service)
- A valid AI provider key if you want the chatbot enabled

## Quick Start

### 1) Install dependencies

```bash
npm install
```

### 2) Configure environment variables

Copy the example environment file and update it with your own values:

```bash
cp .env.example .env
```

At minimum, set:

```env
DATABASE_URL="postgresql://user:password@host:5432/database?sslmode=require"
DIRECT_URL="postgresql://user:password@host:5432/database?sslmode=require"
AUTH_SECRET="your-long-random-secret"
ADMIN_EMAIL="admin@portfolio.dev"
ADMIN_PASSWORD="change-this-password"
OPENROUTER_API_KEY="your-api-key"
OPENROUTER_MODEL="openrouter/free"
NEXT_PUBLIC_SITE_URL="http://localhost:3000"
```

Important:

- Do not commit `.env` to version control
- Use secure values in production
- Keep secrets in your hosting provider's secret manager whenever possible

### 3) Generate Prisma client and initialize the database

```bash
npm run db:generate
npm run db:push
```

If you want the seeded portfolio data:

```bash
npm run db:seed
```

Or run the combined setup:

```bash
npm run db:setup
```

### 4) Start the development server

```bash
npm run dev
```

Then open:

```text
http://localhost:3000
```

## Build for Production

To validate the app before deployment:

```bash
npm run typecheck
npm run build
```

Then run the production server:

```bash
npm run start
```

If you want to inspect the app with a production build locally, use:

```bash
npm run build
npm run start
```

## Admin Access

Once the application is running, access the admin dashboard at:

```text
/admin/login
```

Use the credentials from your `.env` file:

- `ADMIN_EMAIL`
- `ADMIN_PASSWORD`

## Deployment

### Option 1: Vercel + Neon

This project is well suited for a modern deployment flow with:

- Vercel for the Next.js app
- Neon or another managed PostgreSQL service for the database

Recommended steps:

1. Push the repository to GitHub
2. Import the project into Vercel
3. Add all required environment variables in the Vercel dashboard
4. Connect a PostgreSQL database and set `DATABASE_URL` and `DIRECT_URL`
5. Set `AUTH_SECRET`, `ADMIN_PASSWORD`, and `OPENROUTER_API_KEY`
6. Deploy the project

### Option 2: Docker

A Docker setup is included for containerized deployment.

Build and run locally:

```bash
docker compose up --build -d
```

For production hosting, deploy the same container to a VPS, Docker-capable host, or a cloud runtime that supports persistent storage.

### Option 3: Render / Railway / VPS

The app can also be deployed to managed hosting providers that support:

- Node.js app runtime
- PostgreSQL database
- environment variables / secrets
- persistent filesystem if needed

Before production launch:

- rotate `AUTH_SECRET`
- update admin credentials
- configure real site URLs
- confirm AI API keys are valid
- verify the health endpoint and admin login flow

## Health Check

The project includes a health check endpoint for deployment verification.

```text
/api/health
```

## Useful Commands

```bash
npm run dev
npm run build
npm run start
npm run lint
npm run typecheck
npm run db:generate
npm run db:push
npm run db:seed
npm run db:setup
npm run db:studio
```

## Notes

- This portfolio is built as a production-ready personal platform rather than a generic template.
- The app is optimized for easy customization of personal brand content, portfolio items, and admin-managed sections.
- Use environment variables and secret storage for all production credentials.

## License

This project is private and intended for personal portfolio use unless otherwise specified.

A
A
A
A
A
A
A
A
A
A
A