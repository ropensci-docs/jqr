# Manipulation operations

Manipulation operations

## Usage

``` r
join(.data, ...)

join_(.data, ..., .dots)

splitj(.data, ...)

splitj_(.data, ..., .dots)

ltrimstr(.data, ...)

ltrimstr_(.data, ..., .dots)

rtrimstr(.data, ...)

rtrimstr_(.data, ..., .dots)

startswith(.data, ...)

startswith_(.data, ..., .dots)

endswith(.data, ...)

endswith_(.data, ..., .dots)

index_loc(.data, ...)

index_loc_(.data, ..., .dots)

rindex_loc(.data, ...)

rindex_loc_(.data, ..., .dots)

indices(.data, ...)

indices_(.data, ..., .dots)

tojson(.data)

fromjson(.data)

tostring(.data)

tonumber(.data)

contains(.data, ...)

contains_(.data, ..., .dots)

uniquej(.data, ...)

uniquej_(.data, ..., .dots)

group(.data, ...)

group_(.data, ..., .dots)
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
# join
str <- '["a","b,c,d","e"]'
jq(str, 'join(", ")')
#> "a, b,c,d, e"
str %>% join
#> "a, b,c,d, e"
str %>% join(`;`)
#> "a; b,c,d; e"
str %>% join(`yep`)
#> "ayep b,c,dyep e"
## many JSON inputs
'["a","b,c,d","e"] ["a","f,e,f"]' %>% join(`---`)
#> [
#>     "a--- b,c,d--- e",
#>     "a--- f,e,f"
#> ]

# split
jq('"a, b,c,d, e"', 'split(", ")')
#> [
#>     "a",
#>     "b,c,d",
#>     "e"
#> ]

# ltrimstr
jq('["fo", "foo", "barfoo", "foobar", "afoo"]', '[.[]|ltrimstr("foo")]')
#> [
#>     "fo",
#>     "",
#>     "barfoo",
#>     "bar",
#>     "afoo"
#> ]
'["fo", "foo", "barfoo", "foobar", "afoo"]' %>% index() %>% ltrimstr(foo)
#> [
#>     "fo",
#>     "",
#>     "barfoo",
#>     "bar",
#>     "afoo"
#> ]

# rtrimstr
jq('["fo", "foo", "barfoo", "foobar", "foob"]', '[.[]|rtrimstr("foo")]')
#> [
#>     "fo",
#>     "",
#>     "bar",
#>     "foobar",
#>     "foob"
#> ]
'["fo", "foo", "barfoo", "foobar", "foob"]' %>% index() %>% rtrimstr(foo)
#> [
#>     "fo",
#>     "",
#>     "bar",
#>     "foobar",
#>     "foob"
#> ]

# startswith
str <- '["fo", "foo", "barfoo", "foobar", "barfoob"]'
jq(str, '[.[]|startswith("foo")]')
#> [
#>     false,
#>     true,
#>     false,
#>     true,
#>     false
#> ]
str %>% index %>% startswith(foo)
#> [
#>     false,
#>     true,
#>     false,
#>     true,
#>     false
#> ]
## many JSON inputs
'["fo", "foo"] ["barfoo", "foobar", "barfoob"]' %>% index %>% startswith(foo)
#> [
#>     false,
#>     true,
#>     false,
#>     true,
#>     false
#> ]

# endswith
jq(str, '[.[]|endswith("foo")]')
#> [
#>     false,
#>     true,
#>     true,
#>     false,
#>     false
#> ]
str %>% index %>% endswith(foo)
#> [
#>     false,
#>     true,
#>     true,
#>     false,
#>     false
#> ]
str %>% index %>% endswith_("foo")
#> [
#>     false,
#>     true,
#>     true,
#>     false,
#>     false
#> ]
str %>% index %>% endswith(bar)
#> [
#>     false,
#>     false,
#>     false,
#>     true,
#>     false
#> ]
str %>% index %>% endswith_("bar")
#> [
#>     false,
#>     false,
#>     false,
#>     true,
#>     false
#> ]
## many JSON inputs
'["fo", "foo"] ["barfoo", "foobar", "barfoob"]' %>% index %>% endswith(foo)
#> [
#>     false,
#>     true,
#>     true,
#>     false,
#>     false
#> ]

# get index (location) of a character
## input has to be quoted
str <- '"a,b, cd, efg, hijk"'
str %>% index_loc(", ")
#> 3
str %>% index_loc(",")
#> 1
str %>% index_loc("j")
#> 16
str %>% rindex_loc(", ")
#> 12
str %>% indices(", ")
#> [
#>     3,
#>     7,
#>     12
#> ]

# tojson, fromjson, tostring, tonumber
'[1, "foo", ["foo"]]' %>% index %>% tostring
#> [
#>     "1",
#>     "foo",
#>     "[\"foo\"]"
#> ]
'[1, "1"]' %>% index %>% tonumber
#> [
#>     1,
#>     1
#> ]
'[1, "foo", ["foo"]]' %>% index %>% tojson
#> [
#>     "1",
#>     "\"foo\"",
#>     "[\"foo\"]"
#> ]
'[1, "foo", ["foo"]]' %>% index %>% tojson %>% fromjson
#> [
#>     1,
#>     "foo",
#>     [
#>         "foo"
#>     ]
#> ]

# contains
'"foobar"' %>% contains("bar")
#> true
'["foobar", "foobaz", "blarp"]' %>% contains(`["baz", "bar"]`)
#> true
'["foobar", "foobaz", "blarp"]' %>% contains(`["bazzzzz", "bar"]`)
#> false
str <- '{"foo": 12, "bar":[1,2,{"barp":12, "blip":13}]}'
str %>% contains(`{foo: 12, bar: [{barp: 12}]}`)
#> true
str %>% contains(`{foo: 12, bar: [{barp: 15}]}`)
#> false

# unique
'[1,2,5,3,5,3,1,3]' %>% uniquej
#> [
#>     1,
#>     2,
#>     3,
#>     5
#> ]
str <- '[{"foo": 1, "bar": 2}, {"foo": 1, "bar": 3}, {"foo": 4, "bar": 5}]'
str %>% uniquej(foo)
#> [
#>     {
#>         "foo": 1,
#>         "bar": 2
#>     },
#>     {
#>         "foo": 4,
#>         "bar": 5
#>     }
#> ]
str %>% uniquej_("foo")
#> [
#>     {
#>         "foo": 1,
#>         "bar": 2
#>     },
#>     {
#>         "foo": 4,
#>         "bar": 5
#>     }
#> ]
'["chunky", "bacon", "kitten", "cicada", "asparagus"]' %>% uniquej(length)
#> [
#>     "bacon",
#>     "chunky",
#>     "asparagus"
#> ]

# group
x <- '[{"foo":1, "bar":10}, {"foo":3, "bar":100}, {"foo":1, "bar":1}]'
x %>% group(foo)
#> [
#>     [
#>         {
#>             "foo": 1,
#>             "bar": 10
#>         },
#>         {
#>             "foo": 1,
#>             "bar": 1
#>         }
#>     ],
#>     [
#>         {
#>             "foo": 3,
#>             "bar": 100
#>         }
#>     ]
#> ]
x %>% group_("foo")
#> [
#>     [
#>         {
#>             "foo": 1,
#>             "bar": 10
#>         },
#>         {
#>             "foo": 1,
#>             "bar": 1
#>         }
#>     ],
#>     [
#>         {
#>             "foo": 3,
#>             "bar": 100
#>         }
#>     ]
#> ]
```
