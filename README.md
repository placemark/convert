# Placemark convert

This is Placemark's file conversion infrastructure, being
gradually open sourced. This is **under construction
and hasn't reached its first release yet.**

Placemark supports [a lot of file formats](https://www.placemark.io/format-matrix).
It supports things like importing and exporting those formats.
You can convert a single feature to its representation in a format.
Some of the converters are configurable. Some are interactive.
Some give detailed feedback along with the converted file.

This repo will contain that logic: bidirectional (when possible)
converters for a number of formats. Some of the core converters
I wrote and maintained, like toGeoJSON, betterknown, the GTFS
parser. A few parsers are used from open source modules verbatim.
Others have been vendored, to add improvements, types, or
modernizations.

This is more opinionated and application-level than most
conversion methods. I use [Either types](https://gigobyte.github.io/purify/adts/Either)
for results. The parsers are designed to optionally work in
a WebWorker. Some parsers, like toGeoJSON, use a JavaScript
DOM implementation to normalize browser differences. There
are TypeScript definitions for standardized configuration, input,
and output types.

If you're just trying to convert from one format to another,
you probably want something else. But if you're building an
application with an import panel, this might be a good place to start.
