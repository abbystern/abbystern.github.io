# Abby Stern’s portfolio

A static, light-theme Jekyll portfolio. All website source files live **at the repository root**. Page content is Markdown with YAML front matter; design is shared HTML and CSS. There is no Node application, backend, database, tracker, or separate preview app.

## Publish with GitHub Pages

1. Create or use the repository **`abbystern/abbystern.github.io`**.
2. Put this repository’s root files on its **`main`** branch.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select **main** and **/ (root)**, then save.
6. GitHub builds the site automatically. Once its Pages deployment succeeds, visit **https://abbystern.github.io**.

No custom Actions workflow, manual build, or uploaded build output is needed. The site uses supported `jekyll-seo-tag` and `jekyll-sitemap` plugins. Keep `baseurl: ""` in `_config.yml`; this is a user site, not a project site.

This project is prepared for that configuration. Enabling Pages and the first successful deployment still require access to your GitHub account.

## Update the content

| File | Purpose |
| --- | --- |
| `index.md` | Home introduction and connection links |
| `about.md` | First-person story, education, skills, and interests |
| `work-experience.md` | Work history and résumé-sourced achievements |
| `contact.md` | Public email and LinkedIn links |
| `_config.yml` | Site title, description, publishing URL, contact details |
| `_layouts/` | Reusable page structure |
| `_includes/` | Shared navigation, head, and footer |
| `assets/css/styles.css` | Colors, typography, layout, responsive rules |
| `assets/images/abby-stern.webp` | Optimized portrait |
| `assets/favicon.svg` | Site favicon |

Edit text below the front matter between the `---` markers. Keep front matter keys and permalink values intact. Use Markdown headings, lists, and links. Use `relative_url` for internal links and assets, for example:

```liquid
[About me]({{ "/about/" | relative_url }})
```

Public contact information is deliberately limited to Gmail and LinkedIn. A `mailto:` link makes the address public and relies on the visitor having an email app configured. The original résumé’s phone number and Berkeley email are not published, and the original PDF is not offered as a download.

Original uploads are private working materials, not site assets. Do not commit a résumé containing contact information you do not intend to share. Jekyll exclusions keep support files out of the generated site, **but do not make files in a public GitHub repository private**.

## Preview locally

Install Ruby 3.3 and Bundler, then from the repository root run:

```sh
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

Open http://127.0.0.1:4000. Jekyll rebuilds after content changes; restart it after editing `_config.yml`.

For Replit’s preview, run the **Jekyll portfolio** workflow. It serves this same root-level Jekyll site—not a separate app. Dependencies are installed locally with `bundle install`.

To check a production build:

```sh
JEKYLL_ENV=production bundle exec jekyll build
```

`_site/` is generated output and ignored by Git. Do not move the website source there or select it as the Pages source.

## Check links and responsive layout

At both **375px** and **1280px** browser widths, check all four pages:

- All navigation links load, and the current page is identified.
- No horizontal scrolling or clipped text.
- The portrait fits and loads.
- Tab through links: focus remains visible, and the skip link reaches main content.
- Gmail and LinkedIn links have the correct destinations.
- `/404.html`, `/sitemap.xml`, and `/robots.txt` load.

## Run Lighthouse

With the site running locally, open Chrome DevTools → **Lighthouse**. Choose Navigation mode and the Performance, Accessibility, Best Practices, and SEO categories. Run a mobile audit and a desktop audit.

If you have Node tooling available outside this site, the optional CLI equivalent is:

```sh
npx lighthouse http://127.0.0.1:4000 \
  --output=html --output=json --output-path=/tmp/abby-lighthouse
```

Node is **not** a website dependency; this optional auditing command creates no application files. Aim for **90 or higher in each category**. Hosting conditions can affect scores, so repeat after GitHub Pages publishes.

### First-version verification

Checked on October 3, 2026 (America/Los_Angeles):

- The GitHub Pages-compatible Jekyll 3.10 build succeeded.
- Home, About, Work Experience, and Contact were visually checked at 375px and 1280px widths.
- All four pages, their internal links and assets, the 404 page, favicon, sitemap, and robots file returned successfully.
- The public output contains no original résumé PDF, phone number, Berkeley email, Node packages, or starter application files.
- The current branch is `main`, and the website source is at the repository root.

Lighthouse 13.5 homepage audits against the local preview:

| Mode | Performance | Accessibility | Best Practices | SEO |
| --- | ---: | ---: | ---: | ---: |
| Mobile | 100 | 100 | 100 | 100 |
| Desktop | 100 | 100 | 100 | 100 |

These are measured local-preview results, not scores from a published GitHub Pages deployment. Repository settings and the first live deployment still need to be enabled in GitHub.

## Choices and assumptions

- A light-only theme follows Abby’s preference; no theme-switch JavaScript is needed.
- Reusable layouts keep content separate from presentation.
- Teal provides readable interactive accents; sage and mustard are decorative, not low-contrast body text.
- System typography avoids remote font requests and tracking.
- The optimized portrait has explicit dimensions to avoid layout shifts.
- Work history and metrics come from the supplied résumé. Estimates and projections remain qualified.
- SEO and sitemap plugins run in GitHub Pages’ built-in Jekyll build.
- The target account is `abbystern`; no GitHub publishing authorization has been assumed.