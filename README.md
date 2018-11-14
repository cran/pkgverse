
<!-- README.md is generated from README.Rmd. Please edit that file -->

# pkgverse <img src="man/figures/logo.png" width="160px" align="right" />

[![lifecycle](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)

Create your own universe of packages à la
[tidyverse](https://github.com/tidyverse/tidyverse).

## Installation

You can install the dev version of pkgverse from Github with:

``` r
devtools::install_github("mkearney/pkgverse")
```

## Example

Create @hrbrmstr’s [tidyweb](https://github.com/hrbrmstr/tidyweb).

``` r
## vector of pkgs
tidyweb <- c("curl", "jsonlite", "httr", "xml2", "rvest", "purrr", "dplyr",
  "stringi", "gdns", "urltools", "iptools", "seleniumPipes", "webdriver",
  "HARtools", "xslt", "V8", "webreadr", "openssl", "splashr")

## create packages dir
dir.create("~/packages")

## create tidyweb pkgverse
pkgverse("tidyweb", tidyweb,
  keep = "~/packages",
  use = c("readme_rmd", "rstudio", "testthat", "mit_license", "git"),
  install_if = TRUE
)
```

Now load your pkg universe:

``` r
## load tidyweb
library(tidyweb)
── Attaching packages ───────────────────────────────────────────────────────────────────────── tidyweb 0.0.1 ──
✔ curl          3.2       ✔ iptools       0.4.0
✔ jsonlite      1.5       ✔ seleniumPipes 0.3.7
✔ httr          1.3.1     ✔ webdriver     1.0.5
✔ xml2          1.2.0     ✔ HARtools      0.0.5
✔ rvest         0.3.2     ✔ xslt          1.3  
✔ purrr         0.2.5     ✔ V8            1.5  
✔ dplyr         0.7.5     ✔ webreadr      0.4.0
✔ stringi       1.2.2     ✔ openssl       1.0.1
✔ gdns          0.2.1     ✔ splashr       0.4.1
✔ urltools      1.7.0     
── Conflicts ──────────────────────────────────────────────────────────────────────────── tidyweb_conflicts() ──
✖ seleniumPipes::back() masks rvest::back()
✖ dplyr::filter()       masks stats::filter()
✖ purrr::flatten()      masks jsonlite::flatten()
✖ httr::handle_reset()  masks curl::handle_reset()
✖ dplyr::lag()          masks stats::lag()
✖ purrr::pluck()        masks rvest::pluck()
✖ magrittr::set_names() masks purrr::set_names()
✖ urltools::url_parse() masks xml2::url_parse()
```
