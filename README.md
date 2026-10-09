# Cursor Factory Command

Command and control for the Cursor **factory fleet**.
This repo is the **Factory Directorate**. It does not ship a robot.
It interviews you, freezes a campaign spec, and **staffs the plants**.

> **Ops** talks to you. **Engineering** talks to the factories.
> Neither implements the product.

Example campaign in this checkout: **tabletop swarm** — legally distinct
recreations in the class of [Reachy Mini](https://huggingface.co/docs/reachy_mini/en/index)
and [Pollen MicroDuck](https://pollen-robotics.com/microduck/). Desktop expressive
unit, biped RL unit, optional swarm. Policies and VLAs train in
PyTorch / Hugging Face. Coordination is a LangGraph agent.

---

## What this is

| This repo | Not this repo |
| --- | --- |
| C2 harness | A `cursor-*-factory` that implements tickets |
| Directorate of two | A plant's Chief Architect |
| Routes work | Copies Pollen/HF CAD or their SDK |

Plants it commands (you clone those separately):

| Plant | Kind | Slice it gets on the example mission |
| --- | --- | --- |
| [cursor-deep-learning-factory](https://github.com/jxtngx/cursor-deep-learning-factory) | factory | VLA / policy train and finetune. **Team implements.** |
| [cursor-langchain-factory](https://github.com/jxtngx/cursor-langchain-factory) | factory | Swarm / mission agent (LangChain + LangSmith). **Team implements.** |
| [cursor-grok-factory](https://github.com/jxtngx/cursor-grok-factory) | factory | Grok + Cursor SDK product. **Team implements.** `@init-grok` |
| [cursor-fullstack-factory](https://github.com/jxtngx/cursor-fullstack-factory) | factory | Teleop, fleet dashboard. **Team implements.** |
| [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory) | factory | Optional iOS gamepad / companion. **Team implements.** |
| [cursor-extension-factory](https://github.com/jxtngx/cursor-extension-factory) | factory | Optional Cursor/VS Code robot panel. **Team implements.** |
| [dgx-lab](https://github.com/jxtngx/dgx-lab) | train box | NVIDIA DGX Spark as the train box |

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

Default example if you have no other mission: **tabletop-swarm**
([campaigns/tabletop-swarm/MISSION.md](campaigns/tabletop-swarm/MISSION.md)).

Then:

```
@staff-factories
@route-slice
@status
```

---

## Example mission (tabletop swarm)

Public references (do not paste their trees):

- [Reachy Mini docs](https://huggingface.co/docs/reachy_mini/en/index) — expressive desktop, Pi CM4 (wireless), camera, 4 mics, speaker, Dynamixel Stewart head, [MuJoCo sim](https://huggingface.co/docs/reachy_mini/en/platforms/simulation/get_started)
- [MicroDuck](https://pollen-robotics.com/microduck/) — 25 cm biped, 15 motors, camera, LiDAR/ToF, two IMUs, 50 Hz policy, [sim2real](https://github.com/pollen-robotics/microduck)

Our recreation is **class-compatible**, not a clone. New names, new CAD if you print.

| Unit | Class | Stack Command staffs |
| --- | --- | --- |
| Expressive desktop | Reachy Mini-class | MuJoCo sim and interaction policy in deep-learning-factory |
| Biped | MicroDuck-class | MuJoCo RL, 50 Hz policy export, deep-learning-factory |
| Swarm | N of either | [cursor-langchain-factory](https://github.com/jxtngx/cursor-langchain-factory) + VLA from [cursor-deep-learning-factory](https://github.com/jxtngx/cursor-deep-learning-factory) |

Hardware purchase is optional. Sim-first is the default gate.

## Contract

**Ops may:** interview, write `campaigns/<name>/campaign-spec.md`, refuse to staff, reassign an SME.

**Ops must not:** implement tickets, pick a motor bus to look busy.

**Engineering may:** map slices to plants, reject a route outside the staffed factories and dgx-lab, require sim-first.

**Engineering must not:** replace a plant's Chief Architect, sneak-implement a VLA or a dashboard.

Definition of done for Command: every slice has a plant, a spec pointer, and a factory owner. The robot moving is **not** this repo's done.

## Daily loop

1. `@init-campaign` (or reopen `campaigns/tabletop-swarm/`)
2. Approve the spec
3. `@staff-factories` — clones/paths, who owns which slice
4. Work in the plants (you spec; the factory team implements)
5. `@status` here as the single board

## Harness

- **`.cursor/agents/`** — factory-ops, factory-engineering
- **`.cursor/commands/`** — `@init-campaign`, `@staff-factories`, `@route-slice`, `@status`
- **`.cursor/rules/`** — C2 only, factories and dgx-lab only, official robot docs as references
- **`campaigns/`** — one folder per mission
