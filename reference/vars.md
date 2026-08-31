# Variables

Variables

## Usage

``` r
vars(.data, ...)

vars_(.data, ..., .dots)
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
x <- '{
 "posts": [
   {"title": "Frist psot", "author": "anon"},
   {"title": "A well-written article", "author": "person1"}
 ],
 "realnames": {
   "anon": "Anonymous Coward",
   "person1": "Person McPherson"
 }
}'

x %>% dotstr(posts[])
#> [
#>     {
#>         "title": "Frist psot",
#>         "author": "anon"
#>     },
#>     {
#>         "title": "A well-written article",
#>         "author": "person1"
#>     }
#> ]
x %>% dotstr(posts[]) %>% string
#> [1] "{\n \"posts\": [\n   {\"title\": \"Frist psot\", \"author\": \"anon\"},\n   {\"title\": \"A well-written article\", \"author\": \"person1\"}\n ],\n \"realnames\": {\n   \"anon\": \"Anonymous Coward\",\n   \"person1\": \"Person McPherson\"\n }\n}"
x %>% vars(realnames = names) %>% dotstr(posts[]) %>%
   build_object(title, author = "$names[.author]")
#> [
#>     {
#>         "title": "Frist psot",
#>         "author": "Anonymous Coward"
#>     },
#>     {
#>         "title": "A well-written article",
#>         "author": "Person McPherson"
#>     }
#> ]
```
