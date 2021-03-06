---
title: json
type: condition
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/condition/json.go
-->


Checks JSON messages against a logical [operator](#operators) and an argument.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
# Common config fields, showing default values
json:
  operator: exists
  path: ""
  arg: ""
```

</TabItem>
<TabItem value="advanced">

```yaml
# All config fields, showing default values
json:
  operator: exists
  path: ""
  arg: ""
  part: 0
```

</TabItem>
</Tabs>

## Fields

### `operator`

A logical [operator](#operators) to check with.


Type: `string`  
Default: `"exists"`  
Options: `exists`, `equals`, `contains`.

### `path`

The [path](/docs/configuration/field_paths) of a specific field within JSON documents to check.


Type: `string`  
Default: `""`  

### `arg`

An argument to check against. May not be applicable for all operators.


Type: `string`  
Default: `""`  

### `part`

The index of a message within a batch to test the condition against. This
field is only applicable when batching messages
[at the input level](/docs/configuration/batching).

Indexes can be negative, and if so the part will be selected from the end
counting backwards starting from -1.


Type: `number`  
Default: `0`  

## Operators

### `exists`

Checks whether the target path exists within a document. If the path is the root
(empty or '.') then it simply checks that the document is valid JSON.

### `equals`

Checks whether the target path exists and matches the argument.

### `contains`

Checks whether the target path is an array containing the argument.

