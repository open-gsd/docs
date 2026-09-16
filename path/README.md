# GSD Path documentation site

This directory contains the GSD Path section of the Open GSD documentation site.
The site root and shared `docs.json` are one directory above, in `open-gsd/docs`.
The GSD Path tab in that configuration owns navigation for these pages.

## Preview

From the repository root, with Node.js and npm installed:

```bash
npx --yes mint@4.2.894 dev
```

Open the local address printed by the CLI. The default is `http://localhost:3000`.
The pinned CLI version is the version used to validate this site. It does not add
dependencies to the GSD Path package.

Local preview search requires `mint login`. Page rendering and navigation can be
checked without signing in.

## Validate changes

Run from the documentation repository root:

```bash
npx --yes mint@4.2.894 validate
npx --yes mint@4.2.894 broken-links
```

Check the rendered page after editing navigation or components. Every public page
needs a title and description in its frontmatter and an entry in `docs.json`.
Use root-relative internal links beginning with `/path/`, without extensions.
Mintlify ignores `README.md`; it is a maintainer file, not a site page.

## Maintain content

The site is a reader-facing guide. Keep product claims aligned with the canonical
repository contracts; do not copy the agent SOP into MDX or edit generated skill
resources to change documentation.

| Site area | Source to check when behavior changes |
| --- | --- |
| Installation, quickstart, hosts | `README.md`, `FULL.md`, installer help |
| Workflow, programs, shipping, artifacts | `AGENTS.md`, `WORKFLOW.md`, canonical phase skills |
| Updates and guard hooks | `UPDATE.md`, `HOOKS.md` |
| Migration | `MIGRATE.md` |
| Host evidence | `docs/trust-validation/HOST-MATRIX.md` |

Source paths in this table are relative to the `open-gsd/gsd-path` repository root.
Source links in the published pages point to GitHub so readers can inspect the full contracts.
Each product contract has one authoritative source guide. When behavior changes,
update that owner and replace stale copies on site pages with a short pointer.
Do not describe historical host receipts as proof of a newer release.

## Deploy

This section uses the existing `open-gsd/docs` Mintlify project, shared theme,
and deployment settings. There is no separate `path/docs.json` or Path site.
Use the documentation repository root as the site directory, not `/path`.
The site pages are served under `/path/`; the entry page is `/path/introduction`.

Publish through the documentation repository's normal review and deployment
process. Moving these files does not push changes or change dashboard settings.

References: [Mintlify navigation](https://www.mintlify.com/docs/organize/navigation)
and [CLI commands](https://www.mintlify.com/docs/cli/commands).
