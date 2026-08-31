# Staff Factories

After an approved campaign spec, assign plants and owners.

## Usage

```
@staff-factories [slug]
```

## MUST

1. Read `campaign-spec.md`
2. `factory-engineering` writes `campaigns/<slug>/routes.md`
3. For each factory slice: name the plant repo, the init command (`@init-agent`, `@launch-product-discovery`, …), and the spec pointer
4. For each lab slice: name the lab, the starting lesson, and that the **human** writes the code
5. List clone paths the user must have locally
6. Do not run those inits here; tell the user which repo to open next

## MUST NOT

- Implement in this repo
- Skip lab slices by "we'll just use Python ROS"
