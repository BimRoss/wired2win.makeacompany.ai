# wired2win.makeacompany.ai

Pitch mockup for **Wired2Win Golf** — youth golf development site at https://wired2win.makeacompany.ai.

A lightweight static one-pager (no framework, no build step) framing a youth-first rebuild of [wired2wingolf.com](https://wired2wingolf.com/): continuous assessment, the player–coach–parent loop, two age-tiered programs, four development pillars.

## Stack

- `index.html` — the page (vanilla HTML/CSS, Google Fonts: Inter + Fraunces).
- `Dockerfile` — `nginx:1.27-alpine` + the file.
- `.github/workflows/build.yml` — builds + pushes `geeemoney/wired2win:<version>` to Docker Hub on tag.
- Cluster manifests live in [`BimRoss/rancher-admin`](https://github.com/BimRoss/rancher-admin) under `admin/apps/wired2win/`.

## Releasing

```sh
git tag -a v0.1.0 -m "v0.1.0"
git push origin v0.1.0
```

Tag push builds the image and auto-opens a gitops PR against `rancher-admin` to bump `admin/apps/wired2win/deployment.yaml`.
