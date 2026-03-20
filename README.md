# ToolJet on fly.io for Byrdson Services
ToolJet self-hosted instance hosted on fly.io made especially for Byrdson Services' tech team.

## fly.io Deployment
1. Create a Supabase Postgres database.
2. Comment out `DISABLE_SIGNUPS` on fly.toml.
3. `fly launch --copy-config --no-deploy --org byrdson-services`
4. `git restore fly.toml`
5. On .env repo: `fly secrets import --app tooljet-byrdson < .env`
6. `fly deploy --ha=false`
7. Create an admin account on web UI.
8. Uncomment `DISABLE_SIGNUPS` on fly.toml.
9. Comment out all the `[deploy]` section on fly.toml.
10. `fly deploy`

## Change server configuration
1. `fly deploy`

## .env contents
```
LOCKBOX_MASTER_KEY=
SECRET_KEY_BASE=
DATABASE_URL=
TOOLJET_DB_URL=
PGRST_DB_URI=
PGRST_JWT_SECRET=
```