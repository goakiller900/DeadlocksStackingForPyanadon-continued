# Deadlock's Stacking for Pyanodon Continued

An unofficial, community-maintained continuation of **Deadlock's Stacking for Pyanodon**, updated for Factorio 2.1.

The mod adds Deadlock stacking support for intermediate products from the Pyanodon's mod suite. It does not add beltboxes or loaders by itself; those are provided by **Deadlock's Stacking Beltboxes and Compact Loaders Continued**.

## Compatibility

- Factorio 2.1
- `deadlock-beltboxes-loaders-continued` 7.0.3 or newer
- `pycoalprocessing` 3.1.3 or newer
- Optional support for Py Industry, Py High Tech, Py Raw Ores, Py Fusion Energy, Py Petroleum Handling, Py Alien Life and Py Alternative Energy
- Optional support for Deadlock Crating

## Why pycoalprocessing 3.1.3 is required

`pycoalprocessing` 3.1.2 contains a migration bug in `beacon-interference.lua`. When this compatibility mod is added to some existing Py saves, the migration can try to access `storage.beacon_interference_icons` even when that saved-data table does not exist.

The problem is in the Py migration rather than this mod. It was fixed upstream for `pycoalprocessing` 3.1.3 by skipping the migration when the old table is absent:

https://github.com/pyanodon/pybugreports/issues/1515

If 3.1.3 is not yet available on the Factorio Mod Portal, this continuation cannot be installed through the normal dependency resolver yet.

## Installation

Install the mod through the Factorio Mod Portal when a compatible release is available, or download the release ZIP from GitHub and place it unchanged in your Factorio `mods` directory.

Do not extract the ZIP. Factorio expects the archive to contain a single top-level folder named:

```text
DeadlocksStackingForPyanadon-continued_<version>
```

## Status

This continuation keeps the original gameplay concept, item coverage and graphics as intact as possible while restoring compatibility with current Factorio and Py releases.

This is not an official release from the original maintainers. If the original maintainers return and want to resume maintenance, this continuation can be archived, redirected or transferred as appropriate.

## Credits

- Original author: Chrisdec
- Original collaborators: Billbo99 and The_Ghost
- Factorio 2.1 continuation: goakiller900
- Original project contributors and icon authors remain credited through the repository history, changelog and included licence files

## Releases

GitHub Actions validates `info.json`, builds a deterministic Factorio-ready ZIP and creates a SHA-256 checksum.

On pushes to `main`, the workflow creates an immutable GitHub release for the version in `info.json`. Pull requests only build and validate the archive.

Factorio Mod Portal publication is enabled when this repository secret is configured:

```text
FACTORIO_API_KEY
```

The secret is never stored in the repository. A manual workflow run can also build the ZIP and optionally publish the current version to the Mod Portal.
