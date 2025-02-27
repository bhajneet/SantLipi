# Contributing

Anyone providing assistance to the future of this project is considered a contributor. If you wish to play a part in this project, then thank you! This document outlines some of the ways to help.

## Run QA (Quality Assurance)

**Requirements:**

- [Python](https://www.python.org/)
- [Poetry](https://python-poetry.org/)

**Testing:**

- Install project dependencies with `poetry install`.
- Build files with `poetry run build`.
- Open `build/qa/index.html` to view the Sant Lipi Test Suite.

If you wish to add tests or make changes to QA, please see "Open Pull Requests" below.

## Modify/Change Font

**Requirements:**

- [Glyphs 3](https://glyphsapp.com/)

**Development**:

- Use Glyphs 3 to open `sources/SantLipi.glyphs`.

If you wish to share changes back upstream, please see "Open Pull Requests" below.

## Open Pull Requests

_Role: contributors wishing to change the project source code_

**Requirements:**

- [Git](https://git-scm.com/)
- [GitHub](https://github.com/)

**Workflow:**

- Fork this repository
- Create a branch from `main`
- Make any changes
- Submit a pull request

Note: Before creating new branches, ensuring that the forked `main` is up to date with the upstream/original `main` will ease workflow.

## Merge PRs

_Role: project authors/maintainers_

- Pull requests should be squashed or rebased.
- Commit messages on `main` branch should generally conform to [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/).
- No commit's type should be `fix`.

**Note**

OpenType specifications only allow for a "Major" and "Minor" version. There is no "Patch" version number. In Sant Lipi packages, the patch number should always be 0. The minor version in Glyphs should be 3 digits long (e.g. SemVer 0.1.0 becomes Version 0.001, SemVer 2.15.0 becomes Version 2.015). Minor version should not exceed 999. If that ever happens, then should probably just bump the Major version number and reset Minor to 0. Installation software can use these version strings to compare font versions. Please adhere to these rules.

**Types**

Some _types_ correlate with incrementing major, minor, and patch versions in [Semantic Versioning](https://semver.org/). These _types_ should only be used for code changes in the `sources` folder. (This folder is considered the project's API.)

- `BREAK` increments major. To be used when making incompatible changes to the API. E.g. deleting glyphs from the font.
- `feat` increments minor. To be used when adding backwards-compatible functionality to the API. E.g. changing metrics, shapes, features, etc.

Project authors/maintainers should never merge a PR whose commit(s) begin with `fix`, as there are no patch bumps for this project. See **Note** above.

All other _types_ are ignored by the version bump workflow. These types are typically used outside the API folder, but may change API source code without actually affecting anything for the end user. Valid non-versioning (non-API related) _types_ include: `build`, `ci`, `docs`, `perf`, `refactor`, `revert`, `style`, and `test`.

## Release

_Role: project authors/maintainers_

See [actions](https://github.com/shabados/SantLipi/actions) for incrementing the version and publishing.

**Version Increment/Bump**

- This workflow bumps/increments the version via a Pull Request.
- The PR will list all the commit history from after the last release.
- The PR must be merged prior to publishing.

Note: Leave the override field blank for automatic versioning.

Note: If overriding the version bump, remember to use 0 for the patch version number.

**Publish**

- This workflow should immediately follow a version increment/bump PR merge.
- This workflow will publish package(s) and create a GitHub release.
