# Drat Repository for github.com/kjhealy

This contains the latest stable builds of my R packages that aren't suitable for CRAN. At present, that's the `gssr` package, which has too much data and too few functions to be a CRAN candidate. 
The benefit of a `drat` archive like this is that you can install and upgrade non-CRAN packages directly from R using the standard `install.packages()` and `update.packages()` functions. E.g.,

```{r}
if (!require("drat")) {
    install.packages("drat")
    library("drat")
}
drat::addRepo("kjhealy")
install.packages("gssr")
```

For more on using drat (a package by Dirk Eddelbuettel), see [this vignette](http://eddelbuettel.github.io/drat/DratForPackageUsers.html). 
