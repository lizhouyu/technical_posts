---
title: "Thermal-aware policies stretch robot runtime; leak responses go automatic; TVA prices the megawatt"
date: 2026-11-27 08:30:00 +0800
categories: [Daily Brief, Robot Computing, Digital Twins, Power]
tags: [robot-computing, energy, thermal, quadruped, humanoid, rack-ops, liquid-cooling, grid, tariff, industry, academia]
description: "Thermal-aware RL keeps a Unitree Go2 running 174 minutes at 5 kg payload where a baseline shuts down at 19, and temperature pacing carried a G1 humanoid through 100–1,500 m races. NVIDIA Mission Control automates leak response and rack power and cooling telemetry over MQTT. Liquid cooling's best-practice PUE lands at 1.07–1.08, and TVA's large-load tariff prices capacity at about USD 1.5 million per MW above 5 MW."
---

## At a glance

- **Robot heat is now a control variable.** Two [reinforcement-learning](https://en.wikipedia.org/wiki/Reinforcement_learning "Reinforcement learning (RL): training a policy from reward; neither policy observes temperature at deployment.") policies manage motor heat: one ends a quadruped's run at the battery limit, not thermal shutdown; the other paces a racing humanoid by temperature.
- **Rack physics is becoming software policy.** NVIDIA Mission Control automates leak response, electrical isolation and rack power and cooling telemetry into building systems.
- **Grid access has sticker prices.** TVA's first disclosed data-center cohort deal totals USD 1.7 billion at about USD 1.5 million per MW above 5 MW.

## Key developments

### 1. A policy that never senses temperature still ends runs at the battery, not the thermal limit · submitted 17 Nov 2026 · academia / robot thermal

Ségas, Opra, Ghafari and Stewart (arXiv [2611.22231](https://arxiv.org/abs/2611.22231 "Ségas et al., From Temperature-Limited to Battery-Limited Legged Locomotion, arXiv 2611.22231, submitted 17 November 2026. A preprint, not peer reviewed.")) fit a 13-node thermal [RC network](https://en.wikipedia.org/wiki/Lumped_capacitance_model "Lumped-capacitance (RC) model: a resistor-capacitor analog of heat flow, here predicting motor temperatures.") to a [Unitree Go2](https://www.unitree.com/ "Unitree Go2: a consumer quadruped; the paper's platform.") from two runs; it predicts all twelve motor temperatures to under 1 °C mean error across robots, gaits and payloads. Predicted settling temperatures respond within one gait cycle, so a reward that pushes down the hottest motor's predicted steady state works without a temperature sensor. At 5 kg payload and 1 m/s, a baseline hits thermal shutdown at 19 minutes (1.1 km); the trained policy runs 174 minutes (10.0 km) to battery depletion, 14 °C below the limit. A factory circuit goes from 6.2 to 11.2 km per battery.

Implication: Heat, not charge, ends sustained legged missions; a cheap thermal model plus reward shaping moves the constraint.

**Sources:** [arXiv 2611.22231](https://arxiv.org/abs/2611.22231 "Abstract and record."); [Zenodo dataset](https://doi.org/10.5281/zenodo.24274994 "Public dataset.").

### 2. In humanoid racing, thermal margin set the pace · submitted 17 Nov 2026 · academia / robot thermal

Inami and colleagues ran a [Unitree G1](https://www.unitree.com/ "Unitree G1: a general-purpose commercial humanoid; the paper's platform."), fully autonomous, in the 100 m, 400 m and 1,500 m races of the World Humanoid Robot Games 2026, finishing 13th of 74, 10th of 44 and 7th of 35 (arXiv [2611.22445](https://arxiv.org/abs/2611.22445 "Inami et al., Autonomous Track Racing with a Commercially Available Humanoid, arXiv 2611.22445, submitted 17 November 2026. A preprint; submitted to IEEE Robotics and Automation Practice.")). Lane perception, path tracking and an RL running policy are wrapped in thermal management: a hip-torque penalty in training, heat-dissipation plates, and temperature-based speed limiting with event-specific pacing. Their conclusion: "thermal margin set the pace in every event"; the semifinal fall was a lane-detection error.

Implication: Humanoid athletics is thermal scheduling, the margin arithmetic that sets a GPU's sustainable clock.

**Source:** [arXiv 2611.22445](https://arxiv.org/abs/2611.22445 "Abstract: placements, thermal measures, and the pacing statement.").

### 3. Leak response moves from runbook to policy engine · 19 Nov 2026 · industry / rack power and cooling

NVIDIA's [Mission Control](https://developer.nvidia.com/blog/manage-liquid-cooled-ai-factories-with-nvidia-mission-control/ "NVIDIA Technical Blog, 19 November 2026.") documentation shows liquid-cooled [GB200/GB300 NVL72](https://www.nvidia.com/en-us/data-center/gb300-nvl72/ "NVIDIA GB300 NVL72: a liquid-cooled 72-GPU rack-scale system.") [SuperPOD](https://www.nvidia.com/en-us/data-center/dgx-superpod/ "NVIDIA DGX SuperPOD: NVIDIA's reference liquid-cooled cluster architecture.") racks wired to [building management systems](https://en.wikipedia.org/wiki/Building_automation "Building management system (BMS): the facility-side controller for power, cooling and safety.") over [MQTT](https://en.wikipedia.org/wiki/MQTT "MQTT: a lightweight publish/subscribe protocol common in building automation."). Hierarchical leak-action policies (device, rack, row, room, building) power off, electrically isolate and close liquid valves automatically, by scope and affected-device count. Rack commands report circuit loads against budget, supply and return temperatures, flow, differential pressure and isolation state, exported as [Prometheus](https://prometheus.io/ "Prometheus: an open monitoring system and metrics format.") metrics.

Implication: When valves and breakers answer software policy, capping designs must be leak- and isolation-aware, not just setpoints.

**Source:** [NVIDIA Technical Blog, 19 Nov](https://developer.nvidia.com/blog/manage-liquid-cooled-ai-factories-with-nvidia-mission-control/ "Primary documentation post.").

### 4. Liquid cooling's energy and water arithmetic, globally · submitted 18 Nov 2026 · academia / cooling

Zhang, Masanet and Wang (arXiv [2611.23903](https://arxiv.org/abs/2611.23903 "Zhang, Masanet and Wang, AI Surge Accelerates the Transition to Liquid Cooling, arXiv 2611.23903, submitted 18 November 2026. A preprint, not peer reviewed.")) model the global shift to [liquid cooling](https://en.wikipedia.org/wiki/Data_center#Cooling "Liquid cooling: cooling IT equipment with liquid rather than air."): 25-56% lower cooling energy than air, best-practice [PUE](https://en.wikipedia.org/wiki/Power_usage_effectiveness "PUE: facility power divided by IT power.") of 1.07-1.08 today and 1.03-1.04 emerging, [WUE](https://en.wikipedia.org/wiki/Data_center#Energy_use "WUE: water use per kilowatt-hour of IT energy.") of 0.38-2.63 L/kWh, and free-cooling rack-inlet thresholds of 33 °C (evaporative) and 49 °C (dry), making 100% free cooling practical in many places. Caveat: minimum PUE is not minimum total energy, because warmer coolant raises server power.

Implication: Coolant temperature is a facility-wide variable; the server-side watt penalty can eat the cooling-side saving.

**Source:** [arXiv 2611.23903](https://arxiv.org/abs/2611.23903 "Abstract: the 25-56%, PUE, WUE and free-cooling figures.").

### 5. TVA's large-load tariff has a public price: about USD 1.5 million per MW · 12-24 Nov 2026 · industry / grid

TVA's 12 November SEC filing, reported [24 November](https://www.utilitydive.com/news/tva-touts-17b-data-center-deal-under-new-large-load-tariff/875630/ "DiGangi, Utility Dive, 24 November 2026."), discloses USD 1.7 billion of aggregate payments from an unnamed data-center customer under its new tariff for data centers above 5 MW, effective 1 October, phasing in through 2029. Capacity commitment charges run "approximately USD 1.5 million per MW of requested capacity above 5 MW," cohort-based and revisable; a 100 MW request implies about USD 142.5 million. TVA pairs the tariff with a USD 13 billion three-year capital plan, a 1.5 GW gas addition targeted for 2032, and the first NRC construction permit for a [small modular reactor](https://en.wikipedia.org/wiki/Small_modular_reactor "Small modular reactor (SMR): a factory-built nuclear reactor; TVA's BWRX-300 permit at Clinch River is a permit, not a build decision.") at Clinch River.

Implication: After ISO-NE's filing and Duke's 75% minimum bill, TVA publishes a per-MW rate and a deal size: the price of grid certainty.

**Source:** [Utility Dive, 24 Nov](https://www.utilitydive.com/news/tva-touts-17b-data-center-deal-under-new-large-load-tariff/875630/ "Quotes the 12 November filing's USD 1.7 billion, USD 1.5 million per MW, cohort pricing, and the 1 October effective date.").

## Bottom line

Heat ends sustained robot missions before batteries do; policies that predict it convert thermal margin into distance — the margin racks and halls monetize. Leak response and cooling telemetry are becoming rack policies; large-load access is acquiring sticker prices. Papers are preprints; Mission Control is vendor documentation; TVA figures come from its SEC filing.

## Also noted

- Liu et al., "Joule is FLOP" (arXiv [2611.32440](https://arxiv.org/abs/2611.32440 "Submitted 24 November 2026."), 24 Nov): power-cap-aware tensor-kernel design on [B200](https://www.nvidia.com/en-us/data-center/products/b200/ "NVIDIA B200: a Blackwell data-center GPU."); 0.69% mean energy-prediction error and +4.94% geomean GEMM over best-in-class cuBLAS.
- Zhu, Tian and Yinliang (arXiv [2611.29906](https://arxiv.org/abs/2611.29906 "Submitted 23 November 2026."), 23 Nov): [voltage-ride-through](https://en.wikipedia.org/wiki/Fault_ride_through "Voltage ride-through (VRT): staying connected through voltage sags and faults.")-constrained power capping cuts demand about 5% in capped periods while meeting ride-through (IEEE 14-bus case).
- Bellegarda and Ijspeert (arXiv [2611.25958](https://arxiv.org/abs/2611.25958 "Submitted 19 November 2026."), 19 Nov): 11 learned quadruped gaits, selected per terrain and speed by cost of transport, stability or joint smoothness.

## Glossary

- [**BMS**](https://en.wikipedia.org/wiki/Building_automation): Building management system.
- [**MQTT**](https://en.wikipedia.org/wiki/MQTT): Lightweight publish/subscribe messaging protocol.
- [**PUE**](https://en.wikipedia.org/wiki/Power_usage_effectiveness): Power usage effectiveness, facility power over IT power.
- [**RC network**](https://en.wikipedia.org/wiki/Lumped_capacitance_model): Resistor-capacitor analog of heat flow.
- [**RL**](https://en.wikipedia.org/wiki/Reinforcement_learning): Reinforcement learning.
- [**VRT**](https://en.wikipedia.org/wiki/Fault_ride_through): Voltage ride-through.

---

_Rate this brief in chat: overall 1-5, optional per-item 1-5._
