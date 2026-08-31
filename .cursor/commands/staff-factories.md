# Staff Factories

After an approved campaign spec, assign plants and owners.

## Usage

```
@staff-factories [slug]
```

## MUST

1. Read `campaign-spec.md`
2. `factory-engineering` writes `campaigns/<slug>/routes.md`
3. ROS 2 slices → cursor-ros2-factory `@init-robot`
4. Zephyr slices → cursor-zephyr-factory `@init-firmware`
5. Grok / Cursor SDK slices → cursor-grok-factory `@init-grok` (user chooses pairing there)
6. For each factory slice: plant repo, init command, spec pointer
7. CUDA slices only: cursor-cuda-lab, `@start-lesson`, human writes
8. List clone paths the user must have locally
9. Do not run those inits here; tell the user which repo to open next

## MUST NOT

- Implement in this repo
- Route shipping ROS 2 or Zephyr to a lab
