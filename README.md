# O2 User Manual

Source of the user manual for [O2](https://github.com/maurizuki/O2), published at <https://maurizuki.github.io/O2-user-manual>.

The site is built with [Jekyll](https://jekyllrb.com) and the [Just the Docs](https://just-the-docs.github.io/just-the-docs/) theme, and deployed to GitHub Pages by the `Deploy Jekyll site to Pages` workflow on every push to `main`.

## Structure

| Path | Content |
|:-----|:--------|
| `index.md` | Home page. |
| `docs/` | Manual pages. `nav_order` in each page's front matter sets its position in the sidebar. |
| `docs/rules/` | The *Rules* section and its child pages. |
| `_config.yml` | Site settings: favicon, color scheme, callout types (`note`, `tip`, `important`, `warning`), and the default `layout` for pages that don't set one. |
| `assets/images/` | Images used by the manual pages, such as the main window wireframe (`main-window.svg`). Link them with `{{ "/assets/images/<file>" \| relative_url }}` so the path works under the site's base URL. |

## Build and preview locally

With Ruby and Bundler installed:

```
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>. The built site is written to `_site`.

## License

The site template is released under the [MIT License](LICENSE). O2 itself is released under the Mozilla Public License 2.0.
