# olma-core

The package index for [olma](https://github.com/dot12x/olma), a fast macOS package manager.

## Structure

```
packages/
├── ripgrep.toml
├── bat.toml
├── python.toml
└── ...
```

Each TOML file describes one package: GitHub repository, available versions, platform-specific binaries, and SHA-256 checksums. Anything olma installs is defined here.

There is no server, no API. This repository IS the index. olma clones it locally and reads the TOML files directly.

## Adding a package

1. Verify the upstream project has GitHub Releases with macOS binaries (arm64 and/or x64).
2. Create a `packages/<name>.toml` file matching the schema.
3. Compute SHA-256 for each binary asset (`shasum -a 256 file.tar.gz`).
4. Open a pull request.

No upstream author permission is required; rejection reasons are technical only (missing macOS release, wrong format, missing checksums).

## Schema

See the schema reference in the [olma project](https://github.com/dot12x/olma).

## License

Dual-licensed under [MIT](LICENSE-MIT) and [Apache-2.0](LICENSE-APACHE).
