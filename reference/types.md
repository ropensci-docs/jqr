# Types and related functions

Types and related functions

## Usage

``` r
types(.data)

type(.data, ...)

type_(.data, ..., .dots)
```

## Arguments

- .data:

  input. This can be JSON input, or an object of class `jqr` that has
  JSON and query params combined, which is passed from function to
  function when using the jqr DSL.

- ...:

  Comma separated list of unquoted variable names

- .dots:

  Used to work around non-standard evaluation

- dots:

  dots

## Examples

``` r
# get type information for each element
jq('[0, false, [], {}, null, "hello"]', 'map(type)')
#> [
#>     "number",
#>     "boolean",
#>     "array",
#>     "object",
#>     "null",
#>     "string"
#> ]
'[0, false, [], {}, null, "hello"]' %>% types
#> [
#>     "number",
#>     "boolean",
#>     "array",
#>     "object",
#>     "null",
#>     "string"
#> ]
'[0, false, [], {}, null, "hello", true, [1,2,3]]' %>% types
#> [
#>     "number",
#>     "boolean",
#>     "array",
#>     "object",
#>     "null",
#>     "string",
#>     "boolean",
#>     "array"
#> ]

# select elements by type
jq('[0, false, [], {}, null, "hello"]', '.[] | numbers,booleans')
#> [
#>     0,
#>     false
#> ]
'[0, false, [], {}, null, "hello"]' %>% index() %>% type(booleans)
#> false
```
