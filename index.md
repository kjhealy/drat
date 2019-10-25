---
layout: default
title: Drat Repository for R Data Packages on github.com/kjhealy
---


## What is this

This repository contains the latest stable builds of [my](https://kieranhealy.org) R packages that aren't suitable for CRAN. At present, that's the following packages: 

-`cavax`. [Vaccination Exemptions in California Kindergartens](https://kjhealy.github.io/cavax/).
- `congress`. [US Congressional Representatives 1945-2019](https://kjhealy.github.io/congress/).
- `gssr`. [Provides data files from the General Social Survey](https://kjhealy.github.io/gssr/).
- `nycdogs`. [Datasets on dog licenses, bites, and locations in New York City](https://kjhealy.github.io/nycdogs/). 

These are all data packages, which makes them unsuitable for hosting CRAN. The benefit of a `drat` archive like this is that you can install and upgrade non-CRAN packages directly from R using the standard `install.packages()` and `update.packages()` functions. E.g.,

```{r}
if (!require("drat")) {
    install.packages("drat")
    library("drat")
}
drat::addRepo("kjhealy")

install.packages("nycdogs")
```

To ensure that this repository is always available to you in R, you can add the following line to your `.Rprofile` or `.Rprofile.site` file:

```{r}
drat::addRepo("kjhealy")
```

This will allow you to use, e.g., `install.packages("nycdogs")` or `update.packages("nycdogs")`.

## Learn More

For more on using drat (a package by Dirk Eddelbuettel), see [this vignette](http://eddelbuettel.github.io/drat/DratForPackageUsers.html). 
