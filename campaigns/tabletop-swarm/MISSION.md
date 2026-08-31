# Mission — tabletop swarm

Recreate, as a **class**, two public desktop robots and optionally swarm them.

This folder is C2 artifacts (spec, routes, status). Bodies, firmware, and weights live in the staffed plants.

## References (read, do not vendor)

| Class | Public product | Docs |
| --- | --- | --- |
| Expressive desktop | Hugging Face / Pollen Reachy Mini | [docs](https://huggingface.co/docs/reachy_mini/en/index) · [hardware](https://huggingface.co/docs/reachy_mini/en/platforms/reachy_mini/hardware) · [sim](https://huggingface.co/docs/reachy_mini/en/platforms/simulation/get_started) |
| Biped | Pollen MicroDuck | [product](https://pollen-robotics.com/microduck/) · [github](https://github.com/pollen-robotics/microduck) |

Our units get **new names** in `campaign-spec.md`. Apache-2.0 for our software. Do not ship their NC hardware files.

## Why this mission exists

It stresses the whole fleet in one campaign:

| Need | Where Command sends it |
| --- | --- |
| ROS 2 graph, cameras, tf, control | [cursor-robotics-lab](https://github.com/jxtngx/cursor-robotics-lab) (you type C++20) |
| Sensor MCU (IMU, ToF, maybe mics) | [cursor-rtos-lab](https://github.com/jxtngx/cursor-rtos-lab) (Zephyr on `native_sim` first) |
| VLA and/or RL policy, MuJoCo, HF | [cursor-deep-learning-factory](https://github.com/jxtngx/cursor-deep-learning-factory) |
| CUDA if the VLA path needs kernels | [cursor-cuda-lab](https://github.com/jxtngx/cursor-cuda-lab) |
| Swarm / mission agent | [cursor-agent-factory](https://github.com/jxtngx/cursor-agent-factory) |
| Teleop + fleet view | [cursor-fullstack-factory](https://github.com/jxtngx/cursor-fullstack-factory) |
| Optional phone gamepad | [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory) |
| Train box | [dgx-lab](https://github.com/jxtngx/dgx-lab) |

Pollen's MicroDuck onboard stack is Rust daemons, not ROS. **Our recreation standardizes on ROS 2** so the robotics lab is the body interface. Policy loops may still be 50 Hz sidecar processes that speak ROS.

Reachy Mini wireless is a Pi CM4, camera IMX708, 4 PDM mics, Dynamixel Stewart platform. **Our desktop unit** matches that *class* (expressive head, vision, audio), not their mesh.

## Suggested slices (engineering will rewrite after interview)

1. `sim-desktop` — MuJoCo model + ROS 2 bringup (lab)
2. `sim-biped` — MuJoCo biped + 50 Hz dummy policy (lab + factory)
3. `zephyr-imu` — IMU/ToF sample on native_sim (lab)
4. `policy-biped` — RL train, ONNX or Torch export (factory)
5. `vla-desktop` — HF VLA finetune on interaction data (factory)
6. `swarm-agent` — LangGraph mission over N robots (factory)
7. `teleop` — fullstack dashboard (factory)

Sim-first. A slice that needs a SKU in a warehouse is stretch.

## Start

```
@init-campaign tabletop-swarm
```
