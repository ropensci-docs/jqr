# Combine json pieces

Combine json pieces

## Usage

``` r
combine(x)
```

## Arguments

- x:

  Input, of class json

## Examples

``` r
x <- '{"foo": 5, "bar": 7}' %>% select(a = .foo)
combine(x)
#> {
#>     "foo": 5,
#>     "bar": 7
#> }

(x <- commits %>% index() %>%
 select(sha = .sha, name = .commit.committer.name))
#> [
#>     {
#>         "sha": [
#>             "110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Travis Gockel"
#>                 ],
#>                 "email": [
#>                     "travis@gockelhut.com"
#>                 ],
#>                 "date": [
#>                     "2015-03-05T04:09:00Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-22T00:17:16Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add wrapping and clamping to jv_array_slice\n\nFix #716.  Fix #717."
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "tgockel"
#>             ],
#>             "id": [
#>                 386039
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/386039?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/tgockel"
#>             ],
#>             "html_url": [
#>                 "https://github.com/tgockel"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/tgockel/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/tgockel/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/tgockel/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/tgockel/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/tgockel/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/tgockel/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/tgockel/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/tgockel/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/tgockel/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Travis Gockel"
#>                 ],
#>                 "email": [
#>                     "travis@gockelhut.com"
#>                 ],
#>                 "date": [
#>                     "2015-03-05T04:09:00Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-22T00:17:16Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add wrapping and clamping to jv_array_slice\n\nFix #716.  Fix #717."
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "tgockel"
#>             ],
#>             "id": [
#>                 386039
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/386039?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/tgockel"
#>             ],
#>             "html_url": [
#>                 "https://github.com/tgockel"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/tgockel/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/tgockel/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/tgockel/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/tgockel/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/tgockel/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/tgockel/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/tgockel/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/tgockel/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/tgockel/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T22:18:33Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:49:24Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Print offending object in runtime error messages\n\nWhen reporting an error to the user, add information about the offending\nobject/value (possibly truncated).\n\nThe goal is to give a user some context regarding which input object\ncaused the runtime error.\n\nExamples:\n\n    $ echo '\"hello\"' | ./jq '-.'\n    jq: error: string (\"hello\") cannot be negated\n\n    $ echo '\"very-long-string\"' | ./jq '-.'\n    jq: error: string (\"very-long-...) cannot be negated\n\n    $ echo '[\"1\",2]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and number (2) cannot be added\n\n    $ echo '[\"1\",\"2\",{\"a\":{\"b\":{\"c\":33}}}]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and object ({\"a\":{\"b\":{...) cannot be added\n\n    $ echo '{\"a\":{\"b\":{\"c\":33}}}' | ./jq '.a | @tsv'\n    jq: error: object ({\"b\":{\"c\":33}}) cannot be tsv-formatted, only array\n\n(Fix #754)"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T22:18:33Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:49:24Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Print offending object in runtime error messages\n\nWhen reporting an error to the user, add information about the offending\nobject/value (possibly truncated).\n\nThe goal is to give a user some context regarding which input object\ncaused the runtime error.\n\nExamples:\n\n    $ echo '\"hello\"' | ./jq '-.'\n    jq: error: string (\"hello\") cannot be negated\n\n    $ echo '\"very-long-string\"' | ./jq '-.'\n    jq: error: string (\"very-long-...) cannot be negated\n\n    $ echo '[\"1\",2]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and number (2) cannot be added\n\n    $ echo '[\"1\",\"2\",{\"a\":{\"b\":{\"c\":33}}}]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and object ({\"a\":{\"b\":{...) cannot be added\n\n    $ echo '{\"a\":{\"b\":{\"c\":33}}}' | ./jq '.a | @tsv'\n    jq: error: object ({\"b\":{\"c\":33}}) cannot be tsv-formatted, only array\n\n(Fix #754)"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:05Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:15Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Fix error message for @tsv"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:05Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:15Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Fix error message for @tsv"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:47:01Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:55:27Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Don't test input_filename/line_number yet"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:47:01Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:55:27Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Don't test input_filename/line_number yet"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T20:08:10Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T05:49:32Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add filename/line functions to jq (fix #753)\n\nThis adds `input_filename` and `input_line_number` built-in functions\nfor use in, for example, `error` messages.\n\nExample:\n\n    $ printf '{\"a\":1}\\n{\"a\":2}\\n' > 4.json\n    $ printf '{\"a\":\"hello\"}\\n' > 5.json\n    $ ./jq '{ \"file\":input_filename, \"line\":input_line_number, \"value\":.a }' 4.json 5.json\n    {\n      \"file\": \"4.json\",\n      \"line\": 1,\n      \"value\": 1\n    }\n    {\n      \"file\": \"4.json\",\n      \"line\": 2,\n      \"value\": 2\n    }\n    {\n      \"file\": \"5.json\",\n      \"line\": 1,\n      \"value\": \"hello\"\n    }"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T20:08:10Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T05:49:32Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add filename/line functions to jq (fix #753)\n\nThis adds `input_filename` and `input_line_number` built-in functions\nfor use in, for example, `error` messages.\n\nExample:\n\n    $ printf '{\"a\":1}\\n{\"a\":2}\\n' > 4.json\n    $ printf '{\"a\":\"hello\"}\\n' > 5.json\n    $ ./jq '{ \"file\":input_filename, \"line\":input_line_number, \"value\":.a }' 4.json 5.json\n    {\n      \"file\": \"4.json\",\n      \"line\": 1,\n      \"value\": 1\n    }\n    {\n      \"file\": \"4.json\",\n      \"line\": 2,\n      \"value\": 2\n    }\n    {\n      \"file\": \"5.json\",\n      \"line\": 1,\n      \"value\": \"hello\"\n    }"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ]
#>             }
#>         ]
#>     }
#> ]
combine(x)
#> [
#>     {
#>         "sha": [
#>             "110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Travis Gockel"
#>                 ],
#>                 "email": [
#>                     "travis@gockelhut.com"
#>                 ],
#>                 "date": [
#>                     "2015-03-05T04:09:00Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-22T00:17:16Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add wrapping and clamping to jv_array_slice\n\nFix #716.  Fix #717."
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "tgockel"
#>             ],
#>             "id": [
#>                 386039
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/386039?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/tgockel"
#>             ],
#>             "html_url": [
#>                 "https://github.com/tgockel"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/tgockel/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/tgockel/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/tgockel/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/tgockel/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/tgockel/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/tgockel/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/tgockel/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/tgockel/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/tgockel/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Travis Gockel"
#>                 ],
#>                 "email": [
#>                     "travis@gockelhut.com"
#>                 ],
#>                 "date": [
#>                     "2015-03-05T04:09:00Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-22T00:17:16Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add wrapping and clamping to jv_array_slice\n\nFix #716.  Fix #717."
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/a52a4b412c3ba4bd2e237f37a5f11fd565e74bae"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/110e009996e1359d25b8e99e71f83b96e5870790"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/110e009996e1359d25b8e99e71f83b96e5870790/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "tgockel"
#>             ],
#>             "id": [
#>                 386039
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/386039?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/tgockel"
#>             ],
#>             "html_url": [
#>                 "https://github.com/tgockel"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/tgockel/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/tgockel/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/tgockel/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/tgockel/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/tgockel/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/tgockel/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/tgockel/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/tgockel/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/tgockel/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T22:18:33Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:49:24Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Print offending object in runtime error messages\n\nWhen reporting an error to the user, add information about the offending\nobject/value (possibly truncated).\n\nThe goal is to give a user some context regarding which input object\ncaused the runtime error.\n\nExamples:\n\n    $ echo '\"hello\"' | ./jq '-.'\n    jq: error: string (\"hello\") cannot be negated\n\n    $ echo '\"very-long-string\"' | ./jq '-.'\n    jq: error: string (\"very-long-...) cannot be negated\n\n    $ echo '[\"1\",2]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and number (2) cannot be added\n\n    $ echo '[\"1\",\"2\",{\"a\":{\"b\":{\"c\":33}}}]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and object ({\"a\":{\"b\":{...) cannot be added\n\n    $ echo '{\"a\":{\"b\":{\"c\":33}}}' | ./jq '.a | @tsv'\n    jq: error: object ({\"b\":{\"c\":33}}) cannot be tsv-formatted, only array\n\n(Fix #754)"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T22:18:33Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:49:24Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Print offending object in runtime error messages\n\nWhen reporting an error to the user, add information about the offending\nobject/value (possibly truncated).\n\nThe goal is to give a user some context regarding which input object\ncaused the runtime error.\n\nExamples:\n\n    $ echo '\"hello\"' | ./jq '-.'\n    jq: error: string (\"hello\") cannot be negated\n\n    $ echo '\"very-long-string\"' | ./jq '-.'\n    jq: error: string (\"very-long-...) cannot be negated\n\n    $ echo '[\"1\",2]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and number (2) cannot be added\n\n    $ echo '[\"1\",\"2\",{\"a\":{\"b\":{\"c\":33}}}]' | ./jq '.|join(\",\")'\n    jq: error: string (\",\") and object ({\"a\":{\"b\":{...) cannot be added\n\n    $ echo '{\"a\":{\"b\":{\"c\":33}}}' | ./jq '.a | @tsv'\n    jq: error: object ({\"b\":{\"c\":33}}) cannot be tsv-formatted, only array\n\n(Fix #754)"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/9e5a63bde790eb18aed024fc6ae39b0ec05056cf"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/7b6a018dff623a4f13f6bcd52c7c56d9b4a4165f/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:05Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:15Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Fix error message for @tsv"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:05Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T23:20:15Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Fix error message for @tsv"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/0c19fa794d3f49c05143968aab9c1ed5e2a8ab0c"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/a50e548cc5313c187483bc8fb1b95e1798e8ef65"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/a50e548cc5313c187483bc8fb1b95e1798e8ef65/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:47:01Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:55:27Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Don't test input_filename/line_number yet"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:47:01Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T22:55:27Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Don't test input_filename/line_number yet"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/2987821f4f458cd224dc1ea7ac100dad1ac1c2b3"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/4b258f7d31b34ff5d45fba431169e7fd4c995283"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/4b258f7d31b34ff5d45fba431169e7fd4c995283/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T20:08:10Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T05:49:32Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add filename/line functions to jq (fix #753)\n\nThis adds `input_filename` and `input_line_number` built-in functions\nfor use in, for example, `error` messages.\n\nExample:\n\n    $ printf '{\"a\":1}\\n{\"a\":2}\\n' > 4.json\n    $ printf '{\"a\":\"hello\"}\\n' > 5.json\n    $ ./jq '{ \"file\":input_filename, \"line\":input_line_number, \"value\":.a }' 4.json 5.json\n    {\n      \"file\": \"4.json\",\n      \"line\": 1,\n      \"value\": 1\n    }\n    {\n      \"file\": \"4.json\",\n      \"line\": 2,\n      \"value\": 2\n    }\n    {\n      \"file\": \"5.json\",\n      \"line\": 1,\n      \"value\": \"hello\"\n    }"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ]
#>             }
#>         ]
#>     },
#>     {
#>         "sha": [
#>             "d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "commit": {
#>             "author": {
#>                 "name": [
#>                     "Assaf Gordon"
#>                 ],
#>                 "email": [
#>                     "assafgordon@gmail.com"
#>                 ],
#>                 "date": [
#>                     "2015-04-17T20:08:10Z"
#>                 ]
#>             },
#>             "committer": {
#>                 "name": [
#>                     "Nicolas Williams"
#>                 ],
#>                 "email": [
#>                     "nico@cryptonector.com"
#>                 ],
#>                 "date": [
#>                     "2015-05-21T05:49:32Z"
#>                 ]
#>             },
#>             "message": [
#>                 "Add filename/line functions to jq (fix #753)\n\nThis adds `input_filename` and `input_line_number` built-in functions\nfor use in, for example, `error` messages.\n\nExample:\n\n    $ printf '{\"a\":1}\\n{\"a\":2}\\n' > 4.json\n    $ printf '{\"a\":\"hello\"}\\n' > 5.json\n    $ ./jq '{ \"file\":input_filename, \"line\":input_line_number, \"value\":.a }' 4.json 5.json\n    {\n      \"file\": \"4.json\",\n      \"line\": 1,\n      \"value\": 1\n    }\n    {\n      \"file\": \"4.json\",\n      \"line\": 2,\n      \"value\": 2\n    }\n    {\n      \"file\": \"5.json\",\n      \"line\": 1,\n      \"value\": \"hello\"\n    }"
#>             ],
#>             "tree": {
#>                 "sha": [
#>                     "e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/git/trees/e06b0125148eea42b7881c380b6bcfb05c3b102f"
#>                 ]
#>             },
#>             "url": [
#>                 "https://api.github.com/repos/stedolan/jq/git/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>             ],
#>             "comment_count": [
#>                 0
#>             ]
#>         },
#>         "url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "html_url": [
#>             "https://github.com/stedolan/jq/commit/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5"
#>         ],
#>         "comments_url": [
#>             "https://api.github.com/repos/stedolan/jq/commits/d1cb8ee0ad3ddf03a37394bfa899cfd3ddd007c5/comments"
#>         ],
#>         "author": {
#>             "login": [
#>                 "agordon"
#>             ],
#>             "id": [
#>                 523057
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/523057?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/agordon"
#>             ],
#>             "html_url": [
#>                 "https://github.com/agordon"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/agordon/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/agordon/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/agordon/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/agordon/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/agordon/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/agordon/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/agordon/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/agordon/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/agordon/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "committer": {
#>             "login": [
#>                 "nicowilliams"
#>             ],
#>             "id": [
#>                 604851
#>             ],
#>             "avatar_url": [
#>                 "https://avatars.githubusercontent.com/u/604851?v=3"
#>             ],
#>             "gravatar_id": [
#>                 ""
#>             ],
#>             "url": [
#>                 "https://api.github.com/users/nicowilliams"
#>             ],
#>             "html_url": [
#>                 "https://github.com/nicowilliams"
#>             ],
#>             "followers_url": [
#>                 "https://api.github.com/users/nicowilliams/followers"
#>             ],
#>             "following_url": [
#>                 "https://api.github.com/users/nicowilliams/following{/other_user}"
#>             ],
#>             "gists_url": [
#>                 "https://api.github.com/users/nicowilliams/gists{/gist_id}"
#>             ],
#>             "starred_url": [
#>                 "https://api.github.com/users/nicowilliams/starred{/owner}{/repo}"
#>             ],
#>             "subscriptions_url": [
#>                 "https://api.github.com/users/nicowilliams/subscriptions"
#>             ],
#>             "organizations_url": [
#>                 "https://api.github.com/users/nicowilliams/orgs"
#>             ],
#>             "repos_url": [
#>                 "https://api.github.com/users/nicowilliams/repos"
#>             ],
#>             "events_url": [
#>                 "https://api.github.com/users/nicowilliams/events{/privacy}"
#>             ],
#>             "received_events_url": [
#>                 "https://api.github.com/users/nicowilliams/received_events"
#>             ],
#>             "type": [
#>                 "User"
#>             ],
#>             "site_admin": [
#>                 false
#>             ]
#>         },
#>         "parents": [
#>             {
#>                 "sha": [
#>                     "c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "url": [
#>                     "https://api.github.com/repos/stedolan/jq/commits/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ],
#>                 "html_url": [
#>                     "https://github.com/stedolan/jq/commit/c7f063188f50ddf3271828244c5831a30f72a667"
#>                 ]
#>             }
#>         ]
#>     }
#> ]
```
