# Format strings and escaping

Format strings and escaping

## Usage

``` r
at(.data, ...)

at_(.data, ..., .dots)
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
x <- '{"user":"jqlang","titles":["JQ Primer", "More JQ"]}'
x %>% at(base64) %>% peek
#> <jq query>
#>   query: @base64
x %>% at(base64)
#> "eyJ1c2VyIjoianFsYW5nIiwidGl0bGVzIjpbIkpRIFByaW1lciIsIk1vcmUgSlEiXX0="
x %>% index() %>% at(base64)
#> [
#>     "anFsYW5n",
#>     "WyJKUSBQcmltZXIiLCJNb3JlIEpRIl0="
#> ]

y <- '["fo", "foo", "barfoo", "foobar", "barfoob"]'
y %>% index() %>% at(base64)
#> [
#>     "Zm8=",
#>     "Zm9v",
#>     "YmFyZm9v",
#>     "Zm9vYmFy",
#>     "YmFyZm9vYg=="
#> ]

## prepare for shell use
y %>% index() %>% at(sh)
#> [
#>     "'fo'",
#>     "'foo'",
#>     "'barfoo'",
#>     "'foobar'",
#>     "'barfoob'"
#> ]

## rendered as csv with double quotes
z <- '[1, 2, 3, "a"]'
z %>% at(csv)
#> "1,2,3,\"a\""

## rendered as csv with double quotes
z %>% index()
#> [
#>     1,
#>     2,
#>     3,
#>     "a"
#> ]
z %>% index() %>% at(text)
#> [
#>     "1",
#>     "2",
#>     "3",
#>     "a"
#> ]

## % encode for URI's
#### DOESNT WORK --------------------------

## html escape
#### DOESNT WORK --------------------------

## serialize to json
#### DOESNT WORK --------------------------
```
