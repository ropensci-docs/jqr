# Sort and related

Sort and related

## Usage

``` r
sortj(.data, ...)

sortj_(.data, ..., .dots)

reverse(.data)
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
# sort
'[8,3,null,6]' %>% sortj
#> [
#>     null,
#>     3,
#>     6,
#>     8
#> ]
'[{"foo":4, "bar":10}, {"foo":3, "bar":100}, {"foo":2, "bar":1}]' %>%
  sortj(foo)
#> [
#>     {
#>         "foo": 2,
#>         "bar": 1
#>     },
#>     {
#>         "foo": 3,
#>         "bar": 100
#>     },
#>     {
#>         "foo": 4,
#>         "bar": 10
#>     }
#> ]

# reverse order
'[1,2,3,4]' %>% reverse
#> [
#>     4,
#>     3,
#>     2,
#>     1
#> ]

# many JSON inputs
'[{"foo":7}, {"foo":4}] [{"foo":300}, {"foo":1}] [{"foo":2}, {"foo":1}]' %>%
  sortj(foo)
#> [
#>     [
#>         {
#>             "foo": 4
#>         },
#>         {
#>             "foo": 7
#>         }
#>     ],
#>     [
#>         {
#>             "foo": 1
#>         },
#>         {
#>             "foo": 300
#>         }
#>     ],
#>     [
#>         {
#>             "foo": 1
#>         },
#>         {
#>             "foo": 2
#>         }
#>     ]
#> ]

'[1,2,3,4] [10,20,30,40] [100,200,300,4000]' %>%
  reverse
#> [
#>     [
#>         4,
#>         3,
#>         2,
#>         1
#>     ],
#>     [
#>         40,
#>         30,
#>         20,
#>         10
#>     ],
#>     [
#>         4000,
#>         300,
#>         200,
#>         100
#>     ]
#> ]
```
