---
layout: about
title: About
permalink: /
subtitle: jason123jms@gmail.com

profile:
  align: right
  image: myself_3.jpg
  image_circular: false # crops the image to make it circular
  address: >
           <p align="center">
           mingsongj.github.io
           </p>


news: false  # includes a list of news items
selected_papers: false  # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---


[google scholar](https://scholar.google.com/citations?user=1u-F3DUAAAAJ&hl=en)

My work began in **soft robotics and human–robot interaction**, exploring how materials, structures, and algorithms can make robots more adaptive and responsive to human needs. This experience shaped my view of intelligence: what matters is not only what a system can do, but how safely, naturally, and meaningfully it works with people.

That perspective now guides my work on **the next generation of AI companions**—systems that understand people’s needs and routines, offer companionship, and quietly help manage everyday life. At **Mosai Robotics**, which I founded in 2026, I am developing **AI companion agents and an app for older adults**, bringing my experience in human-centered robotics toward a broader goal: making AI a more personal, attentive, and helpful presence in people’s lives.

<br/>

### Current Position

**Founder & CEO**, Mosai Robotics (Shenzhen) · 2026.2 – present
- Building AI companion agents and an app for older adults—offering companionship, understanding their needs and routines, and quietly helping manage everyday life.
- Open to early technical co-founders and angel investors.

### Previous Positions

**Innovation Lab Director** (UV product line lead), Creality · 2025.4 – 2026.1
- Built a 13-person cross-disciplinary lab from scratch and delivered two generations of desktop UV-printer prototypes, with self-developed low-viscosity stackable UV ink enabling 2.5D/3D relief printing and an AIGC + 3D-slicing fabrication pipeline.

**Postdoctoral Associate**, Yale University · 2023.4 – 2025.4
- With [Rebecca Kramer-Bottiglio](https://seas.yale.edu/faculty-research/faculty-directory/rebecca-kramer-bottiglio) at the [Yale Faboratory](https://www.eng.yale.edu/faboratory/). Co-first author on **LUART**, an amphibious turtle robot with morphing limbs whose sim-trained PPO policies transfer to hardware and outdoor terrain. See the [project page](/projects/4_project/).

**Robotics Systems Design Specialist**, XPeng Robotics · 2022.3 – 2022.6
- System architecture, Mujoco-based locomotion simulation, and product definition for the PX3 four-legged rideable robot.

### Education

**Ph.D., Mechanical Engineering**, UC San Diego · 2018 – 2021
- Thesis: *Towards Reconfigurable and Adaptive Soft Robots via Hybrid Materials, Designs and Mechanisms*. Advisor: [Nicholas Gravish](http://web.eng.ucsd.edu/~ngravish/) ([Gravish Lab](http://gravishlab.ucsd.edu/)).

**M.S., Mechanical Engineering**, UC San Diego · 2016 – 2018
- Thesis: *Sliding-layer laminates: a new robotic material enabling robust and adaptable undulatory locomotion*. Advisor: Nicholas Gravish.

**B.S., Mechanical Engineering**, Xi'an Jiaotong University · 2012 – 2016
- Thesis: *Design and fabrication of a 3D printed rehabilitative and wearable hand exoskeleton*. Advisor: Jing Wang.

### Recognition & Service

- 2025 National QM Talent Program awardee (Shenzhen Longhua recommendation), 2026.01
- Shenzhen Longhua District Class-C High-Level Talent
- Adjunct Advisor, School of Advanced Manufacturing, Sun Yat-sen University
- Best Paper Nominee, IEEE RoboSoft 2021
- Lead Teaching Assistant, MAE 207 Bio-inspired Mobile Robotics, UC San Diego (2018–2020)

<br/>

### Projects

<div class="projects">
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
</div>
