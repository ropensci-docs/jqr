# Flags for use with jq

The `flags` function is provided for the high-level DSL approach,
whereas the `jq_flags` function is used to provide the low-level `jq`
with the appropriate flags.

## Usage

``` r
jq_flags(
  pretty = FALSE,
  ascii = FALSE,
  color = FALSE,
  sorted = FALSE,
  stream = FALSE,
  seq = FALSE
)

flags(
  .data,
  pretty = FALSE,
  ascii = FALSE,
  color = FALSE,
  sorted = FALSE,
  stream = FALSE,
  seq = FALSE
)
```

## Arguments

- pretty:

  Pretty print the json (different to jsonlite's pretty printing).

- ascii:

  Force jq to produce pure ASCII output with non-ASCII characters
  replaced by equivalent escape sequences.

- color:

  Add ANSI escape sequences for coloured output

- sorted:

  Output fields of each object with keys in sorted order

- stream:

  Parse the input in streaming fashion, outputing arrays of path and
  leaf values like `jq --stream` command line.

- seq:

  Use the application/json-seq MIME type scheme for separating JSON like
  the `jq --seq` command line.

- .data:

  A `jqr` object.

## Examples

``` r
'{"a": 7, "z":0, "b": 4}' %>% flags(sorted = TRUE)
#> {
#>     "a": 7,
#>     "b": 4,
#>     "z": 0
#> }
'{"a": 7, "z":0, "b": 4}' %>% dot %>% flags(sorted = TRUE)
#> {
#>     "a": 7,
#>     "b": 4,
#>     "z": 0
#> }
jq('{"a": 7, "z":0, "b": 4}', ".") %>% flags(sorted = TRUE)
#> {
#>     "a": 7,
#>     "b": 4,
#>     "z": 0
#> }
jq('{"a": 7, "z":0, "b": 4}', ".", flags = jq_flags(sorted = TRUE))
#> {
#>     "a": 7,
#>     "b": 4,
#>     "z": 0
#> }
```
