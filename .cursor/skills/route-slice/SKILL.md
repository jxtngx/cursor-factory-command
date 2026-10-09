---
name: route-slice
description: Route Slice
disable-model-invocation: true
---

# Route Slice

Send one campaign slice to one plant. Engineering owns the call.

## Usage

```
@route-slice <slice-id>
```

## MUST

- Confirm the slice exists in `routes.md`
- Restate plant, kind (factory or train box), next command
- If factory: the plant's `@init-*` and which requirements file to copy
- If dgx-lab: the train job the spec named
- Stop

## MUST NOT

- Do the slice
