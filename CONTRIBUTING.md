# Contributing to OpenHPS

When contributing to an OpenHPS repository, please first discuss the change you wish to make via an
issue, email (info@openhps.org), or any other method with the owners of the repository before making
a change.

Please note we have a [Code of Conduct](CODE_OF_CONDUCT.md); please follow it in all your
interactions with the project.

## Development requirements

- **Node.js >= 22.12** is required for development. The published packages declare
  `engines.node: ">=22.0.0"`, which describes the *runtime* of the shipped package. The higher
  development floor exists because the test suites use `chai` 6, which is ESM-only: requiring an ESM
  package from the CommonJS-compiled specs (`require(esm)`) is only unflagged from Node 22.12.
- **npm is the package manager** across the whole fleet. Every repository carries a
  `package-lock.json` and a pinned `packageManager` field. Use `npm ci` — never `npm install` — in
  CI and whenever you want to reproduce a known-good tree.
- **Conventional commits are enforced** by commitlint through a husky `commit-msg` hook. Run
  `npm ci` once after cloning so the hooks are installed (`prepare` runs husky).

## Getting started

```bash
npm ci
npm run build
npm run lint
npm test
```

## Pull Request Process

1. Ensure any install or build dependencies are removed before the end of the layer when doing a
   build. The included `.gitignore` should make sure that this is the case.
2. Update the `README.md` with details of changes to the interface, this includes new environment
   variables, exposed ports, useful file locations and container parameters.
3. Increase the version numbers in any example files and the `README.md` to the new version that
   this Pull Request would represent. The versioning scheme we use is [SemVer](http://semver.org/).
4. You may merge the Pull Request in once you have the sign-off of two other developers, or if you
   do not have permission to do that, you may request the second reviewer to merge it for you.

## Coverage

Coverage thresholds live in each repository's `.nycrc.json` and are enforced by
`nyc check-coverage`. **Thresholds only ever go up.** If a change raises coverage, raise the
threshold to match in the same pull request; never lower a threshold to make a build pass.

## Cross-module dependencies

`@openhps/*` packages depend on each other through `peerDependencies`. Every such range must carry
an **upper bound** (for example `">=1.0.16 <2"`), and the matching `devDependencies` entry must
satisfy the same floor so CI tests what consumers actually receive. This is checked automatically by
`scripts/check-peers.mjs`, which runs as part of `npm run lint`.
