---
name: init-campaign
description: Init Campaign
disable-model-invocation: true
---

# Init Campaign

Open Factory Ops. Discover the mission. Freeze a spec. Do not staff plants yet.

## Usage

```
@init-campaign [slug]
```

No default slug. If omitted, ask for one.

## MUST

1. Run as `factory-ops`
2. If `campaigns/<slug>/` already exists, read it and interview deltas
3. Ask for the product in one sentence, which plants, and one falsifier
4. Write `campaigns/<slug>/campaign-spec.md` from the template
5. Call `factory-engineering` for a route table (draft)
6. Stop. Wait for the user to approve. Then they `@staff-factories`

## MUST NOT

- Propose a product, a domain, or a reference design
- Vendor a third-party tree
- Open a factory and start coding
