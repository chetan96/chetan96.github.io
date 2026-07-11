# chetan96.github.io

Personal website — hosted on GitHub Pages, built with Jekyll.

**Live at:** https://chetan96.github.io

---

## Editing content

Almost all updates are just editing markdown or YAML — no code.

| To change...                       | Edit this file                                |
| ---------------------------------- | --------------------------------------------- |
| Name, tagline, site-wide meta      | `_config.yml`                                 |
| Home page bio                      | `index.html`                                  |
| Social links (footer)              | `_data/links.yml`                             |
| Publications                       | `_data/publications.yml`                      |
| CV education and experience        | `_data/experience.yml`                        |
| Add a project                      | New file in `_projects/`                      |
| Add a blog post                    | New file in `_posts/YYYY-MM-DD-title.md`      |
| Attach a post to a project (devlog)| Blog post with `project: <slug>` in front matter |

Push to `main` → GitHub Pages rebuilds and deploys automatically.

## Placeholders you need to fill in

YouTube and other project/demo links aren't set yet — add them to `_data/links.yml` or the relevant `_projects/*.md` file once you have them.

## Adding a blog post

Copy `_posts/2026-07-09-hello.md` as a template. Front matter:

    ---
    title: My post title
    date: 2026-07-15
    tags: [gpu, notes]
    summary: One-line summary shown on the blog index.
    ---

Write markdown below the front matter. It publishes automatically at `/blog/my-post-title/` on the next push.

## Adding a project

Copy `_projects/warpscope.md` as a template. Front matter:

    ---
    title: My Project
    subtitle: Short subtitle
    summary: One-line summary shown on the projects grid.
    dates: Jun 2026 – Aug 2026
    tags: [triton, cuda]
    featured: false   # true to show on the home page
    order: 3          # lower = appears earlier
    links:
      - name: GitHub
        url: "https://github.com/..."
    ---

## Attaching a blog post to a project (devlog)

Any blog post with a `project: <slug>` field in its front matter appears under that project's page in a Devlog section. The `<slug>` is the filename of the project without `.md`.

Example: to add a devlog post to `_projects/warpscope.md`, create a blog post with:

    ---
    title: Warpscope: measuring barrier stalls
    date: 2026-07-20
    project: warpscope
    tags: [devlog, cuda]
    ---

By default the post also appears in the main blog. To hide it from the main blog, add `hidden: true`.

## Local preview (optional)

Not required — GitHub Pages will build on push. But if you want to preview locally:

    bundle install
    bundle exec jekyll serve
    # open http://localhost:4000

Requires Ruby 3+.

## Directory structure

    _config.yml          site config
    _data/               structured content (publications, links, experience)
    _includes/           reusable HTML snippets (nav, footer, head)
    _layouts/            page templates
    _posts/              blog posts
    _projects/           project pages (collection)
    assets/              css, images
    index.html           home
    blog.html            blog index
    projects.html        projects index
    publications.html    publications index
    cv.html              CV page
    CV_*.pdf             downloadable CV
