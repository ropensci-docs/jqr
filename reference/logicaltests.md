# Logical tests

Logical tests

## Usage

``` r
allj(.data)

anyj(.data)
```

## Arguments

- .data:

  input. This can be JSON input, or an object of class `jqr` that has
  JSON and query params combined, which is passed from function to
  function when using the jqr DSL.

## Examples

``` r
# any
'[true, false]' %>% anyj
#> true
'[false, false]' %>% anyj
#> false
'[]' %>% anyj
#> false

# all
'[true, false]' %>% allj
#> false
'[true, true]' %>% allj
#> true
'[]' %>% allj
#> true

## many JSON inputs
'[true, false] [true, true] [false, false]' %>% anyj
#> [
#>     true,
#>     true,
#>     false
#> ]
'[true, false] [true, true] [false, false]' %>% allj
#> [
#>     false,
#>     true,
#>     false
#> ]
```
