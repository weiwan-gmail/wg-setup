# Openimg image host (FlexDCA audits / ScopeTask)

Large audit images (contact sheets, pairs) are hosted on **Openimg**, not in Git.

| Item | Value |
|------|-------|
| Site | https://openimg.io |
| Docs | https://openimg.io/docs |
| CDN base | `https://files.openimgcdn.com/…` |
| Upload | `POST /api/upload` with `Authorization: Bearer <token>` |
| Token | Grok Bot **Vault** entry **`openimg.io`** — never commit secrets |
| Link rot | Acceptable; repos keep markdown + small texts only |

## Image workflow (Tom’s rules)

1. **Never commit compare/audit images.** Keep them in a **gitignored** temp dir (e.g. `audit-images/`).
2. Upload that dir’s images to **Openimg**.
3. Put **CDN links only** in markdown (no binary blobs in Git).
4. **Never commit** secrets, tokens, or WireGuard private keys.

Example `.gitignore` fragment:

```gitignore
# Local audit images — upload to Openimg; link CDN URLs in markdown only
audit-images/
```

## Canonical docs

- GitLab `agent/scopetask` → **`WORKFLOW.md`** (Openimg section)
- Sample CDN URLs: `docs/audits/r22/audit.md`

## Live FlexDCA capture

When Tom opens sims: **flapy** / FlaUI at `http://192.168.4.2:8730` — details in scopetask `WORKFLOW.md`.
