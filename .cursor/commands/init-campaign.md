# Init Campaign

Open Factory Ops. Discover the mission. Freeze a spec. Do not staff plants yet.

## Usage

```
@init-campaign [tabletop-swarm | slug]
```

Default slug: `tabletop-swarm`.

## MUST

1. Run as `factory-ops`
2. If `campaigns/<slug>/MISSION.md` exists, read it and interview deltas
3. Ask units, sim vs hardware, Zephyr, ROS 2, RL vs VLA, swarm N, UI surfaces, train box
4. Write `campaigns/<slug>/campaign-spec.md` from the template
5. Call `factory-engineering` for a route table (draft)
6. Stop. Wait for the user to approve. Then they `@staff-factories`

## MUST NOT

- Clone reachy_mini or microduck
- Open a factory and start coding
- Require a purchased robot
