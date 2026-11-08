# My path into DevOps

The source of my personal blog, [pimkomen.dev](https://pimkomen.dev).

I've recently started a path into DevOps and hope to pivot into this field in 2027. In the posts on this blog I document that journey: what I learn, what goes wrong, and what I figure out along the way. One day I hope to look back and appreciate all the hard work that went into it.

## How it works

I write posts locally and build the site with Hugo. I push the files to GitHub, and Cloudflare builds and hosts the site on a domain that I obtained.

```
Local (Hugo + Obsidian) -> GitHub -> Cloudflare -> pimkomen.dev
```

## Stack

- [Hugo](https://gohugo.io/) (extended), static site generator
- [Rewired](https://github.com/RigleGit/rewired), a dark, terminal-style Hugo theme, included as a git submodule
- [GitHub](https://github.com/pim050/devopsblog) for version control
- [Cloudflare](https://www.cloudflare.com/) for building, hosting and the domain, configured in `wrangler.toml`
- [Obsidian](https://obsidian.md/) for writing in markdown

## Project structure

```
.
├── content/
│   ├── posts/       blog posts
│   └── projects/    portfolio cards
├── archetypes/      templates for new content
├── themes/rewired/  theme (git submodule)
├── hugo.yaml        site configuration
└── wrangler.toml    Cloudflare deployment configuration
```

## Run it locally

Clone the repository together with the theme submodule:

```bash
hugo server -D
```

Then open the address Hugo prints (usually `http://localhost:1313`). The `-D` flag also shows drafts.

## Write a new post

In obsidian use the template for the posting structure. cmd+shift+N
A new post starts with `draft: true`. Set it to `false` when it is ready to publish.

## Deployment

Every push to `main` triggers a build on Cloudflare, which runs `hugo` and serves the `public/` folder. The Hugo version used by the build is set with the `HUGO_VERSION` build variable in Cloudflare, and should match the version used locally.

## Credits

- Setup guided by [My Hugo website](https://hansterhorst.com/articles/my-hugo-website/) by Hans ter Horst
- Theme: [Rewired](https://github.com/RigleGit/rewired) by RigleGit
