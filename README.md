# blog-hugo

[中文](README.zh-TW.md)

Personal blog for Tony Xu, built with Hugo and the Blowfish theme. Supports multilingual content in Traditional Chinese, English, and Japanese.

## Tech Stack

| Component | Version | Description |
|-----------|---------|-------------|
| [Hugo](https://gohugo.io/) | Extended 0.147.6+ | Static site generator |
| [Blowfish](https://blowfish.page/) | v2.98.0 | Hugo theme (Git submodule) |
| [GitHub Pages](https://pages.github.com/) | - | Hosting |
| [GitHub Actions](https://github.com/features/actions) | - | CI/CD |

## Project Structure

```
.
├── config/_default/      # Site configuration (Hugo, params, languages, menus)
├── content/
│   ├── zh-tw/            # Traditional Chinese (default)
│   ├── en/               # English
│   └── ja/               # Japanese
├── assets/               # Images and custom CSS
├── static/               # Favicon and static files
└── themes/blowfish/      # Blowfish theme (submodule)
```

## Getting Started

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) v0.147.6+
- Git

### Local Development

```bash
# Clone with submodules
git clone --recurse-submodules <repo-url>

# Start dev server
hugo server --buildDrafts
```

The site will be available at `http://localhost:1313/`.

### Create a New Post

```bash
hugo new content/zh-tw/tech/my-post/index.md
```

## Deployment

The site is automatically deployed to GitHub Pages via GitHub Actions.

**Trigger:** Push to the `main` branch or manual dispatch.

**Workflow:** `.github/workflows/hugo.yml`

1. Installs Hugo Extended
2. Checks out the repo with submodules
3. Builds the site with `hugo --gc --minify`
4. Deploys to GitHub Pages
