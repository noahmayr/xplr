# Searching

xplr supports searching paths using different algorithm. The search mechanism
generally appears between filters and sorters in the `Sort & filter` panel.

Example:

```
/fzy↓abc
```

This line means that the nodes visible on the table are being filtered using the
[fuzzy matching][1] algorithm. The arrow means that ranking based ordering is
being applied, i.e. [sorters][2] are being ignored.

## Node Searcher Applicable

Node Searcher contains the following fields:

- [pattern][3]
- [recoverable_focus][4]
- [algorithm][5]
- [unordered][7]

### pattern

The patters used to search.

Type: string

### recoverable_focus

Where to focus when search is cancelled.

Type: nullable string

### algorithm

Search algorithm to use. Defaults to `Fuzzy`.

It can be one of the following:

- Fuzzy
- Regex

### unordered

Whether to skip ordering the search result by algorithm based ranking. Defaults
to `false`.

Type: boolean

## Example:

```lua
local searcher = {
  pattern = "pattern to search",
  recoverable_focus = "/path/to/focus/on/cancel",
  algorithm = "Fuzzy",
}

xplr.util.explore({ searcher = searcher })
```

See [xplr.util.explore][6]

[1]: https://en.wikipedia.org/wiki/Approximate_string_matching
[2]: sorting.md
[3]: #pattern
[4]: #recoverable_focus
[5]: #algorithm
[6]: xplr.util.md#explore
[7]: #unordered
