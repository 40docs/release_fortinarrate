# FortiNarrate — releases

Built artefacts only. No source lives here.

The source is at [`40docs/app_fortinarrate`](https://github.com/40docs/app_fortinarrate),
which is where issues and pull requests belong. This repository exists so that
releases can be fetched without access to that one.

## What lands here

| | |
|---|---|
| `FortiNarrate-*.dmg` / `*.exe` | installers, macOS and Windows |
| `components.json` + `.sig` | the signed update manifest |
| `payload-*.tar.gz` | editor updates, applied by the app itself |
| `libreoffice-*.tar.gz` | the slide-import component, on its own tag |

Every artefact is published by CI from a tag on the source repository. Nothing
is uploaded by hand.

## Verifying

`components.json` is signed with ed25519, and the public key is compiled into
every copy of the application. The app checks that signature before acting on
the manifest, and checks each archive against the digest the manifest names — so
this repository does not have to be trusted, only reachable.
