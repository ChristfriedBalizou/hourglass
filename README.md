# tzdata-rs

Timezone library for the Rust programming language ([doc](https://maximelenoir.github.io/tzdata-rs/tzdata))

[![Build Status](https://travis-ci.org/maximelenoir/tzdata-rs.svg?branch=master)](https://travis-ci.org/maximelenoir/tzdata-rs)
[![Crate Version](https://img.shields.io/crates/v/tzdata.svg)](https://crates.io/crates/tzdata)

## Usage

Add the following in your `Cargo.toml`:

```toml
[dependencies]
tzdata = "0.1"
```

And put this in your crate root:

```rust
extern crate tzdata;
```
## Example

The library provides basic support for timezone conversion.

```rust
let now = now_utc();
for tzname in &["Europe/Paris", "America/New_York", "Asia/Seoul"] {
    let tz = Timezone::new(tzname).unwrap();
    let now = tz.localize(now);
    println!("now is {} in {}", now.rfc3339(), tz.name);
}
```