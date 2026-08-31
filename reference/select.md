# Select - filtering

The function `select(foo)` produces its input unchanged if `foo` returns
TRUE for that input, and produces no output otherwise

## Usage

``` r
select(.data, ...)

select_(.data, ..., .dots)
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

## Note

this function has changed what it does dramatically. we were using this
function for object construction, which is now done with
[`build_object`](https://docs.ropensci.org/jqr/reference/build.md)

## Examples

``` r
jq('[1,5,3,0,7]', 'map(select(. >= 2))')
#> [
#>     5,
#>     3,
#>     7
#> ]
'[1,5,3,0,7]' %>% map(select(. >= 2)) 
#> [
#>     5,
#>     3,
#>     7
#> ]


'{"foo": 4, "bar": 7}' %>% select(.foo == 4)
#> {
#>     "foo": 4,
#>     "bar": 7
#> }
'{"foo": 5, "bar": 7} {"foo": 4, "bar": 7}' %>% select(.foo == 4)
#> {
#>     "foo": 4,
#>     "bar": 7
#> }
'[{"foo": 5, "bar": 7}, {"foo": 4, "bar": 7}]' %>% index() %>% 
  select(.foo == 4)
#> {
#>     "foo": 4,
#>     "bar": 7
#> }
'{"foo": 4, "bar": 7} {"foo": 5, "bar": 7} {"foo": 8, "bar": 7}' %>% 
  select(.foo < 6)
#> [
#>     {
#>         "foo": 4,
#>         "bar": 7
#>     },
#>     {
#>         "foo": 5,
#>         "bar": 7
#>     }
#> ]

x <- '{"foo": 4, "bar": 2} {"foo": 5, "bar": 4} {"foo": 8, "bar": 12}'
jq(x, 'select((.foo < 6) and (.bar > 3))')
#> {
#>     "foo": 5,
#>     "bar": 4
#> }
jq(x, 'select((.foo < 6) or (.bar > 3))')
#> [
#>     {
#>         "foo": 4,
#>         "bar": 2
#>     },
#>     {
#>         "foo": 5,
#>         "bar": 4
#>     },
#>     {
#>         "foo": 8,
#>         "bar": 12
#>     }
#> ]
x %>% select((.foo < 6) && (.bar > 3))
#> {
#>     "foo": 5,
#>     "bar": 4
#> }
x %>% select((.foo < 6) || (.bar > 3))
#> [
#>     {
#>         "foo": 4,
#>         "bar": 2
#>     },
#>     {
#>         "foo": 5,
#>         "bar": 4
#>     },
#>     {
#>         "foo": 8,
#>         "bar": 12
#>     }
#> ]

x <- '[{"foo": 5, "bar": 7}, {"foo": 4, "bar": 7}, {"foo": 4, "bar": 9}]'
jq(x, '.[] | select(.foo == 4) | {user: .bar}')
#> [
#>     {
#>         "user": 7
#>     },
#>     {
#>         "user": 9
#>     }
#> ]
x %>% index() %>% select(.foo == 4) %>% build_object(user = .bar)
#> [
#>     {
#>         "user": 7
#>     },
#>     {
#>         "user": 9
#>     }
#> ]
```
