## Windows

#### 1. Get R

Get [R > 3.3.0](https://cran.r-project.org/bin/windows/base/R-devel-493-win.exe) build with GCC 4.9 and [Rtools 3.3](https://cran.r-project.org/bin/windows/Rtools/Rtools33.exe)

#### 2. Get Rust with GNU ABI 

Checkout https://www.rust-lang.org/downloads.html

One of Stable, Beta, or Nightly version of Rust is OK. 

You can put Rust installation in path or set `CARGO_HOME` environment varible to the path of `cargo.exe`. 

If you want to build multi-arch R package, make sure you install both 64bit and 32bit Rust standard library, for example `C:\Rust\lib\rustlib\i686-pc-windows-gnu` and `C:\Rust\lib\rustlib\x86_64-pc-windows-gnu`

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
