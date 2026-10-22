# Repository Guidelines

## Project Structure

This repository is a static website served from its root. `index.html` is the main page and `index_Side-B.html` is the alternate page; both use `Styles.css`. Keep images, GIFs, video, and other media in `pictures_and_gifs/`, and reference them with relative paths. `wrangler.jsonc` configures Cloudflare Wrangler to serve the repository root as static assets. There is no separate source, test, or build directory.

## Development Commands

No package manifest or build pipeline is defined. Use Wrangler through `npx` if it is available in your environment:

- `npx wrangler dev` starts the local development server using `wrangler.jsonc`.
- `npx wrangler deploy` publishes the configured static assets to Cloudflare; use only when authorized and configured for the intended account.

For a quick local check without Wrangler, open `index.html` in a browser. Verify both pages and their images, links, video playback, and interactive controls after edits.

## Coding Style

Use semantic HTML, two-space indentation for new markup, and descriptive, hyphenated CSS class names. Keep shared presentation in `Styles.css`; use relative asset URLs and preserve the existing filename casing (including `Styles.css`). Keep page-specific behavior small and close to the markup it controls unless it is reused. Match the existing plain HTML, CSS, and JavaScript setup; no formatter or linter is configured.

## Testing

There is no automated test framework or coverage requirement. For user-facing changes, manually inspect both `index.html` and `index_Side-B.html` at desktop and narrow viewport widths. Check browser console errors, especially when changing inline scripts, and verify referenced asset paths and interactive behavior.

## Commits and Pull Requests

Recent history uses short, informal, sentence-case summaries (for example, “Add initial wrangler configuration file”). Keep commit subjects concise and action-oriented. Pull requests should describe the visible change, list any manual checks performed, link related issues when applicable, and include screenshots for visual changes. Call out new or replaced media assets.

## Configuration and Assets

Keep deployment configuration changes in `wrangler.jsonc`. Avoid adding secrets to the repository; configure credentials through Wrangler or the deployment environment. Optimize large media where practical and ensure every added asset is referenced with its correct case-sensitive path.
