---
layout: "functions"
page_title: "tolist - Functions - Configuration Language"
sidebar_current: "docs-funcs-conversion-tolist"
description: |-
  The tolist function converts a value to a list.
---

# `tolist` Function

`tolist` converts its argument to a list value.

Explicit type conversions are rarely necessary in Terraform because it will
convert types automatically where required. Use the explicit type conversion
functions only to normalize types returned in module outputs.

## Examples

```
> tolist(["a", "b", "c"])
[
  "a",
  "b",
  "c",
]
```

Since Terraform's concept of a list requires all of the elements to be of the
same type, mixed-typed elements will be converted to the most general type:

```
> tolist(["a", "b", 3])
[
  "a",
  "b",
  "3",
]
```
