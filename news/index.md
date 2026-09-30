# Changelog

## jqr 1.4.0

CRAN release: 2024-12-16

- Windows: use libjq from Rtools if found

## jqr 1.3.4

CRAN release: 2024-08-16

- Remove problematic link anchor

## jqr 1.3.3

CRAN release: 2023-12-04

- Fix printf warning for cran

## jqr 1.3.2

CRAN release: 2023-11-20

- Fix shell script for cross compilation

## jqr 1.3.0

CRAN release: 2023-09-20

- Windows: update to libjq 1.7
- Fix test for libjq 1.7 on Debian

## jqr 1.2.3

CRAN release: 2022-03-10

- New maintainer

## jqr 1.2.2

CRAN release: 2021-11-08

- fix a failing test

## jqr 1.2.1

CRAN release: 2021-05-06

- Windows: update to libjq 1.6

## jqr 1.2.0

CRAN release: 2020-11-13

#### MINOR IMPROVEMENTS

- fix to internal method `pipeline_on_exit()` for compatibility with the
  upcoming magrittr v2.0
  ([\#82](https://github.com/ropensci/jqr/issues/82)) thanks
  [@lionel-](https://github.com/lionel-) !
- [`jq()`](https://docs.ropensci.org/jqr/reference/jq.md) errors better
  now when any NA class passed to it
  ([\#78](https://github.com/ropensci/jqr/issues/78))

## jqr 1.1.0

CRAN release: 2018-10-22

#### NEW FEATURES

- All functions now support connection objects (file paths, urls) as
  input types for streaming. see new methods `jqr_feed` and `jqr_new`
  ([\#55](https://github.com/ropensci/jqr/issues/55))
- fix [`jq()`](https://docs.ropensci.org/jqr/reference/jq.md) to be able
  to accept `json` objects as input
  ([\#62](https://github.com/ropensci/jqr/issues/62))
- gains new functions
  [`build_array()`](https://docs.ropensci.org/jqr/reference/build.md)/[`build_array_()`](https://docs.ropensci.org/jqr/reference/build.md)
  and
  [`build_object()`](https://docs.ropensci.org/jqr/reference/build.md)/[`build_object_()`](https://docs.ropensci.org/jqr/reference/build.md)
  for building arrays and objects, respectively. and
  [`select()`](https://docs.ropensci.org/jqr/reference/select.md)
  changes to only do filtering (instead of also doing construction) to
  match jq behavior ([\#66](https://github.com/ropensci/jqr/issues/66))
  ([\#67](https://github.com/ropensci/jqr/issues/67))
- [`jq_flags()`](https://docs.ropensci.org/jqr/reference/jq_flags.md)
  gains parameters `stream` and `seq`

#### MINOR IMPROVEMENTS

- fixed `strncpy` call in `src/jqr.c`
  ([\#75](https://github.com/ropensci/jqr/issues/75))

#### BUG FIXES

- fix [`select()`](https://docs.ropensci.org/jqr/reference/select.md) to
  handle operators other than `=`
  ([\#65](https://github.com/ropensci/jqr/issues/65))
  ([\#67](https://github.com/ropensci/jqr/issues/67))

## jqr 1.0.0

CRAN release: 2017-09-28

- Unbundle jq: the libjq library and headers are now available on all
  major platforms. See <https://jqlang.github.io/jq/download/> for
  details. ([\#59](https://github.com/ropensci/jqr/issues/59))
- Removed a few authors due to n longer including jq in package
- No longer linking to BH and Rcpp. No longer using/importing Rcpp
- Use `R_registerRoutines` and `R_useDynamicSymbols` as required for
  packages with compiled code.
  ([\#57](https://github.com/ropensci/jqr/issues/57))
- Internal dataset changed name from “githubcommits” to “commits”
- Multiple JSON inputs now supported (see
  [\#53](https://github.com/ropensci/jqr/issues/53))

## jqr 0.2.4

CRAN release: 2016-07-29

#### Fixes for CRAN

- Fixed the ASAN/valgrind problem (use after free) in jqr.cpp

## jqr 0.2.3

CRAN release: 2016-05-10

#### Fixes for CRAN

- Fixes in v0.2.2 actually applied in this version

## jqr 0.2.2

CRAN release: 2016-05-03

#### Fixes for CRAN

- Backport ec7c3cf (<https://git.io/vwCFS>)
- Backport eb2fc1d (<https://git.io/vwCF5>)
- Port 15c4a7f (<https://git.io/vw1vM>)

## jqr 0.2.0

CRAN release: 2016-03-23

### NEW FEATURES

- Released to CRAN.
