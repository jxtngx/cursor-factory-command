# Status

Single board for the campaign. Ops presents it.

## Usage

```
@status [slug]
```

## MUST

Table: slice, plant, kind, owner, state (spec / in-lab / in-factory / blocked / done).
Blockers that are "waiting on a robot in the mail" are not blockers if sim is green.

## MUST NOT

- Mark a lab slice done because an agent offered a node
- Mark a factory slice done because the spec exists
