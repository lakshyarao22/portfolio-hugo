# portfolio-hugo

Personal portfolio website built with [Hugo](https://gohugo.io/) using the [Terminal](https://github.com/panr/hugo-theme-terminal) theme.

## Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.116.0+)
- Git

### Setup

```bash
# Clone the repo
git clone https://github.com/lakshyarao22/portfolio-hugo.git
cd portfolio-hugo

# Add the theme as a submodule
git submodule add -f https://github.com/panr/hugo-theme-terminal.git themes/terminal

# Run the dev server
hugo server -D
```

Open http://localhost:1313 in your browser.

### Build

```bash
hugo --gc --minify
```

Output goes to `./public/`.

## Deployment

This site auto-deploys via GitHub Actions on push to `main`. The workflow:

1. Installs Hugo Extended
2. Builds the site with minification
3. Deploys to GitHub Pages

### GitHub Settings Required

1. Go to **Settings > Pages**
2. Set Source to **GitHub Actions**
3. (For custom domain) Add your domain under **Custom domain** and configure DNS:
   - A records pointing to GitHub Pages IPs
   - Or CNAME record pointing to `lakshyarao22.github.io`

## Structure

```
.
├── .github/workflows/hugo.yml   # CI/CD deployment
├── archetypes/                  # Content templates
├── content/                     # Site content (Markdown)
│   ├── _index.md               # Homepage
│   ├── about/
│   ├── experience/
│   ├── projects/
│   ├── skills/
│   ├── blog/
│   └── contact/
├── static/                      # Static assets (CNAME, images)
├── themes/terminal/             # Hugo theme (git submodule)
└── hugo.toml                    # Site configuration
```

## Adding a Blog Post

```bash
hugo new blog/my-new-post.md
```

Edit the file, set `draft = false` when ready, push to `main`.

## Custom Domain

The site is configured for `inqstv.in`. The CNAME file is in `static/CNAME`.

DNS should point to:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Or CNAME: `lakshyarao22.github.io`
