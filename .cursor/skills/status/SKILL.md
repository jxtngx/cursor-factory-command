---
name: status
description: Status
disable-model-invocation: true
---

# Status

Single board for the campaign. Ops presents it.

## Usage

```
@status [slug]
```

## MUST

Table: slice, plant, kind, owner, state (spec / in-factory / blocked / done).
A blocker that lives outside this repo is not a Command blocker.

## MUST NOT

- Mark a factory slice done because the spec exists
