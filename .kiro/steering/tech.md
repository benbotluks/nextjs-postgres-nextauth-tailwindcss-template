# Technology Stack

## Core Framework
- **Next.js 15** with App Router (React 19)
- **TypeScript** for type safety
- **Tailwind CSS** for styling
- **Shadcn UI** component library

## Database & ORM
- **PostgreSQL** (Neon serverless)
- **Drizzle ORM** with Zod validation
- Database schema uses enums and proper typing

## Authentication
- **Auth.js (NextAuth v5 beta)** 
- GitHub OAuth provider configured
- Server-side session handling

## Development Tools
- **pnpm** as package manager
- **Prettier** for code formatting with specific config:
  - Single quotes
  - 2-space tabs
  - No trailing commas
  - Arrow parens always
- **Turbopack** for faster development builds

## Key Libraries
- **Radix UI** primitives for accessible components
- **Lucide React** for icons
- **Class Variance Authority** for component variants
- **Vercel Analytics** for usage tracking

## Common Commands

### Development
```bash
pnpm install          # Install dependencies
pnpm dev              # Start dev server with Turbopack
pnpm build            # Build for production
pnpm start            # Start production server
```

### Database Setup
```bash
# After Vercel Postgres setup
vercel link
vercel env pull
# Hit /api/seed endpoint to populate database
```

## Environment Setup
- Copy `.env.example` to `.env`
- Configure GitHub OAuth application
- Set up Vercel Postgres database connection