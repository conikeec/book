## Mac

#### 1. Get R

Get [R](https://cran.r-project.org/bin/macosx/).

#### 2. Get Rust with GNU ABI 

Checkout https://www.rust-lang.org/downloads.html

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

#### 4. Get Xcode Command Line Tools

Open Terminal, and run `git` or `clang`, It may show a message to get you started. 

Or you can check [this great guide](http://rud.is/b/2015/10/20/installing-r-on-os-x/).

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
