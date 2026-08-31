# Math operations

Math operations

## Usage

``` r
do(.data, ...)

do_(.data, ..., .dots)

lengthj(.data)

sqrtj(.data)

floorj(.data)

minj(.data, ...)

minj_(.data, ..., .dots)

maxj(.data, ...)

maxj_(.data, ..., .dots)

ad(.data)

map(.data, ...)

map_(.data, ..., .dots)
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
# do math
jq('{"a": 7}', '.a + 1')
#> 8
# adding null gives back same result
jq('{"a": 7}', '.a + null')
#> 7
jq('{"a": 7}', '.a += 1')
#> {
#>     "a": 8
#> }
'{"a": 7}' %>%  do(.a + 1)
#> 8
# '{"a": 7}' %>%  do(.a += 1) # this doesn't work quite yet
'{"a": [1,2], "b": [3,4]}' %>%  do(.a + .b)
#> [
#>     1,
#>     2,
#>     3,
#>     4
#> ]
'{"a": [1,2], "b": [3,4]}' %>%  do(.a - .b)
#> [
#>     1,
#>     2
#> ]
'{"a": 3}' %>%  do(4 - .a)
#> 1
'["xml", "yaml", "json"]' %>%  do('. - ["xml", "yaml"]')
#> ". - [\"xml\", \"yaml\"]"
'5' %>%  do(10 / . * 3)
#> 6
## many JSON inputs
'{"a": [1,2], "b": [3,4]} {"a": [1,5], "b": [3,10]}' %>%  do(.a + .b)
#> [
#>     [
#>         1,
#>         2,
#>         3,
#>         4
#>     ],
#>     [
#>         1,
#>         5,
#>         3,
#>         10
#>     ]
#> ]

# comparisons
'[5,4,2,7]' %>% index() %>% do(. < 4)
#> [
#>     false,
#>     false,
#>     true,
#>     false
#> ]
'[5,4,2,7]' %>% index() %>% do(. > 4)
#> [
#>     true,
#>     false,
#>     false,
#>     true
#> ]
'[5,4,2,7]' %>% index() %>% do(. <= 4)
#> [
#>     false,
#>     true,
#>     true,
#>     false
#> ]
'[5,4,2,7]' %>% index() %>% do(. >= 4)
#> [
#>     true,
#>     true,
#>     false,
#>     true
#> ]
'[5,4,2,7]' %>% index() %>% do(. == 4)
#> [
#>     false,
#>     true,
#>     false,
#>     false
#> ]
'[5,4,2,7]' %>% index() %>% do(. != 4)
#> [
#>     true,
#>     false,
#>     true,
#>     true
#> ]
## many JSON inputs
'[5,4,2,7] [4,3,200,0.1]' %>% index() %>% do(. < 4)
#> [
#>     false,
#>     false,
#>     true,
#>     false,
#>     false,
#>     true,
#>     false,
#>     true
#> ]

# length
'[[1,2], "string", {"a":2}, null]' %>% index %>% lengthj
#> [
#>     2,
#>     6,
#>     1,
#>     0
#> ]

# sqrt
'9' %>% sqrtj
#> 3
## many JSON inputs
'9 4 5' %>% sqrtj
#> [
#>     3,
#>     2,
#>     2.23606797749979
#> ]

# floor
'3.14159' %>% floorj
#> 3
## many JSON inputs
'3.14159 30.14 45.9' %>% floorj
#> [
#>     3,
#>     30,
#>     45
#> ]

# find minimum
'[5,4,2,7]' %>% minj
#> 2
'[{"foo":1, "bar":14}, {"foo":2, "bar":3}]' %>% minj
#> {
#>     "foo": 2,
#>     "bar": 3
#> }
'[{"foo":1, "bar":14}, {"foo":2, "bar":3}]' %>% minj(foo)
#> {
#>     "foo": 1,
#>     "bar": 14
#> }
'[{"foo":1, "bar":14}, {"foo":2, "bar":3}]' %>% minj(bar)
#> {
#>     "foo": 2,
#>     "bar": 3
#> }
## many JSON inputs
'[{"foo":1}, {"foo":14}] [{"foo":2}, {"foo":3}]' %>% minj(foo)
#> [
#>     {
#>         "foo": 1
#>     },
#>     {
#>         "foo": 2
#>     }
#> ]

# find maximum
'[5,4,2,7]' %>% maxj
#> 7
'[{"foo":1, "bar":14}, {"foo":2, "bar":3}]' %>% maxj
#> {
#>     "foo": 1,
#>     "bar": 14
#> }
'[{"foo":1, "bar":14}, {"foo":2, "bar":3}]' %>% maxj(foo)
#> {
#>     "foo": 2,
#>     "bar": 3
#> }
'[{"foo":1, "bar":14}, {"foo":2, "bar":3}]' %>% maxj(bar)
#> {
#>     "foo": 1,
#>     "bar": 14
#> }
## many JSON inputs
'[{"foo":1}, {"foo":14}] [{"foo":2}, {"foo":3}]' %>% maxj(foo)
#> [
#>     {
#>         "foo": 14
#>     },
#>     {
#>         "foo": 3
#>     }
#> ]

# increment values
## requires special % operators, they get escaped internally
'{"foo": 1}' %>% do(.foo %+=% 1)
#> {
#>     "foo": 2
#> }
'{"foo": 1}' %>% do(.foo %-=% 1)
#> {
#>     "foo": 0
#> }
'{"foo": 1}' %>% do(.foo %*=% 4)
#> {
#>     "foo": 4
#> }
'{"foo": 1}' %>% do(.foo %/=% 10)
#> {
#>     "foo": 0.1
#> }
'{"foo": 1}' %>% do(.foo %//=% 10)
#> {
#>     "foo": 1
#> }
### fix me - %= doesn't work
# '{"foo": 1}' %>% do(.foo %%=% 10)
## many JSON inputs
'{"foo": 1} {"foo": 2} {"foo": 3}' %>% do(.foo %+=% 1)
#> [
#>     {
#>         "foo": 2
#>     },
#>     {
#>         "foo": 3
#>     },
#>     {
#>         "foo": 4
#>     }
#> ]

# add
'["a","b","c"]' %>% ad
#> "abc"
'[1, 2, 3]' %>% ad
#> 6
'[]' %>% ad
#> null
## many JSON inputs
'["a","b","c"] ["d","e","f"]' %>% ad
#> [
#>     "abc",
#>     "def"
#> ]

# map
## as far as I know, this only works with numbers, thus it's
## in the maths section
'[1, 2, 3]' %>% map(.+1)
#> [
#>     2,
#>     3,
#>     4
#> ]
'[1, 2, 3]' %>% map(./1)
#> [
#>     1,
#>     2,
#>     3
#> ]
'[1, 2, 3]' %>% map(.*4)
#> [
#>     4,
#>     8,
#>     12
#> ]
# many JSON inputs
'[1, 2, 3] [100, 200, 300] [1000, 2000, 30000]' %>% map(.+1)
#> [
#>     [
#>         2,
#>         3,
#>         4
#>     ],
#>     [
#>         101,
#>         201,
#>         301
#>     ],
#>     [
#>         1001,
#>         2001,
#>         30001
#>     ]
#> ]
```
