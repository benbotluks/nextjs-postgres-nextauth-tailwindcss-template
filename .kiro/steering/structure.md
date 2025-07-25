# Project Structure

## App Router Organization

### Core App Structure
```
app/
├── layout.tsx              # Root layout with Analytics
├── globals.css             # Global Tailwind styles
├── (dashboard)/            # Route group for authenticated pages
│   ├── layout.tsx          # Dashboard layout with navigation
│   ├── page.tsx            # Main products dashboard
│   ├── customers/          # Customer management pages
│   └── [components]        # Dashboard-specific components
├── login/                  # Authentication pages
└── api/                    # API routes
    ├── auth/[...nextauth]/ # NextAuth configuration
    └── seed/               # Database seeding endpoint
```

### Component Architecture
```
components/
├── ui/                     # Shadcn UI components
│   ├── button.tsx
│   ├── table.tsx
│   ├── card.tsx
│   └── [other-ui-components]
└── icons.tsx               # Custom icon components
```

### Library Organization
```
lib/
├── auth.ts                 # NextAuth configuration
├── db.ts                   # Database schema and queries
└── utils.ts                # Utility functions (cn, etc.)
```

## Key Conventions

### File Naming
- Use kebab-case for files and folders
- Component files use `.tsx` extension
- API routes use `route.ts` naming convention
- Page components are named `page.tsx`

### Import Aliases
- `@/components/*` → `components/*`
- `@/lib/*` → `lib/*`
- Configured in `tsconfig.json` paths

### Route Groups
- `(dashboard)` route group for authenticated pages
- Shared layouts without affecting URL structure
- Middleware handles authentication redirects

### Component Patterns
- Server components by default (App Router)
- Client components marked with 'use client'
- Database queries in server components
- Form actions using server actions

### Database Patterns
- Drizzle schema definitions in `lib/db.ts`
- Type inference with `$inferSelect`
- Zod validation schemas from Drizzle
- Server-only imports for database code