# Build arrays and objects

Build arrays and objects

## Usage

``` r
build_array(.data, ...)

build_array_(.data, ..., .dots)

build_object(.data, ...)

build_object_(.data, ..., .dots)
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
## BUILD ARRAYS
x <- '{"user":"jqlang", "projects": ["jq", "wikiflow"]}' 
jq(x, "[.user, .projects[]]")
#> [
#>     "jqlang",
#>     "jq",
#>     "wikiflow"
#> ]
x %>% build_array(.user, .projects[])
#> [
#>     "jqlang",
#>     "jq",
#>     "wikiflow"
#> ]

jq('[1, 2, 3]', '[ .[] | . * 2]')
#> [
#>     2,
#>     4,
#>     6
#> ]
'[1, 2, 3]' %>% build_array(.[] | . * 2)
#> [
#>     2,
#>     4,
#>     6
#> ]


## BUILD OBJECTS
'{"foo": 5, "bar": 7}' %>% build_object(a = .foo) %>% peek
#> <jq query>
#>   query: {a: .foo}
'{"foo": 5, "bar": 7}' %>% build_object(a = .foo)
#> {
#>     "a": 5
#> }

# using json dataset, just first element
x <- commits %>% index(0)
x %>%
   build_object(message = .commit.message, name = .commit.committer.name)
#> {
#>     "message": [
#>         "Add wrapping and clamping to jv_array_slice\n\nFix #716.  Fix #717."
#>     ],
#>     "name": [
#>         "Nicolas Williams"
#>     ]
#> }
x %>% build_object(sha = .commit.tree.sha, author = .author.login)
#> {
#>     "sha": [
#>         "a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>     ],
#>     "author": [
#>         "tgockel"
#>     ]
#> }

# using json dataset, all elements
x <- index(commits)
x %>% build_object(message = .commit.message, name = .commit.committer.name)
#> [
#>     {
#>         "message": [
#>             "Add wrapping and clamping to jv_array_slice\n\nFix #716.  Fix #717."
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "message": [
#>             "Print offending object in runtime error messages\n\nWhen reporting an error to the user, add information about the offending\nobject/value (possibly truncated).\n\nThe goal is to give a user some context regarding which input object\ncaused the runtime error.\n\nExamples:\n\n    $ echo '\"hello\"' | ./jq '-.'\n    jq: error: string (\"hello\") cannot be negated\n\n    $ echo '\"very-long-string\"' | ./jq '-.'\n    jq: error: string (\"very-long-...) cannot be negated\n\n    $ echo '[\"1\",2]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and number (2) cannot be added\n\n    $ echo '[\"1\",\"2\",{\"a\":{\"b\":{\"c\":33}}}]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and object ({\"a\":{\"b\":{...) cannot be added\n\n    $ echo '{\"a\":{\"b\":{\"c\":33}}}' | ./jq '.a | @tsv'\n    jq: error: object ({\"b\":{\"c\":33}}) cannot be tsv-formatted, only array\n\n(Fix #754)"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "message": [
#>             "Fix error message for @tsv"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "message": [
#>             "Don't test input_filename/line_number yet"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "message": [
#>             "Add filename/line functions to jq (fix #753)\n\nThis adds `input_filename` and `input_line_number` built-in functions\nfor use in, for example, `error` messages.\n\nExample:\n\n    $ printf '{\"a\":1}\\n{\"a\":2}\\n' > 4.json\n    $ printf '{\"a\":\"hello\"}\\n' > 5.json\n    $ ./jq '{ \"file\":input_filename, \"line\":input_line_number, \"value\":.a }' 4.json 5.json\n    {\n      \"file\": \"4.json\",\n      \"line\": 1,\n      \"value\": 1\n    }\n    {\n      \"file\": \"4.json\",\n      \"line\": 2,\n      \"value\": 2\n    }\n    {\n      \"file\": \"5.json\",\n      \"line\": 1,\n      \"value\": \"hello\"\n    }"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     }
#> ]
x %>% build_object(sha = .sha, name = .commit.committer.name)
#> [
#>     {
#>         "sha": [
#>             "110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "name": [
#>             "Nicolas Williams"
#>         ]
#>     }
#> ]

# many JSON inputs
'{"foo": 5, "bar": 7} {"foo": 50, "bar": 7} {"foo": 500, "bar": 7}' %>%
  build_object(hello = .foo)
#> [
#>     {
#>         "hello": 5
#>     },
#>     {
#>         "hello": 50
#>     },
#>     {
#>         "hello": 500
#>     }
#> ]
```
