# Our Library

A shared book library for two, with Open Library search and covers, a wooden bookcase view, and a wishlist.

- **Frontend:** a single `index.html` (no build step), using supabase-js from a CDN.
- **Database and sign-in:** Supabase project `our-library` (ref `chlbxeuffwgwtzondpam`). Tables are `books` and `members`, an email allowlist; row-level security only lets members read and write. Cover photos go to the public `covers` storage bucket.
- **Book data:** [Open Library](https://openlibrary.org) search, ISBN lookup and cover images.
- **Hosting:** Netlify project `our-library-shelf` (https://our-library-shelf.netlify.app), which publishes the repo root.

## Add someone to the library

Run this in the Supabase SQL editor:

```sql
insert into public.members (email) values ('their@email.com');
```

## Supabase Auth settings

Under Authentication → URL Configuration:
- Site URL: `https://our-library-shelf.netlify.app`
- Redirect URLs: `https://our-library-shelf.netlify.app/**`
