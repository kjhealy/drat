---
layout: default
title: R Data Packages on github.com/kjhealy
---


## Where am I? What is this?

This repository contains the latest stable builds of [my](https://kieranhealy.org) R packages that aren't suitable for CRAN. At present, that's the following packages: 

- `cavax`. [Vaccination Exemptions in California Kindergartens](https://kjhealy.github.io/cavax/).
- `congress`. [US Congressional Representatives 1945-2019](https://kjhealy.github.io/congress/).
- `covdata`. [COVID-19 case and fatality data for countries and US states](https://kjhealy.github.io/covdata/).
- `gssr`. [Provides data files from the General Social Survey](https://kjhealy.github.io/gssr/).
- `nycdogs`. [Datasets on dog licenses, bites, and locations in New York City](https://kjhealy.github.io/nycdogs/). 
- `ukelection2019`. [Candidate-level vote data within constituencies for the 2019 UK General Election](https://kjhealy.github.io/ukelection2019/). 
- `uscenpops`. [Annual decennial and intercensal estimates of the US Population by year of age and sex, from 1900 to 2019](https://kjhealy.github.io/uscenpops/)

These are all data packages, which is what makes them unsuitable for hosting CRAN. The benefit of a `drat` archive like this is that you can install and upgrade non-CRAN packages directly from R using the standard `install.packages()` and `update.packages()` functions. What you need to do is, install `drat` and then use it to make R aware of this repository. Like so:

```{r}
if (!require("drat")) {
    install.packages("drat")
    library("drat")
}
drat::addRepo("kjhealy")

```

Once you've done that, you can then do this, for example:

```{r}

install.packages("nycdogs")
```

To ensure that this drat repository is always available to you in R, you can add the following line to your `.Rprofile` or `.Rprofile.site` file:

```{r}
drat::addRepo("kjhealy")
```

This will allow you to use, e.g., `install.packages("nycdogs")` or `update.packages("nycdogs")`.

## Learn More

For more on using drat (a package by Dirk Eddelbuettel), see [this vignette](http://eddelbuettel.github.io/drat/DratForPackageUsers.html). 
