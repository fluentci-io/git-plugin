# Git Plugin

[![ci](https://github.com/fluentci-io/git-plugin/actions/workflows/ci.yml/badge.svg)](https://github.com/fluentci-io/git-plugin/actions/workflows/ci.yml)

This plugin sets up your CI/CD pipeline with a specific version of [Git](https://git-scm.com/).

## 🚀 Usage

Add the following command to your CI configuration file:

```bash
fluentci run --wasm git setup
```

## Functions

| Name   | Description                               |
| ------ | ----------------------------------------- |
| setup  | Installs a specific version of git.       |

## Code Usage

Add `fluentci-pdk` crate to your `Cargo.toml`:

```toml
[dependencies]
fluentci-pdk = "0.1.9"
```

Use the following code to call the plugin:

```rust
use fluentci_pdk::dag;

// ...

dag().call("https://pkg.fluentci.io/git@v0.1.0?wasm=1", "setup", vec!["latest"])?;
```

## 📚 Examples

Github Actions:

```yaml
- name: Setup Fluent CI CLI
  uses: fluentci-io/setup-fluentci@v5
  with:
    wasm: true
    plugin: git
    args: |
      setup
- name: Show git version
  run: |
    type git
    git version
```
