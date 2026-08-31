# Search through a recursive structure - extract data from all levels

Search through a recursive structure - extract data from all levels

## Usage

``` r
recurse(.data, ...)

recurse_(.data, ..., .dots)
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
x <- '{"name": "/", "children": [
  {"name": "/bin", "children": [
    {"name": "/bin/ls", "children": []},
    {"name": "/bin/sh", "children": []}]},
  {"name": "/home", "children": [
    {"name": "/home/stephen", "children": [
      {"name": "/home/stephen/jq", "children": []}]}]}]}'
x %>% recurse(.children[]) %>% build_object(name)
#> [
#>     {
#>         "name": "/"
#>     },
#>     {
#>         "name": "/bin"
#>     },
#>     {
#>         "name": "/bin/ls"
#>     },
#>     {
#>         "name": "/bin/sh"
#>     },
#>     {
#>         "name": "/home"
#>     },
#>     {
#>         "name": "/home/stephen"
#>     },
#>     {
#>         "name": "/home/stephen/jq"
#>     }
#> ]
x %>% recurse(.children[]) %>% build_object(name) %>% string
#> [1] "{\"name\": \"/\", \"children\": [\n  {\"name\": \"/bin\", \"children\": [\n    {\"name\": \"/bin/ls\", \"children\": []},\n    {\"name\": \"/bin/sh\", \"children\": []}]},\n  {\"name\": \"/home\", \"children\": [\n    {\"name\": \"/home/stephen\", \"children\": [\n      {\"name\": \"/home/stephen/jq\", \"children\": []}]}]}]}"
```
