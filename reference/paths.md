# Outputs paths to all the elements in its input

Outputs paths to all the elements in its input

## Usage

``` r
paths(.data)
```

## Arguments

- .data:

  input

## Examples

``` r
'[1,[[],{"a":2}]]' %>% paths
#> [
#>     [
#>         0
#>     ],
#>     [
#>         1
#>     ],
#>     [
#>         1,
#>         0
#>     ],
#>     [
#>         1,
#>         1
#>     ],
#>     [
#>         1,
#>         1,
#>         "a"
#>     ]
#> ]
'[{"name":"JSON", "good":true}, {"name":"XML", "good":false}]' %>% paths
#> [
#>     [
#>         0
#>     ],
#>     [
#>         0,
#>         "name"
#>     ],
#>     [
#>         0,
#>         "good"
#>     ],
#>     [
#>         1
#>     ],
#>     [
#>         1,
#>         "name"
#>     ],
#>     [
#>         1,
#>         "good"
#>     ]
#> ]
```
