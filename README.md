# yatty.ca

Source for [yatty.ca](https://yatty.ca), the personal site of Yatharth Choudhary.

| Path | What it is |
| --- | --- |
| `/` | Landing page |
| `/resume/` | Resume and selected work |
| `/homelab-docs/` | Homelab write-ups (coming soon) |

## How it's built

Plain static HTML in `site/`, with no build step. Every push to `main` runs
[`deploy.yml`](.github/workflows/deploy.yml), which:

1. validates the HTML with `html-validate`
2. checks links with `lychee`
3. publishes `site/` to GitHub Pages

Pull requests run the checks without deploying.

## Hosting and DNS

GitHub Pages serves the apex domain. DNS lives at Spaceship:

| Type | Host | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | yatharth121.github.io |

Self-hosted services stay on their own subdomains and are not affected by this site.

## Adding a section

Create `site/<section>/index.html` and link it from `site/index.html`.
