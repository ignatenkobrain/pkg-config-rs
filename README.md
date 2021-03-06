# pkg-config-rs

[![Build Status](https://travis-ci.org/alexcrichton/pkg-config-rs.svg?branch=master)](https://travis-ci.org/alexcrichton/pkg-config-rs)

[Documentation](https://docs.rs/pkg-config)

A simple library meant to be used as a build dependency with Cargo packages in
order to use the system `pkg-config` tool (if available) to determine where a
library is located.

You can use this crate directly to probe for specific libraries, or use
[metadeps](https://github.com/joshtriplett/metadeps) to declare all your
`pkg-config` dependencies in `Cargo.toml`.

# Example

Find the system library named `foo`, with minimum version 1.2.3:

```rust
extern crate pkg_config;

fn main() {
    pkg_config::Config::new().atleast_version("1.2.3").probe("foo").unwrap();
}
```

Find the system library named `foo`, with no version requirement (not
recommended):

```rust
extern crate pkg_config;

fn main() {
    pkg_config::probe_library("foo").unwrap();
}
```

# License

This project is licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in Serde by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.
