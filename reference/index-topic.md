# index and related functions

index and related functions

## Usage

``` r
index(.data, ...)

index_(.data, ..., .dots)

indexif(.data, ...)

indexif_(.data, ..., .dots)

dotindex(.data, ...)

dotindex_(.data, ..., .dots)
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

## Details

- `index`/`index_` - queries like: `.[]`, `.[0]`, `.[1:5]`, `.["foo"]`

- `indexif`/`indexif_` - queries like: `.["foo"]?`

- `dotindex`/`dotindex_` - queries like: `.[].foo`, `.[].foo.bar`

## Examples

``` r
str <- '[{"name":"JSON", "good":true}, {"name":"XML", "good":false}]'
str %>% index
#> [
#>     {
#>         "name": "JSON",
#>         "good": true
#>     },
#>     {
#>         "name": "XML",
#>         "good": false
#>     }
#> ]
'{"name":"JSON", "good":true}' %>% indexif(name)
#> "JSON"
'{"name":"JSON", "good":true}' %>% indexif(good)
#> true
'{"name":"JSON", "good":true}' %>% indexif(that)
#> null
'{"a": 1, "b": 1}' %>% index
#> [
#>     1,
#>     1
#> ]
'[]' %>% index
#> [
#> 
#> ]
'[{"name":"JSON", "good":true}, {"name":"XML", "good":false}]' %>% index(0)
#> {
#>     "name": "JSON",
#>     "good": true
#> }
'["a","b","c","d","e"]' %>% index(2)
#> "c"
'["a","b","c","d","e"]' %>% index('2:4')
#> [
#>     "c",
#>     "d"
#> ]
'["a","b","c","d","e"]' %>% index('2:5')
#> [
#>     "c",
#>     "d",
#>     "e"
#> ]
'["a","b","c","d","e"]' %>% index(':3')
#> [
#>     "a",
#>     "b",
#>     "c"
#> ]
'["a","b","c","d","e"]' %>% index('-2:')
#> [
#>     "d",
#>     "e"
#> ]

str %>% index %>% select(bad = .name)
#> [
#>     {
#>         "name": "JSON",
#>         "good": true
#>     },
#>     {
#>         "name": "XML",
#>         "good": false
#>     }
#> ]

'[{"name":"JSON", "good":true}, {"name":"XML", "good":false}]' %>%
  dotindex(name)
#> [
#>     "JSON",
#>     "XML"
#> ]
'[{"name":"JSON", "good":true}, {"name":"XML", "good":false}]' %>%
  dotindex(good)
#> [
#>     true,
#>     false
#> ]
'[{"name":"JSON", "good":{"foo":5}}, {"name":"XML", "good":{"foo":6}}]' %>%
  dotindex(good)
#> [
#>     {
#>         "foo": 5
#>     },
#>     {
#>         "foo": 6
#>     }
#> ]
'[{"name":"JSON", "good":{"foo":5}}, {"name":"XML", "good":{"foo":6}}]' %>%
  dotindex(good.foo)
#> [
#>     5,
#>     6
#> ]
```
