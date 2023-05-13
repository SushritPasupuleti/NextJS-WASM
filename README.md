# NextJS with WASM (Rust)

A repo to test WASM with NextJS.

## Setup

Install dependencies:

```bash
cd web
yarn
```

Ensure `wasm-pack` is installed:

```bash
cargo install wasm-pack
```

## Running

Compile the Rust code and start the NextJS dev server:

```bash
cd web
yarn dev:wasm
```

## Adding a new WASM module

1. Create a new Rust crate in `wasm/`:

```bash
# inside nextjs root folder
cd web
cargo new --lib <name>
```

2. Add the crate to `wasm/Cargo.toml`:

```toml
[dependencies]
wasm-bindgen = "0.2.85"

[lib]
crate-type = ["cdylib"]
```

3. Install module as depencency in `web/package.json`:

```json
{
  "dependencies": {
    "<name>": "file:../wasm/<name>"
  }
}
```

4. Install Install dependencies:

```bash
cd web
yarn
cd <lib-name>
yarn
```

