# Route Slice

Send one campaign slice to one plant. Engineering owns the call.

## Usage

```
@route-slice <slice-id>
```

## MUST

- Confirm the slice exists in `routes.md`
- Restate plant, kind (lab|factory|tool), next command
- If lab: `@start-lesson` and the lesson id
- If factory: the plant's `@init-*` and which requirements file to copy
- Stop

## MUST NOT

- Do the slice
