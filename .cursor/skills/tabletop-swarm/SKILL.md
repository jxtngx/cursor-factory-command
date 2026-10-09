---
name: tabletop-swarm
description: "Example campaign: Reachy Mini-class expressive desktop, MicroDuck-class biped, optional swarm. VLA and RL in deep-learning-factory. Use with @init-campaign tabletop-swarm."
---

# Tabletop swarm

References, not sources to vendor:

- https://huggingface.co/docs/reachy_mini/en/index
- https://pollen-robotics.com/microduck/

## Units

- Expressive desktop: camera, mics, speaker, Stewart-like head, MuJoCo
- Biped: ~15 DoF, camera, depth, dual IMU, 50 Hz policy, MuJoCo RL
- Swarm: N units, langchain-factory coordination, VLA from deep-learning-factory

## Plants

Staff deep-learning-factory for sim and policy.
Staff langchain-factory for the swarm graph.
Do not staff cursor-ros2-factory, cursor-zephyr-factory, cursor-kotlin-factory, or cursor-cesium-factory.

## Policy

- Biped: RL sim2real (PPO-class) then optional VLA on top
- Desktop: scripted + VLA for interaction
- Swarm: shared VLA or role-split policies plus a mission graph
