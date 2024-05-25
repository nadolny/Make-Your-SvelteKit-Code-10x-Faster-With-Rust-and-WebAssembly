# Make-Your-SvelteKit-Code-10x-Faster-With-Rust-and-WebAssembly

## Check create-svelte

Everything you need to build a Svelte project, powered by
[`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or
`pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an
> [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

## Create project benchmark

```bash
$ npm create svelte@latest benchmark
Need to install the following packages:
  create-svelte@6.2.0
Ok to proceed? (y) y

create-svelte version 6.2.0

┌  Welcome to SvelteKit!
│
◇  Which Svelte app template?
│  Skeleton project
│
◇  Add type checking with TypeScript?
│  Yes, using TypeScript syntax
│
◇  Select additional options (use arrow keys/space bar)
│  none
│
└  Your project is ready!

✔ Typescript
  Inside Svelte components, use <script lang="ts">

Install community-maintained integrations:
  https://github.com/svelte-add/svelte-add

Next steps:
  1: cd benchmark
  2: npm install
  3: git init && git add -A && git commit -m "Initial commit" (optional)
  4: npm run dev -- --open

To close the dev server, hit Ctrl-C

Stuck? Visit us at https://svelte.dev/chat
[nadolny@marcos-inspiron3583 Make-Your-SvelteKit-Code-10x-Faster-With-Rus
```

## Create rust lib

```bash
$ cargo new sum --lib
    Creating library `sum` package
note: see more `Cargo.toml` keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html
```

```bash
sum]$ cargo add wasm-bindgen
    Updating crates.io index
      Adding wasm-bindgen v0.2.92 to dependencies
             Features:
             + spans
             + std
             - enable-interning
             - gg-alloc
             - serde
             - serde-serialize
             - serde_json
             - strict-macro
             - xxx_debug_only_print_generated_code
    Updating crates.io index
```

```bash
sum]$ cargo build --release --target=wasm32-unknown-unknown
   Compiling proc-macro2 v1.0.84
   Compiling unicode-ident v1.0.12
   Compiling wasm-bindgen-shared v0.2.92
   Compiling log v0.4.21
   Compiling once_cell v1.19.0
   Compiling bumpalo v3.16.0
   Compiling wasm-bindgen v0.2.92
   Compiling cfg-if v1.0.0
   Compiling quote v1.0.36
   Compiling syn v2.0.66
   Compiling wasm-bindgen-backend v0.2.92
   Compiling wasm-bindgen-macro-support v0.2.92
   Compiling wasm-bindgen-macro v0.2.92
   Compiling sum v0.1.0 (../sum)
    Finished `release` profile [optimized] target(s) in 4.53s
```

- [The wasm-bindgen Command Line Interface](https://rustwasm.github.io/wasm-bindgen/reference/cli.html)

```bash
sum]$ cargo install -f wasm-bindgen-cli
    Updating crates.io index
  Installing wasm-bindgen-cli v0.2.92
    Updating crates.io index
   Compiling libc v0.2.155
   Compiling proc-macro2 v1.0.84
   Compiling unicode-ident v1.0.12
   Compiling autocfg v1.3.0
   Compiling cfg-if v1.0.0
   Compiling crossbeam-utils v0.8.20
   Compiling log v0.4.21
   Compiling rayon-core v1.12.1
   Compiling syn v1.0.109
   Compiling version_check v0.9.4
   Compiling anyhow v1.0.86
   Compiling either v1.12.0
   Compiling hashbrown v0.12.3
   Compiling indexmap v1.9.3
   Compiling memchr v2.7.2
   Compiling unicase v2.7.0
   Compiling unicode-segmentation v1.11.0
   Compiling fallible-iterator v0.2.0
   Compiling stable_deref_trait v1.2.0
   Compiling leb128 v0.2.5
   Compiling quote v1.0.36
   Compiling crossbeam-epoch v0.9.18
   Compiling getrandom v0.2.15
   Compiling heck v0.3.3
   Compiling wasm-encoder v0.29.0
   Compiling crossbeam-deque v0.8.5
   Compiling wasmparser v0.80.2
   Compiling gimli v0.26.2
   Compiling cc v1.0.98
   Compiling rayon v1.10.0
   Compiling syn v2.0.66
   Compiling ring v0.17.8
   Compiling serde v1.0.203
   Compiling tinyvec_macros v0.1.1
   Compiling rustix v0.38.34
   Compiling tinyvec v1.6.0
   Compiling bitflags v2.5.0
   Compiling linux-raw-sys v0.4.14
   Compiling walrus-macro v0.19.0
   Compiling id-arena v2.2.1
   Compiling unicode-normalization v0.1.23
   Compiling mime_guess v2.0.4
   Compiling serde_derive v1.0.203
   Compiling rand_core v0.6.4
   Compiling aho-corasick v1.1.3
   Compiling walrus v0.20.3
   Compiling num-traits v0.2.19
   Compiling unicode-bidi v0.3.15
   Compiling ppv-lite86 v0.2.17
   Compiling fastrand v2.1.0
   Compiling rustls-pki-types v1.7.0
   Compiling regex-syntax v0.8.3
   Compiling httparse v1.8.0
   Compiling spin v0.9.8
   Compiling serde_json v1.0.117
   Compiling percent-encoding v2.3.1
   Compiling untrusted v0.9.0
   Compiling form_urlencoded v1.2.1
   Compiling rand_chacha v0.3.1
   Compiling tempfile v3.10.1
   Compiling wasm-bindgen-wasm-conventions v0.2.92
   Compiling idna v0.5.0
   Compiling regex-automata v0.4.6
   Compiling adler v1.0.2
   Compiling itoa v1.0.11
   Compiling alloc-no-stdlib v2.0.4
   Compiling powerfmt v0.2.0
   Compiling mime v0.3.17
   Compiling wasm-bindgen-shared v0.2.92
   Compiling rustls v0.22.4
   Compiling safemem v0.3.3
   Compiling ryu v1.0.18
   Compiling buf_redux v0.8.4
   Compiling deranged v0.3.11
   Compiling regex v1.10.4
   Compiling alloc-stdlib v0.2.2
   Compiling miniz_oxide v0.7.3
   Compiling url v2.5.0
   Compiling rand v0.8.5
   Compiling rustls-webpki v0.102.4
   Compiling twoway v0.1.8
   Compiling num_cpus v1.16.0
   Compiling crc32fast v1.4.2
   Compiling zeroize v1.8.1
   Compiling ascii v1.1.0
   Compiling quick-error v1.2.3
   Compiling num-conv v0.1.0
   Compiling httpdate v1.0.3
   Compiling num_threads v0.1.7
   Compiling chunked_transfer v1.5.0
   Compiling iana-time-zone v0.1.60
   Compiling time-core v0.1.2
   Compiling subtle v2.5.0
   Compiling time v0.3.36
   Compiling chrono v0.4.38
   Compiling tiny_http v0.12.0
   Compiling multipart v0.18.0
   Compiling flate2 v1.0.30
   Compiling threadpool v1.8.1
   Compiling brotli-decompressor v2.5.1
   Compiling wasm-bindgen-wasm-interpreter v0.2.92
   Compiling wasm-bindgen-threads-xform v0.2.92
   Compiling webpki-roots v0.26.1
   Compiling wasm-bindgen-multi-value-xform v0.2.92
   Compiling wasm-bindgen-externref-xform v0.2.92
   Compiling filetime v0.2.23
   Compiling atty v0.2.14
   Compiling sha1_smol v1.0.0
   Compiling base64 v0.22.1
   Compiling base64 v0.21.7
   Compiling strsim v0.10.0
   Compiling rustc-demangle v0.1.24
   Compiling termcolor v1.4.1
   Compiling once_cell v1.19.0
   Compiling base64 v0.13.1
   Compiling lazy_static v1.4.0
   Compiling humantime v2.1.0
   Compiling rouille v3.6.2
   Compiling env_logger v0.8.4
   Compiling docopt v1.1.1
   Compiling ureq v2.9.7
   Compiling wasm-bindgen-cli-support v0.2.92
   Compiling wasm-bindgen-cli v0.2.92
    Finished `release` profile [optimized] target(s) in 59.66s
warning: the following packages contain code that will be rejected by a future version of Rust: buf_redux v0.8.4, multipart v0.18.0
note: to see what the problems were, use the option `--future-incompat-report`, or run `cargo report future-incompatibilities --id 1`
  Installing /home/nadolny/.cargo/bin/wasm-bindgen
  Installing /home/nadolny/.cargo/bin/wasm-bindgen-test-runner
  Installing /home/nadolny/.cargo/bin/wasm2es6js
   Installed package `wasm-bindgen-cli v0.2.92` (executables `wasm-bindgen`, `wasm-bindgen-test-runner`, `wasm2es6js`)
```

- Now run "wasm-bindgen" to pack this WebAssembly, so we can run it with Svelte

```bash
sum]$ wasm-bindgen target/wasm32-unknown-unknown/release/sum.wasm --out-dir pkg
```

```bash
$ npm i -D vite-plugin-wasm
$ npm i -D vite-plugin-top-level-await
```

## Test

```bash
$ npm run dev

> benchmark@0.0.1 dev
> vite dev

Forced re-optimization of dependencies

  VITE v5.2.11  ready in 787 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
1000000
Sum large array in JS: 11.726ms
1000000
Sum large array in WASM: 2.911ms
1000000
Sum large array in JS: 18.175ms
1000000
Sum large array in WASM: 1.456ms
1000000
Sum large array in JS: 15.395ms
1000000
Sum large array in WASM: 1.447ms
1000000
Sum large array in JS: 13.048ms
1000000
Sum large array in WASM: 1.225ms
```

- ... is like 12 years of hardware improvements just down the drain it like
  this.

### References

- [Make Your SvelteKit Code 10x Faster With Rust and WebAssembly](https://www.youtube.com/watch?v=Vn2bIv_J_UE)
- [sveltekit-rust-webassembly](https://github.com/svelterust/sveltekit-rust-webassembly)
