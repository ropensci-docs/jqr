# Operations on keys, or by keys

`keys` takes no input, and retrieves keys. `del` deletes provided keys.
`haskey` checks if a json string has a key, or the input array has an
element at the given index.

## Usage

``` r
keys(.data)

del(.data, ...)

del_(.data, ..., .dots)

haskey(.data, ...)

haskey_(.data, ..., .dots)
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
# get keys
str <- '{"foo": 5, "bar": 7}'
jq(str, "keys")
#> [
#>     "bar",
#>     "foo"
#> ]
str %>% keys()
#> [
#>     "bar",
#>     "foo"
#> ]

# delete by key name
jq(str, "del(.bar)")
#> {
#>     "foo": 5
#> }
str %>% del(bar)
#> {
#>     "foo": 5
#> }

# check for key existence
str3 <- '[[0,1], ["a","b","c"]]'
jq(str3, "map(has(2))")
#> [
#>     false,
#>     true
#> ]
str3 %>% haskey(2)
#> [
#>     false,
#>     true
#> ]
jq(str3, "map(has(1,2))")
#> [
#>     true,
#>     false,
#>     true,
#>     true
#> ]
str3 %>% haskey(1,2)
#> [
#>     true,
#>     false,
#>     true,
#>     true
#> ]

## many JSON inputs
'{"foo": 5, "bar": 7} {"hello": 5, "world": 7}' %>% keys
#> [
#>     [
#>         "bar",
#>         "foo"
#>     ],
#>     [
#>         "hello",
#>         "world"
#>     ]
#> ]
'{"foo": 5, "bar": 7} {"hello": 5, "bar": 7}' %>% del(bar)
#> [
#>     {
#>         "foo": 5
#>     },
#>     {
#>         "hello": 5
#>     }
#> ]
```
