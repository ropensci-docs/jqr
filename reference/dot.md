# dot and related functions

dot and related functions

## Usage

``` r
dot(.data)

dot_(.data, dots = ".")

dotstr(.data, ...)

dotstr_(.data, ..., .dots)
```

## Arguments

- .data:

  input. This can be JSON input, or an object of class `jqr` that has
  JSON and query params combined, which is passed from function to
  function when using the jqr DSL.

- dots:

  dots

- ...:

  Comma separated list of unquoted variable names

- .dots:

  Used to work around non-standard evaluation

## Examples

``` r
str <- '[{"name":"JSON", "good":true}, {"name":"XML", "good":false}]'
str %>% dot
#> [
#>     {
#>         "name": "JSON",
#>         "good": true
#>     },
#>     {
#>         "name": "XML",
#>         "good": false
#>     }
#> ]
str %>% index %>% dotstr(name)
#> [
#>     "JSON",
#>     "XML"
#> ]
'{"foo": 5, "bar": 8}' %>% dot
#> {
#>     "foo": 5,
#>     "bar": 8
#> }
'{"foo": 5, "bar": 8}' %>% dotstr(foo)
#> 5
'{"foo": {"bar": 8}}' %>% dotstr(foo.bar)
#> 8
```
