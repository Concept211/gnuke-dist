# gnuke-dist

Auto-update channel for [Gnuke](https://github.com/Concept211/Gnuke) (private source).

This repo holds only built artifacts, published as assets on the **latest** release:
- `gnuke.crx` — the signed extension
- `updates.xml` — the manifest Chrome polls

Chrome fetches these unauthenticated, which is why they live here and not in the
private source repo. The `.crx` is useless without the owner's Google sign-in.

Install / policy setup: see `_md/install.md` in the source repo.
