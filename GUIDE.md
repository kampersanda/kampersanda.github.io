# Guide to development

First, see https://sighingnow.github.io/jekyll-gitbook/.

## Deploying the page on localhost

Start the server with the following command:

```console
docker compose build
docker compose up
```

http://localhost:4000/ will be available.

### References

- https://note.com/sistersatori/n/nf2e6660661df

## Customization

[custom-local.css](./assets/gitbook/custom-local.css) is available for customization.

### Research page link badges

The research page uses CSS-only badges for links such as `doi`, `arXiv`, `code`, `pdf`, `slide`, `video`, `repo`, and `read-only`.

- The page-specific class is enabled in [_pages/research.md](./_pages/research.md) with `body_class: research-page`.
- The class is attached to the content section in [_includes/body.html](./_includes/body.html).
- The badge rules themselves live in [assets/gitbook/custom-local.css](./assets/gitbook/custom-local.css).

To add a new badge target, update `custom-local.css` in three places:

1. Add the URL pattern to the shared badge selector block.
2. Add the same URL pattern to the color block of the intended badge kind, or create a new color block.
3. Add the same URL pattern to the hover selector block.

Example:

```css
.markdown-section.research-page a[href*="example.com"]
```

This mechanism is intentionally simple and pattern-based. Markdown in [_pages/research.md](./_pages/research.md) can stay as ordinary links like `[slide](https://...)`.
