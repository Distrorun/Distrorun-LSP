# DistroRun LSP

Schema-powered autocompletion and validation for [DistroRun](https://github.com/distrorun) YAML configuration files.

## Overview

DistroRun LSP is a Visual Studio Code extension that provides intelligent editing support for DistroRun configuration files. It delivers real-time validation, context-aware autocompletion, and inline documentation by leveraging a JSON Schema through the [Red Hat YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) extension.

## Features

- **Autocompletion** — Context-aware suggestions for configuration keys, values, and enums.
- **Validation** — Real-time diagnostics for invalid keys, incorrect types, and missing required fields.
- **Hover Documentation** — Inline descriptions and usage examples on hover.

## Requirements

- Visual Studio Code 1.75 or later
- [Red Hat YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) (installed automatically as a dependency)

## Configuration Reference

The extension validates the following top-level keys in `.yaml` and `.yml` files:

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `version` | `string` | Yes | Semantic version of the configuration file |
| `name` | `string` | Yes | Name of the DistroRun configuration |
| `distro` | `object` | Yes | Target OS (`fedora` or `alpine`) and system profile |
| `packages` | `string[]` | No | Packages to install via the native package manager |
| `users` | `object[]` | Yes | System users, each with a `name` and `password` |
| `services` | `object` | No | Services to enable at boot |
| `build` | `object` | No | Build options such as SBOM generation |

## Example

```yaml
version: "1.0"
name: my-server

distro:
  base: fedora
  type: server

packages:
  - nginx
  - vim
  - curl

users:
  - name: root
    password: changeme
  - name: charif
    password: securepass

services:
  enable:
    - nginx
    - sshd

build:
  sbom: true
```

## Development

```bash
# Install dependencies
npm install

# Compile TypeScript
npm run compile

# Launch the Extension Development Host
# Press F5 in VS Code
```

## License

MIT
