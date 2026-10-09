# Cursor Factory Command

Command and control for the Cursor **factory fleet**.
This repo is the **Factory Directorate**. It does not implement the product.
It interviews you, freezes a campaign spec, and **staffs the plants**.

> **Ops** talks to you. **Engineering** talks to the factories.
> Neither implements the product.

---

## What this is

| This repo | Not this repo |
| --- | --- |
| C2 harness | A `cursor-*-factory` that implements tickets |
| Directorate of two | A plant's Chief Architect |
| Routes work | A product spec written in advance |

Plants it commands (you clone those separately):

| Plant | Kind | What it is |
| --- | --- | --- |
| [cursor-deep-learning-factory](https://github.com/jxtngx/cursor-deep-learning-factory) | factory | PyTorch / Hugging Face. **Team implements.** |
| [cursor-langchain-factory](https://github.com/jxtngx/cursor-langchain-factory) | factory | LangChain. **Team implements.** |
| [cursor-grok-factory](https://github.com/jxtngx/cursor-grok-factory) | factory | Grok + Cursor SDK. **Team implements.** `@init-grok` |
| [cursor-fullstack-factory](https://github.com/jxtngx/cursor-fullstack-factory) | factory | Fullstack app. **Team implements.** |
| [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory) | factory | Swift app. **Team implements.** |
| [cursor-extension-factory](https://github.com/jxtngx/cursor-extension-factory) | factory | Cursor / Open VSX extension. **Team implements.** |
| [dgx-lab](https://github.com/jxtngx/dgx-lab) | train box | NVIDIA DGX Spark |

---

## Directorate

| Agent | Title | Face |
| --- | --- | --- |
| `factory-ops` | Director of Factory Ops | You. Discovery, campaign freeze, staffing. |
| `factory-engineering` | Director of Factory Engineering | The plants. Routing, harness, ship-readiness. |

`@init-campaign` always opens **ops** first. Ops pulls engineering when the spec has to survive a real plant.

## First command

```
@init-campaign
```

You name the campaign. There is no sample mission in this repo.

Then:

```
@staff-factories
@route-slice
@status
```

## Contract

**Ops may:** interview, write `campaigns/<name>/campaign-spec.md`, refuse to staff, reassign an SME.

**Ops must not:** implement tickets, invent a product you did not name.

**Engineering may:** map slices to plants, reject a route outside the staffed factories and dgx-lab.

**Engineering must not:** replace a plant's Chief Architect, implement the product here.

Definition of done for Command: every slice has a plant, a spec pointer, and a factory owner. Shipping the product is **not** this repo's done.

## Daily loop

1. `@init-campaign` (or reopen `campaigns/<slug>/`)
2. Approve the spec
3. `@staff-factories` — clones/paths, who owns which slice
4. Work in the plants (you spec; the factory team implements)
5. `@status` here as the single board

## Harness

- **`.cursor/agents/`** — factory-ops, factory-engineering
- **`.cursor/commands/`** — `@init-campaign`, `@staff-factories`, `@route-slice`, `@status`
- **`.cursor/rules/`** — C2 only, factories and dgx-lab only
- **`campaigns/`** — one folder per mission, written at init
