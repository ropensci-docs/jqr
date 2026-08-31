# Peek at a query

Prints the query resulting from `jq` all in one character string just as
you would execute it on the command line. Output gets class of json, and
pretty prints to the console for easier viewing.

## Usage

``` r
peek(.data)
```

## Arguments

- .data:

  (list) input, using higher level interface

## See also

[`jq`](https://docs.ropensci.org/jqr/reference/jq.md).

## Examples

``` r
'{"a": 7}' %>% do(.a + 1) %>% peek
#> <jq query>
#>   query: .a + 1
'[8,3,null,6]' %>% sortj %>% peek
#> <jq query>
#>   query: sort
```
