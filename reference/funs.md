# Define and use functions

Define and use functions

## Usage

``` r
funs(.data, fxn, action)
```

## Arguments

- .data:

  input

- fxn:

  A function definition, without `def` (added internally)

- action:

  What to do with the function on the data

## Examples

``` r
jq("[1,2,10,20]", 'def increment: . + 1; map(increment)')
#> [
#>     2,
#>     3,
#>     11,
#>     21
#> ]
"[1,2,10,20]" %>% funs('increment: . + 1', 'map(increment)')
#> [
#>     2,
#>     3,
#>     11,
#>     21
#> ]
"[1,2,10,20]" %>% funs('increment: . / 100', 'map(increment)')
#> [
#>     0.01,
#>     0.02,
#>     0.1,
#>     0.2
#> ]
"[1,2,10,20]" %>% funs('increment: . / 100', 'map(increment)')
#> [
#>     0.01,
#>     0.02,
#>     0.1,
#>     0.2
#> ]
'[[1,2],[10,20]]' %>% funs('addvalue(f): f as $x | map(. + $x)', 'addvalue(.[0])')
#> [
#>     [
#>         1,
#>         2,
#>         1,
#>         2
#>     ],
#>     [
#>         10,
#>         20,
#>         1,
#>         2
#>     ]
#> ]
"[1,2]" %>% funs('f(a;b;c;d;e;f): [a+1,b,c,d,e,f]', 'f(.[0];.[1];.[0];.[0];.[0];.[0])')
#> [
#>     2,
#>     2,
#>     1,
#>     1,
#>     1,
#>     1
#> ]
"[1,2,3,4]" %>% funs('fac: if . == 1 then 1 else . * (. - 1 | fac) end', '[.[] | fac]')
#> [
#>     1,
#>     2,
#>     6,
#>     24
#> ]
```
