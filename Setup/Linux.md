## Mac

#### 1. Get R

Get [R](), I think you know how. :)

#### 2. Get Rust with GNU ABI 

```
curl -sSf https://static.rust-lang.org/rustup.sh | sh
```

One of Stable, Beta, or Nightly version of Rust is OK. 

You can put Rust installation in path or set `CARGO_HOME` environment varible to the path of `cargo`.

#### 3. Get rustinr

Run This in R:

```r
install.package("devtools")
devtools::install_github("rustr/rustinr")
```

And we are ready to Play!

Run this in R console.

```r
rust(code ='
// #[rustr_export]
pub fn say_hi() -> String{
	"Hello World".into()
}
')

say_hi()
#> [1] "Hello World"
```
