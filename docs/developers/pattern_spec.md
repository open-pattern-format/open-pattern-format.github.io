# OPAF Pattern Specification

Pattern files have the extension `.opaf` and should be seen as source code for a given pattern. Pattern files require [packaging](packaging.md) before being distributed.

A pattern is built using the following basic elements:

 * `<opaf:component>`
 * `<opaf:instruction>`
 * `<opaf:action>`

## Pattern
A pattern file requires a `<pattern>` root element with the following attributes:

 * `xmlns:opaf`: `"https://github.com/open-pattern-format/opaf"`
 * `name`: The name of the pattern [required]
 * `version`: Version number which is compatible with the [Symantic Versioning Specification](https://semver.org/) (e.g. 1.0.0) [required]
 * `unique_id`: UUID identifier for the pattern (e.g. 89ab9835-10c0-46a8-89ab-d81b980a1d97)

``` xml title="Pattern Example"
<pattern version="1.0.0" xmlns:opaf="https://github.com/open-pattern-format/opaf" name="My First Pattern" unique_id="123ab456-1234-56cc-d789-60f8305bcdab">

</pattern>
```

## Metadata
Metadata is indicated by a `<opaf:metadata>` node which will contain nested child elements. See the [metadata specification](metadata.md) documentation for more information.

``` xml title="Metadata Example"
<opaf:metadata>
    ...
</opaf:metadata>
```

## Color
Colors which will be used in the pattern are defined using `<opaf:define_color>` nodes. The following attributes are supported:

 * `name`: A string identifier for the color. The name must not contain spaces.
 *  `description`: A short description of the color and what it is used for.
 * `value`: A hex representation of the color or one of the following `[black, silver, white, red, purple, green, yellow, blue]`

``` xml title="Color Example"
<opaf:define_color name="contrast" value="#2a365c" description="Contrast yarn"/>
```

## Action
Actions are used to build instructions in a pattern. Everything from a simple knit stitch to cables are defined using actions.

A set of standard knitting actions are defined [HERE](https://github.com/open-pattern-format/opaf/blob/main/actions.opaf).