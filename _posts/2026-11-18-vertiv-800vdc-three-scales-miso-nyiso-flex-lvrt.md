---
title: "Vertiv fills the 800 VDC stack; MISO and NYISO file flexibility services; ride-through needs the battery"
date: 2026-11-18 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [800vdc, grid, ramp-smoothing, ride-through, demand-response, oversubscription, AIDC-infra, energy-storage, industry, academia]
description: "A 5-minute cut. Vertiv’s Nov 17 SC26 release extends 800 VDC from a sidecar rack to a 1.5 MW pod and a 5 MW PowerNexus MV SST; ride-through and AI power smoothing are claimed only with storage on the 800 VDC bus. MISO and NYISO filed flexibility services at FERC on Nov 16. Wang et al. (arXiv 2611.19667) show a battery is required for the deepest ERCOT ride-through test; Mishra et al. (2611.19073) cut the cost of flexible interconnection 12 percent with value-based job caps."
media_subpath: /assets/img/briefs/2026-11-18/
image:
  path: fig-vertiv-800vdc-three-levels.png
  alt: Vertiv’s Nov 17 800 VDC portfolio at rack, compute-pod and data-hall scale, with vendor-stated ratings
math: true
---

## At a glance

- **800 VDC at three scales, on paper.** On Nov 17, at [SC26](https://sc26.supercomputing.org/ "SC26: International Conference for High-Performance Computing, Networking, Storage and Analysis, Chicago, 17–22 Nov 2026."), [Vertiv](https://www.vertiv.com/en-us/ "Vertiv: US maker of data-center power and thermal equipment (UPS, PDUs, busway, cooling).") extended 800 VDC from the May [PowerDirect 5000](https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-advances-800-vdc-power-architectures-to-support-growing-ai-data-center-demands/ "PowerDirect 5000: Vertiv sidecar power rack that converts facility 480 VAC to 800 or ±400 VDC, configurable up to 800 kW.") sidecar to a 1.5 MW pod and a 5 MW [PowerNexus](https://lizhouyu.github.io/technical_posts/posts/mv-ups-smoothing-aemc-ride-through-fair-energy-bills/ "PowerNexus: Vertiv’s medium-voltage outdoor power family; the Nov 13 brief covered the MV UPS. Today’s item is a different SKU, the MV SST, which converts MV AC directly to 800 VDC.") MV [solid-state transformer](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer (SST): a power-electronic transformer that converts medium-voltage AC to a controlled DC or AC output in one conversion stage."). The in-rack 90 kW shelf claims 180 percent pulse for 0.5 ms; no named customer or in-service hall.
- **MISO and NYISO filed flexibility services.** [MISO](https://www.misoenergy.org/ "Midcontinent Independent System Operator: grid operator for all or parts of 15 US states and Manitoba.") proposed a [Large Load Project Review](https://www.publicpower.org/periodical/article/grid-operators-file-plans-address-large-loads-filings-submitted-ferc "Large Load Project Review (LLPR): MISO’s proposed application and study process for transmission service to large loads, including deposits, milestones and network-upgrade cost assessment."), Firm Service Step Up, Interim Non-Firm [NITS](https://www.misoenergy.org/engage/MISO-Dashboard/firm-service-step-up-for-large-load-interconnections/ "Network Integration Transmission Service: firm transmission service that lets a customer integrate load with the network and be treated comparably to the transmission owner’s own load."), and companion [GRITS](https://www.utilitydive.com/news/pjm-rto-large-load-interconnection-ferc-show-cause/874872/ "Grid Responsive Integration Transmission Service (GRITS): MISO’s proposed permanent service for large loads that can limit electricity use under certain price and reliability conditions."). [NYISO](https://www.nyiso.com/ "New York Independent System Operator: grid operator for New York State.") filed Firm and Non-Firm Withdrawal Service and a State Exempt Load Project exception. These are [FERC](https://www.ferc.gov/ "Federal Energy Regulatory Commission: US federal agency that regulates interstate transmission and wholesale electricity markets.") proposals, not accepted tariffs.
- **Ride-through needs the battery for the deepest sags.** Wang et al. (arXiv [2611.19667](https://arxiv.org/abs/2611.19667 "Wang et al., Low-Voltage Ride-Through in AI Data Centers via Coordinated Battery and Computing Load Control, arXiv 2611.19667, 14 Nov 2026.")) show battery support stays connected through [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: grid operator for most of Texas.")’s deepest model-quality test; IT curtailment alone does not. Mishra et al. (arXiv [2611.19073](https://arxiv.org/abs/2611.19073 "Mishra, Omidi and Almassalkhi, Job-Level Workload Allocation for Data Centers Under Flexible Interconnections, arXiv 2611.19073, 14 Nov 2026.")) cut the cost of meeting grid limits 12 percent with value-based job caps in a 100 MW case study.

> Mix: 3 industry / 2 academia. Tightened to a 5-minute read; three further papers are listed at the end.
{: .prompt-tip }

![Vertiv’s Nov 17 800 VDC portfolio at rack, compute-pod and data-hall scale, with vendor-stated ratings](fig-vertiv-800vdc-three-levels.png){: w="1440" h="622" }
_Figure 1. Vertiv’s Nov 17 800 VDC architectures and vendor-stated ratings. The release names no customer or in-service hall._

## Key developments

### 1. Vertiv extends 800 VDC from a sidecar rack to a 1.5 MW pod and a 5 MW SST · Nov 17 2026 · industry / rack–pod–hall

On Nov 17 Vertiv added two layers above the May PowerDirect 5000 sidecar (480 VAC to 800 or ±400 VDC, up to 800 kW, with a [battery backup unit](https://en.wikipedia.org/wiki/Battery_backup "Battery backup unit (BBU): a rack or shelf battery that holds up IT load for seconds when the upstream source is lost or a step load arrives.") rated for at least 50 seconds). The in-rack PowerDirect 3000 is a 90 kW 800-to-54 VDC shelf with a claimed 180 percent pulse for 0.5 ms. The PowerDirect 9000 is a 1.5 MW 480 VAC-to-800 VDC pod center, with EnergyCore Li5 cabinets at 200 kW on that bus. The PowerNexus MV SST converts medium-voltage AC to 800 VDC in one 5 MW outdoor stage; Vertiv claims fault ride-through and “AI power smoothing” only when external storage sits on the 800 VDC bus. This is a different SKU from the [Nov 13 PowerNexus MV UPS](https://lizhouyu.github.io/technical_posts/posts/mv-ups-smoothing-aemc-ride-through-fair-energy-bills/ "Nov 13 brief: Vertiv PowerNexus MV UPS, an outdoor medium-voltage UPS with claimed fault ride-through and AI power smoothing, shipments mid-2027."). These are vendor ratings, not measured hall results; no customer or in-service date is named.

**Primary source:** [Vertiv, 17 Nov 2026](https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-advances-800-vdc-power-architectures-to-support-growing-ai-data-center-demands/ "Vertiv press release announcing the PowerDirect 9000, EnergyCore Li5, PowerDirect 3000 shelf and PowerNexus MV SST.").

### 2. MISO files staged firm and non-firm service, plus a companion flexibility tariff · Nov 16 2026 · industry / grid

MISO told FERC on Nov 16 that a Large Load Project Review would be the study process for transmission service to large loads, with upgrade costs borne by those customers. New services include Firm Service Step Up (firm service at a reduced level before all upgrades are finished) and Interim Non-Firm NITS while the project is built. A companion filing proposes GRITS, under which large loads could limit use under certain price and reliability conditions. The workplan aims at the first quarter of 2027; nothing here is an accepted tariff, and the public summaries do not restate the pending 30 MW/min ramp proposal.

**Sources:** [MISO large-load page](https://www.misoenergy.org/planning/large-loads---container-page/large-load-additions/ "MISO first-party page on the proposed large-load tariff changes."); [APPA, 17 Nov 2026](https://www.publicpower.org/periodical/article/grid-operators-file-plans-address-large-loads-filings-submitted-ferc "APPA summary of the Nov 16 RTO large-load filings, including MISO’s LLPR, dashboard, cost-recovery agreements, Firm Service Step Up and Interim Non-Firm NITS."); [Utility Dive, 17 Nov 2026](https://www.utilitydive.com/news/pjm-rto-large-load-interconnection-ferc-show-cause/874872/ "Utility Dive, 17 Nov 2026: account of the Nov 16 RTO filings, including MISO’s companion GRITS filing.").

### 3. NYISO files firm and non-firm withdrawal service and a resource-adequacy compromise · Nov 16 2026 · industry / grid

NYISO filed Large Load Integration Procedures with Firm and Non-Firm Withdrawal Service for flexible or co-located large loads, plus a State Exempt Load Project exception intended to reconcile NYISO’s reliability duties with the [New York Public Service Commission](https://dps.ny.gov/ "New York Public Service Commission: state regulator for retail electricity, resource adequacy and in-state interconnection.")’s resource-adequacy authority. Public summaries do not quote a bid cap, a MW threshold, or a study timeline. Together with MISO’s filings, and with [CAISO](https://www.caiso.com/ "California Independent System Operator: grid operator for most of California and part of Nevada.")’s Flexible Interim Load Interconnection and [PJM](https://www.pjm.com/ "PJM Interconnection: regional grid operator for 13 eastern US states and the District of Columbia.")’s Fast Energization covered yesterday, the show-cause class is converging on earlier access in exchange for real flexibility. [SPP](https://www.spp.org/ "Southwest Power Pool: regional grid operator for all or parts of 14 central US states.") was still due to file later this week.

**Sources:** [APPA, 17 Nov 2026](https://www.publicpower.org/periodical/article/grid-operators-file-plans-address-large-loads-filings-submitted-ferc "APPA account of NYISO’s Nov 16 Large Load Integration Procedures filing."); [Utility Dive, 17 Nov 2026](https://www.utilitydive.com/news/pjm-rto-large-load-interconnection-ferc-show-cause/874872/ "Utility Dive account of NYISO’s Firm and Non-Firm Withdrawal Service and the State Exempt Load Project exception.").

### 4. Coordinated UPS-battery and IT curtailment rides through ERCOT’s LVRT test; curtailment alone fails the deepest sag · Nov 14 2026 · academia / ride-through

Wang, Chen, Lin and Enjeti at [Texas A&M](https://engineering.tamu.edu/electrical/index.html "Texas A&M University Department of Electrical and Computer Engineering."), with Yazdanpanah, Cheng and Abhyankar at ERCOT (arXiv [2611.19667](https://arxiv.org/abs/2611.19667 "Wang et al., arXiv 2611.19667v1, submitted 14 Nov 2026.")), treat [low-voltage ride-through](https://en.wikipedia.org/wiki/Fault_ride_through "Low-voltage ride-through (LVRT): remaining connected, with a prescribed power behavior, through a grid voltage sag.") as a DC-link power-balance problem. Once the rectifier hits its current limit, grid power falls with voltage; if the DC-link then reaches its undervoltage trip, the hall disconnects. On the TAMU–ERCOT [PSCAD](https://www.pscad.com/ "PSCAD: electromagnetic-transient simulation tool used for converter-level studies.") model of a 1 MW hall (1,000 V, 20 mF DC link, 800 V trip, 1 MW battery, 0.4 per-unit IT floor), battery support alone or coordinated with IT curtailment stays connected through ERCOT’s model-quality test, including a near-zero-voltage fault. Curtailment alone rides through sags above about 0.36 per unit but trips on the zero-voltage fault. This is an [EMT](https://en.wikipedia.org/wiki/EMTP "Electromagnetic-transient (EMT) simulation: a time-domain model of converter and fault dynamics.") study, not a field trial.

**Primary source:** [arXiv 2611.19667](https://arxiv.org/abs/2611.19667 "Abstract and PDF for Wang et al.").

### 5. Value-based job caps cut the cost of flexible interconnection by 12 percent; on-site supply cuts it a further 90 percent · Nov 14 2026 · academia / capping and flexibility

Mishra, Omidi and Almassalkhi at the [University of Vermont](https://www.uvm.edu/cems/ebe "University of Vermont Department of Electrical and Biomedical Engineering.") (arXiv [2611.19073](https://arxiv.org/abs/2611.19073 "Mishra, Omidi and Almassalkhi, arXiv 2611.19073v1, submitted 14 Nov 2026.")) treat that flexibility bargain from the hall side. The cost of a grid-import limit is the work lost, not the megawatt-hours curtailed: the paper cites H100 rental of about USD 3–5 per GPU-hour, or roughly USD 4,300–7,100 per MWh at 700 W, against about USD 85 per MWh for US industrial power. In a one-year 100 MW case study, allocating import by job value rather than by priority tier lowers the annual cost of meeting grid limits by 12 percent; adding on-site generation and storage lowers that cost by a further 90 percent. Job values are assumed or model-generated, and interactive inference is treated as inflexible.

**Primary source:** [arXiv 2611.19073](https://arxiv.org/abs/2611.19073 "Abstract and PDF for Mishra, Omidi and Almassalkhi.").

## Spotlight: ride-through as a DC-link balance

Once the rectifier is at its current limit, grid power tracks voltage:

$$P_{\mathrm{grid}} = I_{\mathrm{grid}}^{\max}\, V_{\mathrm{grid}}.$$

The deficit $$P_{\mathrm{IT}} - P_{\mathrm{grid}}$$ has to come from the DC-link capacitor, the UPS battery, or IT curtailment. If it does not, $$V_{\mathrm{DC}}$$ falls to the trip threshold and the hall leaves the grid — the failure mode in the no-control case of arXiv 2611.19667, and the reason Vertiv’s SST smoothing claim is conditioned on storage on the 800 VDC bus.

## Bottom line

Vertiv will sell 800 VDC at rack, pod or hall scale, and claims ride-through and AI smoothing at the medium-voltage SST only with storage on the DC bus. MISO and NYISO have now filed, as CAISO and PJM did this week, services that trade earlier interconnection for firm-plus-flexible offtake. The papers say how to use that flexibility without failing ride-through: keep a battery in the loop for deep voltage sags, and allocate caps by job value rather than by tier. Industrial numbers are vendor or filed-proposal figures; academic numbers are simulations. SPP’s filing is still outstanding.

## Also noted

- Ma, Qiu and Liu (arXiv [2611.19125](https://arxiv.org/abs/2611.19125 "Ma, Qiu and Liu, AI Inference-Aware Optimal Power Flow: Converting Token Requirements into Grid Flexibility, arXiv 2611.19125, 14 Nov 2026.")): an inference-aware [optimal power flow](https://en.wikipedia.org/wiki/Optimal_power_flow "Optimal power flow (OPF): an optimization that dispatches generation to meet demand at minimum cost while respecting transmission limits.") stays feasible on a 7,830-bus PJM model at 6–8 percent inference share, where nearest-hall and price-only routing do not.
- Odunlami and Netto (arXiv [2611.21144](https://arxiv.org/abs/2611.21144 "Odunlami and Netto, A Hybrid Systems Approach to Parameterizing the PERC1 Model for Data Centers Using Synchrophasor Measurements, arXiv 2611.21144, 16 Nov 2026.")): the PERC1 ceasing-and-reconnection model can be identified from [synchrophasors](https://en.wikipedia.org/wiki/Synchrophasor "Synchrophasor: a time-synchronized voltage or current phasor, typically from a phasor-measurement unit at 30–60 frames per second."), but one disturbance is not enough.
- Ferreira et al. (arXiv [2611.20830](https://arxiv.org/abs/2611.20830 "Ferreira et al., Investigating the Impact of CI-Source Sensitivity in Carbon-Aware Resource Management Systems, arXiv 2611.20830, 16 Nov 2026.")): switching the carbon-intensity feed changes the chosen site in 43.50 percent of cases in a reproduced placement study.

## Glossary

- [**800 VDC**](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/ "800 VDC: high-voltage DC rack and facility distribution, aimed at lower current than low-voltage AC or 54 V paths."): High-voltage DC rack and facility distribution.
- [**BBU**](https://en.wikipedia.org/wiki/Battery_backup): Battery backup unit.
- [**CAISO**](https://www.caiso.com/): Grid operator for most of California and part of Nevada.
- [**DC link**](https://en.wikipedia.org/wiki/Variable-frequency_drive#DC_link): The intermediate DC bus in a rectifier–inverter or UPS chain.
- [**EMT**](https://en.wikipedia.org/wiki/EMTP): Electromagnetic-transient simulation.
- [**ERCOT**](https://www.ercot.com/): Grid operator for most of Texas.
- [**FERC**](https://www.ferc.gov/): US Federal Energy Regulatory Commission.
- [**GRITS**](https://www.utilitydive.com/news/pjm-rto-large-load-interconnection-ferc-show-cause/874872/): MISO’s proposed Grid Responsive Integration Transmission Service.
- [**LVRT**](https://en.wikipedia.org/wiki/Fault_ride_through): Low-voltage ride-through.
- [**MISO**](https://www.misoenergy.org/): Midcontinent Independent System Operator.
- [**NITS**](https://www.misoenergy.org/engage/MISO-Dashboard/firm-service-step-up-for-large-load-interconnections/): Network Integration Transmission Service.
- [**NYISO**](https://www.nyiso.com/): New York Independent System Operator.
- [**PJM**](https://www.pjm.com/): Regional grid operator for 13 eastern US states and D.C.
- [**PowerNexus MV SST**](https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-advances-800-vdc-power-architectures-to-support-growing-ai-data-center-demands/ "Vertiv 5 MW solid-state transformer that converts medium-voltage AC directly to 800 VDC."): Vertiv’s 5 MW medium-voltage solid-state transformer to 800 VDC.
- [**SPP**](https://www.spp.org/): Southwest Power Pool.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**Vertiv**](https://www.vertiv.com/en-us/): Data-center power and cooling vendor.

---

_How useful was today’s brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
