# Execute a query with jq

`jq` is meant to work with the high level interface in this package.
`jq` also provides access to the low level interface in which you can
use jq query strings just as you would on the command line. Output gets
class of json, and pretty prints to the console for easier viewing.
`jqr` doesn't do pretty printing.

## Usage

``` r
jq(x, ...)

# S3 method for class 'jqr'
jq(x, ...)

# S3 method for class 'character'
jq(x, ..., flags = jq_flags())

# S3 method for class 'json'
jq(x, ..., flags = jq_flags())

# S3 method for class 'connection'
jq(x, ..., flags = jq_flags(), out = NULL)
```

## Arguments

- x:

  `json` object or character string with json data. this can be one or
  more valid json objects

- ...:

  character specification of jq query. Each element in `...` will be
  combined with " \| ", which is convenient for long queries.

- flags:

  See [`jq_flags`](https://docs.ropensci.org/jqr/reference/jq_flags.md)

- out:

  a filename, callback function, connection object to stream output. Set
  to \`NULL\` to buffer all output and return a character vector.

## See also

[`peek`](https://docs.ropensci.org/jqr/reference/peek.md)

## Examples

``` r
'{"a": 7}' %>%  do(.a + 1)
#> 8
'[8,3,null,6]' %>% sortj
#> [
#>     null,
#>     3,
#>     6,
#>     8
#> ]

x <- '[{"message": "hello", "name": "jenn"},
  {"message": "world", "name": "beth"}]'
jq(index(x))
#> [
#>     {
#>         "message": "hello",
#>         "name": "jenn"
#>     },
#>     {
#>         "message": "world",
#>         "name": "beth"
#>     }
#> ]

jq('{"a": 7, "b": 4}', 'keys')
#> [
#>     "a",
#>     "b"
#> ]
jq('[8,3,null,6]', 'sort')
#> [
#>     null,
#>     3,
#>     6,
#>     8
#> ]

# many json inputs
jq(c("[123, 456]", "[77, 88, 99]", "[41]"), ".[]")
#> [
#>     123,
#>     456,
#>     77,
#>     88,
#>     99,
#>     41
#> ]
# Stream from connection
tmp <- tempfile()
writeLines(c("[123, 456]", "[77, 88, 99]", "[41]"), tmp)
jq(file(tmp), ".[]")
#> [
#>     123,
#>     456,
#>     77,
#>     88,
#>     99,
#>     41
#> ]

if (FALSE) { # \dontrun{
# from a url
x <- 'http://jeroen.github.io/data/diamonds.json'
jq(url(x), ".[]")

# from a file
file <- file.path(tempdir(), "diamonds_nd.json")
download.file(x, destfile = file)
jq(file(file), ".carat")
jq(file(file), "select(.carat > 1.5)")
jq(file(file), 'select(.carat > 4 and .cut == "Fair")')
} # }
```
