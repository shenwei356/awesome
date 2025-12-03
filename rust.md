# Rust


## Book

Basic

- [Rust Book](https://doc.rust-lang.org/stable/book/)
- [Comprehensive Rust](https://google.github.io/comprehensive-rust/)
- [Learning Rust by Writing a Command Line App in 15 Minutes](https://rust-cli.github.io/book/tutorial/index.html)
- [Rust Language Cheat Sheet](https://cheats.rs/)

Best practice

- [Rust Cookbook](https://rust-lang-nursery.github.io/rust-cookbook/)
- [Rust Design Patterns](https://rust-unofficial.github.io/patterns/)
- [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/)
- [Pragmatic Rust Guidelines](https://microsoft.github.io/rust-guidelines/guidelines/index.html)

Performance

- [The Rust Performance Book](https://nnethercote.github.io/perf-book/)
- [Asynchronous Programming in Rust](https://rust-lang.github.io/async-book/)
- [Recipes for avoiding bounds checks in Rust, without unsafe!](https://github.com/Shnatsel/bounds-check-cookbook/)

## Online practice

- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)
- https://rustfinity.com/


## Packages

General

- Std: https://doc.rust-lang.org/std/index.html
    - [Primitive Types](https://doc.rust-lang.org/std/#primitives)
    - [Enum Option](https://doc.rust-lang.org/std/option/enum.Option.html), [Enum Result](https://doc.rust-lang.org/std/result/enum.Result.html), [Trait Error](https://doc.rust-lang.org/std/error/trait.Error.html)
    - [Struct String](https://doc.rust-lang.org/std/string/struct.String.html#method.starts_with), [Primitive Type str](https://doc.rust-lang.org/stable/std/primitive.str.html)
- Error: [thiserror](https://github.com/dtolnay/thiserror) or [anyhow](https://github.com/dtolnay/anyhow)
- Regular expression: [regex](https://github.com/rust-lang/regex)
- String search: [memchr](https://github.com/BurntSushi/memchr)

Computation

- N-dimensional array: [ndarray](https://github.com/rust-ndarray/ndarray)
- Data Frame: [polars](https://github.com/pola-rs/polars)

CLI

- CLI: [clap](https://github.com/clap-rs/clap)
- Log: [log](https://docs.rs/log/latest/log/) and [fern](https://docs.rs/fern/latest/fern/)
- Color: [colored](https://github.com/colored-rs/colored) or [owo-colors](https://github.com/owo-colors/owo-colors)
- CPU/Memory: [sysinfo](https://docs.rs/sysinfo/latest/sysinfo/index.html)
- Progress bar: [indicatif](https://crates.io/crates/indicatif)
- Signal: [CtrlC](https://crates.io/crates/ctrlc)

IO

- [byteorder](https://github.com/BurntSushi/byteorder)
- Dir walk: [walkdir](https://github.com/BurntSushi/walkdir) or [ignore](https://github.com/BurntSushi/ripgrep/tree/master/crates/ignore) for high performance.
- Serialization: [bincode](https://docs.rs/bincode/latest/bincode/)

Performance

- [crossbeam - Tools for concurrent programming](https://github.com/crossbeam-rs/crossbeam)
- Data parallelism: [rayon](https://github.com/rayon-rs/rayon)
- Asynchronous programming: [tokio](https://github.com/tokio-rs/tokio)
- Benchmarking: [hyperfine](https://github.com/sharkdp/hyperfine)

Bioinformatics

- Sequence parser: [seq_io](https://github.com/markschl/seq_io), [**needletail**](https://github.com/onecodex/needletail), [noodles](https://github.com/zaeleus/noodles)
