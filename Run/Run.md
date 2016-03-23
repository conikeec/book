# rustinr

`rustinr` is a R package to help user generate the basic struture of a Rust-R package and source Rust script in R.

## Rust Function in R Console

`rust()` is a R function to create Rust function in R console interatively.

If there is a Rust function:

```rust
// #[rustr_export]
pub fn say_hi() -> String{
	"Hello World".into()
}
```

Just mark it with `// #[rustr_export]`, and put this function in `rust()`

```r
library(rustinr)

rust(code = '
// #[rustr_export]
pub fn say_hi() -> String{
	"Hello World".into()
}
')
```

and then you can call `say_hi` in R.

```r
say_hi()
#> [1] "Hello World"

say_hi
#> function(){ .Call('qxJFNNnLVpqF_say_hi',PACKAGE = 'qxJFNNnLVpqF')}
``` 

Here is another example：

```r
rust(code = '
// #[rustr_export]
pub fn fib_rs(x:u64)-> u64{
    if x == 0 { return 0 };
    if x == 1 { return 1 };
    return fib_rs(x - 1) + fib_rs(x - 2);
}')

fib_rs(10L)
#> [1] 55
```

For more example, you can also checkout https://gallery.rustr.org



