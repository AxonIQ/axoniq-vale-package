# Vale Package

This folder contains the configuration for AxonIQ Vale package.

Since vale v3.0, [config folder structure for vocabularies has changed](https://vale.sh/docs/topics/vocab/#folder-structure) and Vocabularies have been moved from `<StylesPath>/Vocab` to `<StylesPath>/config/vocabularies`.

Temporarily, we keep a symbolic link in `Vocab` to `/config/vocabularies` to keep compatibility for older versions of vale.

## Pinned dependencies

The `proselint` and `Google` packages are pinned to exact release URLs in `.vale.ini`.
If you list them by name only, `vale sync` downloads the latest upstream release.
A new upstream release can then break every consuming docs build without any change here (see [#6](https://github.com/AxonIQ/axoniq-vale-package/issues/6)).

Upgrade them on purpose: bump the version in the URL, check the package's `meta.json` for the minimum `vale_version`, test the change, and cut a new release of this package.

Current pins:

| Package | Version | Minimum Vale |
|---|---|---|
| proselint | v0.3.4 | any 3.x |
| Google | v0.7.2 | any 3.x |

`proselint` v0.4.0 and later need Vale >= 3.28.1.
Before upgrading to it, raise the org-level Actions variable `LIBRARY_VALE_VERSION` (currently `3.3.0`) to match.
