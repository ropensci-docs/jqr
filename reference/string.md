# Give back a character string

Give back a character string

## Usage

``` r
string(.data)
```

## Arguments

- .data:

  (list) input, using higher level interface

## See also

[`peek`](https://docs.ropensci.org/jqr/reference/peek.md)

## Examples

``` r
'{"a": 7}' %>% do(.a + 1) %>% string
#> [1] "{\"a\": 7}"
'[8,3,null,6]' %>% sortj %>% string
#> [1] "[8,3,null,6]"
```
