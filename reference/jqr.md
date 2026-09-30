# jqr

An R client for the C library jq

## Low-level

Low level interface, in which you can execute \`jq\` code just as you
would on the command line. Available via
[`jq`](https://docs.ropensci.org/jqr/reference/jq.md)

## High-level DSL

High-level, uses a suite of functions to construct queries. Queries are
constucted, then excuted internally with
[`jq`](https://docs.ropensci.org/jqr/reference/jq.md)

## Pipes

The high level DSL supports piping, though you don't have to use pipes.

## NSE and SE

Most DSL functions have NSE (non-standard evaluation) and SE (standard
evaluation) versions, which make `jqr` easy to use for interactive use
as well as programming.

## jq version

We link to `jq` through the installed version on your system, so the
version can vary. Run `jq --version` to get your jq version

## indexing

note that `jq` indexing starts at `0`, whereas R indexing starts at `1`.
So when you want the first thing in an array using `jq`, for example,
you want `0`, not `1`

## output data format

Note that with both the low level interface and the high level DSL, we
print the output to look like a valid JSON object to make it easier to
look at. However, it's important to know that the output is really just
a simple character string or vector of strings - it's just the print
function that pretty prints it and makes it look like a single JSON
object. What jq is giving you often is a stream of valid JSON objects,
each one of which is valid, but altogether are not valid. However, a
trick you can do is to wrap your jq program in brackets like `[.[]]`
instead of `.[]` to give a single JSON object

Related to above, you can use the function provided
[`string`](https://docs.ropensci.org/jqr/reference/string.md) with the
high level DSL to get back a character string instead of pretty printed
version

## See also

Useful links:

- <https://docs.ropensci.org/jqr/>

- <https://ropensci.r-universe.dev/jqr>

- Report bugs at <https://github.com/ropensci/jqr/issues>

## Author

**Maintainer**: Jeroen Ooms <jeroen@gmail.com>

Authors:

- Rich FitzJohn <rich.fitzjohn@gmail.com>

- Scott Chamberlain <myrmecocystus@gmail.com>

- Stefan Milton Bache <stefan@stefanbache.dk>
