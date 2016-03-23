## Summary

### 1. rust()

```r
rust(path = "Rust file", code = "Rust code", depend = "Optional Cargo TOML dependency")
``` 

Source Rust file or code in R console.

### 2. rustr_init()

```r
rustr_init(name = "R package name", path = "Pacakage path")
```

Init a Rust-R package struture. It is similar to `package.skeleton()`.

### 3. headr()

```r
headr()
```

Give you the header of the `lib.rs` for Rust Library to get started with R.

### 4. rustrize()

```r
rustrize(path = ".")
```

Generate R function for Rust function in a R package. It is similar to `compileAttributes()` in `Rcpp`.

