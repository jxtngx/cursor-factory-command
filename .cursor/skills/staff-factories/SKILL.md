---
name: staff-factories
description: Staff Factories
disable-model-invocation: true
---

# Staff Factories

After an approved campaign spec, assign plants and owners.

## Usage

```
@staff-factories [slug]
```

## MUST

1. Read `campaign-spec.md`
2. `factory-engineering` writes `campaigns/<slug>/routes.md`
3. Grok / Cursor SDK slices → cursor-grok-factory `@init-grok` (user chooses pairing there)
4. For each factory slice: plant repo, init command, spec pointer
5. Train box: dgx-lab when the spec names DGX Spark
6. List clone paths the user must have locally
7. Do not run those inits here; tell the user which repo to open next

## MUST NOT

- Implement in this repo
- Staff cursor-ros2-factory, cursor-zephyr-factory, cursor-kotlin-factory, or cursor-cesium-factory
