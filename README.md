# LinkAce (LazyCat LPK)

Self-hosted bookmark archive with tags, lists, full-text search and link checks.

- Upstream: https://github.com/Kovah/LinkAce (branch 2.x)
- Image: `linkace/linkace:v2.6.3` (mirror mode, digest-matched)
- License: GPL-3.0 (full text in `content/licenses/LICENSE.md`)
- Containers: app + MariaDB 12 + Meilisearch v1.16 + Redis 8.2

## Notes

- Upstream compose mounts `./.env:/app/.env`; this package instead injects the same
  values as plain environment variables, which Laravel reads natively. No .env is written
  inside the container, so there is no write-permission problem.
- No seeded account: the first admin is created by LinkAce's web setup wizard.
- DB password, Redis password, Meilisearch key and APP_KEY all come from platform stable secrets.
- No mail service configured (invites / password reset by email unavailable).
- Not yet verified on a real device.
