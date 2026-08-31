---
name: tabletop-swarm
description: "Example campaign: Reachy Mini-class expressive desktop, MicroDuck-class biped, optional swarm. VLA, ROS 2, Zephyr sensors. Use with @init-campaign tabletop-swarm."
---

# Tabletop swarm

References, not sources to vendor:

- https://huggingface.co/docs/reachy_mini/en/index
- https://pollen-robotics.com/microduck/

## Units

- Expressive desktop: camera, mics, speaker, Stewart-like head, MuJoCo, ROS 2
- Biped: ~15 DoF, camera, depth, dual IMU, 50 Hz policy, MuJoCo RL, ROS 2
- Swarm: N units, agent-factory coordination, VLA from deep-learning-factory

## Firmware guess

Sensor boards (IMU, ToF, mic array) may be Zephyr. Do not assume the Pi/CM4 is Zephyr.
cursor-rtos-lab is sim-first (`native_sim`).

## Policy

- Biped: RL sim2real (PPO-class) then optional VLA on top
- Desktop: scripted + VLA for interaction
- Swarm: shared VLA or role-split policies plus a mission graph
