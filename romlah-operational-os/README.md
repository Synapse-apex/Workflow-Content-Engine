# Romlah Operational OS

An operational dashboard foundation based on the supplied Romlah Data Flow concept. Next.js 16 + TypeScript + Supabase + Vercel.

> This is an MVP scaffold, not a connected production system. Demo KPI values are illustrative. Imported rows are staged for review only and are not promoted into canonical business tables.

## Included
- Overview, Daily, Weekly, Monthly, Data Center, Products & Inventory, Team, and Settings views.
- Responsive dashboard UI.
- CSV/XLS/XLSX preview with 5 MB / 5,000 row cap and duplicate detection.
- Supabase Auth foundation, PostgreSQL schema, role-based RLS policies, and raw import staging endpoint.
- Claude Code instructions and local `romlah-ops-build` skill.

## Local development
Requires Node.js 22.13+.

```bash
npm install
cp .env.example .env.local
npm run dev
```

Without Supabase environment variables the app runs in demo mode. Imports can be previewed but are not persisted.

## Supabase setup
1. Create a Supabase project.
2. Set `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY` in `.env.local`.
3. Apply `supabase/migrations/0001_initial.sql`.
4. Create the first Auth user and explicitly set the intended owner profile role.

Never put a service-role key in `NEXT_PUBLIC_*` or client code.

## Deploy
Import this folder as the Vercel project root, use the Next.js framework preset and Node.js 22. Add the two Supabase public environment variables only after creating the Supabase project. Deploy a Preview first and verify auth, RLS, import and data integrity before Production.

## Key docs
- `docs/ROMlah_PRODUCT_SPEC.md`
- `docs/IMPLEMENTATION_STATUS.md`
- `docs/DEPLOY_TO_VERCEL.md`
- `docs/CLAUDE_SKILLS.md`
- `CLAUDE.md`

See `Romlah Data Flow.html` for the original concept source.
