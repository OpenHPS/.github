## Description

<!-- What does this change do, and why? Link any related issue. -->

## Checklist

- [ ] The PR title follows [conventional commits](https://www.conventionalcommits.org/) (`feat:`, `fix:`, `chore:`, …); breaking changes carry a `!` and a `BREAKING CHANGE:` footer
- [ ] Tests added or updated for the change
- [ ] `npm run lint` passes with no errors
- [ ] `npm run build` succeeds
- [ ] Coverage has not been lowered (thresholds in `.nycrc.json` only ratchet up)
- [ ] `npm run build:typedoc` emits no unresolved `{@link}` warnings, if the public API changed
- [ ] No new unbounded `@openhps/*` peer range (`scripts/check-peers.mjs` passes)
