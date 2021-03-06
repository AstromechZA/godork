# `godork`

A system like godoc but designed for static self-hosting.

It comes in various parts:

- The core `github.com/AstromechZA/godork` package. Provides the parsing and interpretation by wrapping the `go/doc`
api.
- The `github.com/AstromechZA/godork/cli` binary which wraps all the functionality in a convenient binary.
- A set of example and default templates in the `./templates` directory.

*Note:* Unlike the official godoc, this package doesn't automatically link text in the output format to other symbols and documentation. That'll be an extension to this package in the future.

## Examples

An `example` package is provided that we use to test various features of this.

The two templates that are provided result in the following:

- `templates/milligram.html.template` -> [milligram.example.html](https://htmlpreview.github.io/?https://github.com/AstromechZA/godork/blob/master/templates/milligram.example.html)
- `templates/markdown.md.template` -> [markdown.example.md](./templates/markdown.example.md)

## Build the binary

```bash
$ cd ./cli
$ ./build
```

This creates the `godork` binary.

## Usage

A quick example that generates markdown documentation for the package.

```bash
$ godork template ./example github.com/AstromechZA/godork/example --template templates/markdown.md.template > templates/markdown.example.md
```

Markdown is not the best representation when compared to the official godoc stuff but it may be suitable in some places.
So we can move onto using a simple html example:

```bash
$ godork template ./example github.com/AstromechZA/godork/example --template templates/milligram.html.template --html-mode > templates/milligram.example.html
```
