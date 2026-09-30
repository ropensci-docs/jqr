# JQ Streaming API

Low level JQ API. First create a program using a \`query\` and \`flags\`
and then feed pieces of data.

## Usage

``` r
jqr_new(query, flags = jq_flags())

jqr_feed(jqr_program, json, unlist = TRUE, finalize = FALSE)
```

## Arguments

- query:

  string with a valid jq program

- flags:

  See [`jq_flags`](https://docs.ropensci.org/jqr/reference/jq_flags.md)

- jqr_program:

  object returned by \[jqr_new\]

- json:

  character vector with json data. If the JSON object is incomplete, you
  must set \`finalize\` to \`FALSE\` otherwise you get an error.

- unlist:

  if \`TRUE\` returns a single character vector with all output for each
  each string in \`json\` input

- finalize:

  completes the parsing and verifies that the JSON string is valid. Set
  this to \`TRUE\` when feeding the final piece of data.

## Examples

``` r
program <- jqr_new(".[]")
jqr_feed(program, c("[123, 456]", "[77, 88, 99]"))
#> [1] "123" "456" "77"  "88"  "99" 
jqr_feed(program, c("[41, 234]"))
#> [1] "41"  "234"
jqr_feed(program, "", finalize = TRUE)
#> character(0)
```
