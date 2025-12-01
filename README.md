
# Neon + Cloudflare Hyperdrive demo

Note that Hyperdrive appears to work for `wrangler deploy` but only the remote type of `wrangler dev`.

```bash
cd neon-hyperdrive
npm install

# you'll need to redo this bit for your DB, then copy the new binding id into wrangler.toml

wrangler hyperdrive create neon-eu-central-1 --connection-string="postgres://user:password@ep-long-grass-595339.eu-central-1.aws.neon.tech:5432/main?sslmode=verify-full"

# 🚧 Creating 'neon-eu-central-1'
# ✅ Created new Hyperdrive config
#  {
#   "id": "e00ae1df7f614dd9858c1b3361011352",
#   "name": "neon-eu-central-1",
#   "origin": {
#     "host": "ep-long-grass-595339.eu-central-1.aws.neon.tech",
#     "port": 5432,
#     "database": "main",
#     "user": "user"
#   },
#   "caching": {
#     "disabled": false
#   }
# }

code src/index.ts
npx wrangler deploy
```
