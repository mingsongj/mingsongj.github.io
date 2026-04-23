---
layout: page
title: LUART — Amphibious Robotic Turtle
description: Surrogate compliance modeling enables reinforcement-learned locomotion gaits for a soft-rigid hybrid turtle robot
img: assets/img/luart_cover.png
importance: 4
category: research
---

This project is joint work I led with Jue Wang at Yale's Faboratory (Prof. Rebecca Kramer-Bottiglio), building **LUART** — a Learning Untethered Amphibious Robotic Turtle. LUART is a soft-rigid hybrid quadruped with variable-stiffness, shape-morphing limbs that can switch between a cylindrical "tortoise leg" for firm ground and a hydrofoil-like "sea-turtle flipper" for deformable terrain. The core contribution is a method we call **surrogate compliance modeling**: instead of simulating the soft limbs with expensive finite-element physics, we represent their deformation as a small set of indirect variables — effective limb length and limb center of mass — inside a standard rigid-body simulator, then train locomotion policies with reinforcement learning under aggressive randomization over those variables. The resulting closed-loop gaits transfer directly to hardware and achieve an order-of-magnitude reduction in cost of transport over previous hand-designed open-loop baselines.

<p align="center">
<img src="{{ '/assets/img/luart_cover.png' | prepend: site.baseurl }}" width="85%" />
</p>
<p align="center">
<em><b>LUART concept: one robot, two limb modes — rigid columnar legs for flat terrain, compliant flippers for gravel, mud, and grass — with a single RL-trained policy that adapts.</b></em>
</p>

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Why this matters</p>

Most soft and soft-rigid robots still run on open-loop, hand-tuned gaits because accurate soft-body simulation is too slow for large-scale RL. We sidestep that: by capturing only the *mechanical consequences* of compliance (how long is the limb really, where is its mass) rather than full soft-body physics, we make RL tractable in a rigid-body simulator (Genesis) and still get policies that hold up in the real world — including on rheologically complex substrates like mud and wet grass.

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Sim-to-real comparison</p>

<p align="center">
<video width="720" height="405" controls>
  <source src="{{ '/assets/video/luart_sim2real.mp4' | prepend: site.baseurl }}" type="video/mp4">
</video>
</p>
<p align="center">
<em><b>Side-by-side of the learned policy in Genesis vs. the physical robot on flat ground. Velocity-mapping error is below 6% across walking, backward walking, lateral motion, and in-place turning.</b></em>
</p>

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Gait and limb-mode switching</p>

<p align="center">
<video width="720" height="405" controls>
  <source src="{{ '/assets/video/luart_gait_change.mp4' | prepend: site.baseurl }}" type="video/mp4">
</video>
</p>
<p align="center">
<em><b>A single policy handles the transition between upright walking (rigid limbs, inflated pouch) and low-profile crawling (soft limbs, deflated pouch) by changing only the body-height command.</b></em>
</p>

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Multi-terrain field tests</p>

<p align="center">
<video width="720" height="405" controls>
  <source src="{{ '/assets/video/luart_terrains.mp4' | prepend: site.baseurl }}" type="video/mp4">
</video>
</p>
<p align="center">
<em><b>LUART navigating concrete, mud, grass, gravel, and streambed terrain in field trials at Yale and East Rock Park. Adaptive limb/gait switching keeps cost of transport roughly half of pure rigid-limb crawling across all terrains.</b></em>
</p>

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Behind the scenes</p>

<p align="center">
<img src="{{ '/assets/img/luart_robot_inside.jpg' | prepend: site.baseurl }}" width="48%" style="margin-right: 1%;" />
<img src="{{ '/assets/img/luart_robot_black.jpg' | prepend: site.baseurl }}" width="48%" />
</p>
<p align="center">
<em><b>Left: the robot guts — Jetson Orin Nano, dual LiPo batteries, Dynamixel XH joints, and the pneumatic PCB that drives pouch inflation and jamming. Right: assembled platform with morphing limbs mounted.</b></em>
</p>

<p align="center">
<img src="{{ '/assets/img/luart_field.jpg' | prepend: site.baseurl }}" width="48%" style="margin-right: 1%;" />
<img src="{{ '/assets/img/luart_team_field.jpg' | prepend: site.baseurl }}" width="48%" />
</p>
<p align="center">
<em><b>Field testing along a muddy creek bank in New Haven (left) and with co-first-author Jue Wang during an outdoor run (right). ArUco markers on the shell were used for ground-truth pose when GPS resolution wasn't enough.</b></em>
</p>

<p align="center">
<img src="{{ '/assets/img/luart_team_robot.jpg' | prepend: site.baseurl }}" width="70%" />
</p>
<p align="center">
<em><b>The Faboratory turtle team after the Yale Engineering feature.</b></em>
</p>

<p align="center">
<img src="{{ '/assets/img/luart_yale_ins.jpg' | prepend: site.baseurl }}" width="50%" />
</p>
<p align="center">
<em><b>Coverage on @yaleengineering's Instagram featuring the Faboratory and the field deployment.</b></em>
</p>

<p align="center">
<img src="{{ '/assets/img/luart_gtc.jpg' | prepend: site.baseurl }}" width="60%" />
</p>
<p align="center">
<em><b>NVIDIA GTC 2026 in San Jose — sharing the RL + Genesis simulation stack that powered LUART.</b></em>
</p>

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Key results</p>

- **Sim-to-real fidelity**: velocity mapping error 2.29%–7.76% (mean 5.29%) on flat, rigid terrain for walking; 1.00%–5.20% (mean 3.41%) for crawling.
- **Gait repertoire**: forward/backward walking and crawling, omnidirectional translation, in-place turning (CW/CCW), figure-eight curve turns, and dynamic walk↔crawl transitions — all from a single learned policy.
- **Energetics**: an order-of-magnitude reduction in cost of transport compared to our previous open-loop ART, across flat ground, mud, grass, and gravel.
- **Field robustness**: multi-terrain courses on concrete, mud, grass, gravel, rain-softened soil, and streambeds; navigates under obstacles, climbs curbs, and reorients with its backward gait in confined spaces.

<p style="font-size: 1.17em; font-weight: bold; margin-top: 28px; margin-bottom: 10px;">Publication</p>

1. J. Wang*, <b>M. Jiang*</b>, L. A. Ramirez, B. Yang, M. Zhang, E. Figueroa, W. Yan, R. Kramer-Bottiglio, "Surrogate compliance modeling enables reinforcement learned locomotion gaits for soft robots," 2025. *Equal contribution. <a href="/assets/pdf/luart.pdf" target="_blank">[pdf]</a> <a href="https://github.com/the-faboratory/LUART" target="_blank">[code]</a>
