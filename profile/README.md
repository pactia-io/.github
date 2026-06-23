# pactia.io

### Official public package host for Pactia

**Browse packages here until [pactia.io](https://pactia.io) is live.**

This GitHub organization is the official placeholder for public Pactia packages — a stable, browsable home for versioned intent you can `import` in `.pactia` files. The future registry at [pactia.io](https://pactia.io) will serve the same artifacts; repos here are the interim mirror.

---

### What lives here

| Kind | Example | Purpose |
| --- | --- | --- |
| **Kernel** | `@pactia/kernel` | Core tags, macros, and registry defaults |
| **Stack** | `@pactia/rust-stack` | Platform law — language, errors, pagination |
| **Surface** | `@pactia/html-css-js` | UI / static-site stack macros |
| **Community** | `@github.com/you/your-rules` | Shared domain or compliance intent |

Each package is a git repository with `pactia.toml`, `index.pactia`, and semver tags (`v1.0.0`, `v1.1.0`, …). The `pactia` CLI resolves coordinates to these repos and vendors them into `.pactia/packages/`.

---

### Consume a package

```bash
# Install the pactia CLI (includes build)
curl -fsSL https://raw.githubusercontent.com/pactia-lang/pactia/main/scripts/install-pactia.sh | bash

pactia init my-product
pactia add @pactia/kernel ^1.0
pactia build
```

In your product:

```pactia
pactia 1.0

import @pactia/kernel;
import @pactia/rust-stack;

product MyApp {
  > Your product intent in prose — tags and packages layer on when you need enforcement.

  #rust-stack
}
```

Coordinates resolve from built-in defaults, `~/.pactia/config.toml`, or Go-style host paths (`@github.com/org/repo`). Lockfiles pin name, version, and digest.

---

### Publish a package

1. Create a repository under this org (or use your own host with a full `@github.com/org/repo` coordinate).
2. Add `pactia.toml` (package name must match the import coordinate) and `index.pactia` (exported tags/macros).
3. Tag a release: `git tag v1.0.0 && git push origin v1.0.0`.

No central upload step — publish is git + semver tags. Optional later: `pactia publish` and HTTP archives from pactia.io.

---

### Not the language home

Pactia itself — spec, compiler, CLI, editor — lives under **[pactia-lang](https://github.com/pactia-lang)**.

| | Where |
| --- | --- |
| Language spec | [pactia-lang/spec](https://github.com/pactia-lang/spec) |
| Compiler (`pactiac`) | [pactia-lang/pactiac](https://github.com/pactia-lang/pactiac) |
| Package manager (`pactia`) | [pactia-lang/pactia](https://github.com/pactia-lang/pactia) |
| **Public packages** | **here — [pactia-io](https://github.com/pactia-io)** |
| Registry (coming) | [pactia.io](https://pactia.io) |

---

### Status

**Registry:** [pactia.io](https://pactia.io) is not live yet. Use this org to discover and link to official `@pactia/*` packages until the web registry ships.

**Get involved** — [spec issues](https://github.com/pactia-lang/spec/issues/new?template=spec_clarification.yml) · [pactia](https://github.com/pactia-lang/pactia/issues) · [pactiac](https://github.com/pactia-lang/pactiac/issues)

[pactia.io](https://pactia.io) · [docs.pactia.io](https://docs.pactia.io) *(coming soon)*
