# MemorySprout Legal Documents

Source of truth for Privacy Policy and Terms of Use.

**Developer:** ManLin Zhao  
**Public hosting:** Option B — separate public repo `memorysprout-legal` (app source stays private).

## Public URLs

Each document is **one bilingual page**. English | 中文 is a language toggle (not four separate nav items).

| Doc | URL |
|---|---|
| Privacy Policy | https://kinwah-leong.github.io/memorysprout-legal/legal/privacy.html |
| Terms of Use | https://kinwah-leong.github.io/memorysprout-legal/legal/terms.html |
| Privacy (中文) | https://kinwah-leong.github.io/memorysprout-legal/legal/privacy.html?lang=zh-Hans |
| Terms (中文) | https://kinwah-leong.github.io/memorysprout-legal/legal/terms.html?lang=zh-Hans |

Legacy per-locale paths (`privacy-en.html`, …) redirect to the bilingual pages.

App Release uses:

```text
MEMORYSPROUT_LEGAL_BASE_URL = https://kinwah-leong.github.io/memorysprout-legal
```

and loads `$BASE/legal/privacy.html?embed=1&lang=…` or `terms.html?embed=1&lang=…`.

### App embed lock

With `?embed=1` (also injected by the iOS WKWebView):

- Language toggle stays available
- Cross-document links (other policy, legal index) are hidden
- WKWebView cancels navigation away from the opened document

## One-time setup

Local tree is prepared at `/Users/aimo/memorysprout-legal` (synced from `web/legal/`).

```bash
# GitHub → memorysprout-legal → Settings → Pages
# Source: Deploy from a branch → main → / (root) → Save
```

## Update legal content later

From the private MemorySprout repo:

```bash
python3 scripts/generate-legal-html.py
./scripts/sync-legal-public-repo.sh /Users/aimo/memorysprout-legal
cd /Users/aimo/memorysprout-legal && git add -A && git commit -m "Update legal" && git push
```

## Markdown (private MemorySprout)

| Document | English | 简体中文 |
|---|---|---|
| Privacy Policy | `privacy-policy-en.md` | `privacy-policy-zh-Hans.md` |
| Terms of Use | `terms-of-use-en.md` | `terms-of-use-zh-Hans.md` |

Also under `ios/MemorySprout/Legal/*.md` / `*.html` for test builds.

## App loading rule

| Channel | Source |
|---|---|
| Development / Alpha / Beta | Bundled HTML in the app |
| Release | Remote URL only (no local fallback) |

## Still to complete

- Confirm Pages returns HTTP 200 for `privacy.html` / `terms.html`
- Custom domain / monitored emails when ready
- Correspondence address, governing law
