# resume

My resume, a single static `index.html` page.

**Live:** https://resume.sujitkuswain.workers.dev

## Hosting

Hosted on **Cloudflare Workers (static assets)**, connected to this GitHub repo through Workers Builds.

- No build step: the repo root is served as-is.
- HTTPS and global CDN included.
- Cost: free tier (static asset requests are free and unlimited, no idle charges).

## Deployments

| Branch | What happens | URL |
|---|---|---|
| `main` | Production deploy (`npx wrangler deploy`) | https://resume.sujitkuswain.workers.dev |
| any other branch | Preview deploy (`npx wrangler preview`) | `https://<branch>-resume.sujitkuswain.workers.dev` |

Example: pushing branch `add-skills` produced https://add-skills-resume.sujitkuswain.workers.dev.

Build status shows as the **Workers Builds: resume** check on each commit in GitHub.

## Config files

- `wrangler.jsonc`: Worker name, static assets directory (`.`), and the `previews` block that `wrangler preview` requires.
- `.assetsignore`: files not published to the site (`.git`, `README.md`, config files).

## Workflow

1. Create a branch and edit `index.html`.
2. Push the branch and check the preview URL.
3. Merge to `main` to go live.

Cloudflare dashboard: Workers & Pages → `resume` (Settings → Builds for build and branch settings).
