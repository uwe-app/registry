# Registry

This is the plugin registry containing an index of plugin versions and associated meta data; for plugin source code see the [plugins][] repository.

## Packages

The [packages](/packages) directory contains JSON files for each available plugin. Each file indicates which versions have been published and stores meta data such as archive checksums.

Packages are stored by fully qualified plugin name, eg: `std::core.json`.

## Downloads

The downloads directory is used to cache downloaded archives. When a plugin is first downloaded the archive is put in the downloads directory and subsequent attempts to install that version of the plugin will be resolved from the downloads to prevent additional network traffic and to support working offline.

Downloads are stored using the fully qualified plugin name and the version, eg: `std::core::4.1.12.tar.xz`.

## Repositories

The repositories directory is used to cache plugins installed using `git`; each repository is installed using an opaque identifier for the repository which is the `SHA3-256` digest of the URL used to clone the repository.

During installation if a repository is already cloned then the program will perform a `fetch` operation to update the local repository.

## Archives

The archives directory is where plugins installed from archives are extracted to; the folder name for the extracted plugin is an opaque identifier generated from the file system path (`SHA3-256`).

[plugins]: https://github.com/uwe-app/plugins
