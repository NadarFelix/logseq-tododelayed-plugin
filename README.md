# Delayed TODO

A Logseq plugin that adds a start date to a block. The block stays without a task marker until that date, then is automatically converted into a `TODO`.

## Usage

1. Place the cursor in a block.
2. Type `/TODO-delayed`.
3. Pick a start date in the date picker. It must be later than today.
4. Confirm. The property `todostart:: YYYY-MM-DD` is added to the block.

You can also add the property manually:

```text
Write the report
todostart:: 2026-11-01
```

## Behavior

- On or after the start date, the block content is prefixed with `TODO `.
- Blocks that already start with `TODO`, `DOING`, `DONE`, `NOW` or `LATER` are left unchanged.
- The check runs:
  - when the plugin loads,
  - when the graph changes or finishes indexing,
  - every hour,
  - at midnight (00:00:05).
- Logseq must be running for the conversion to happen.

## Limitations

- The plugin loads `@logseq/libs` from a CDN, so an internet connection is required.
- The date picker interface is currently in French, because it's so romantic, isn't it ?

## Compatibility

Logseq 0.10.15+ (file-based Markdown graphs).
