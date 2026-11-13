---
title: "Smoothing moves to medium voltage; Australia's 30 MW ride-through rule; fair per-request energy bills"
date: 2026-11-13 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [ramp-smoothing, ride-through, grid, 800vdc, sst, inference, energy-accounting, oversubscription, industry, academia, adjacent]
description: "Vertiv launches the PowerNexus MV UPS, an outdoor medium-voltage UPS with fault ride-through and AI power smoothing (shipments mid-2027). Australia's AEMC finalizes a 30 MW threshold and ride-through standards for large inverter-based loads, effective immediately. Vertiv's 800 VDC engineering note explains why converter-fed faults may not trip breakers. SolidUltra raises €3 million for grid-to-800 VDC SSTs; Heron Power books 1.5 GW of factory capacity. Howden puts US data-center demand growth at 19% a year against 2% grid growth. StepSplit bills each LLM request a Shapley-fair energy share at 0.4–6.4% error. Microsoft's ShadowPrefill finds code-serving instances idle 72% of the median hour. TU Berlin powers off idle serverless nodes for 39.6–46.7% less power."
media_subpath: /assets/img/briefs/2026-11-13/
image:
  path: fig-protection-ridethrough-windows.png
  alt: Vendor-stated time windows for 800 VDC fault clearing, medium-voltage UPS ride-through tests and battery backup
math: true
---

## At a glance

- **Ramp smoothing moves to the point of connection.** [Vertiv](https://www.vertiv.com/ "Vertiv: US maker of data-center power and thermal equipment (UPS, PDUs, busway, cooling).") launched the PowerNexus [MV](https://en.wikipedia.org/wiki/Voltage#Medium_voltage "Medium voltage (MV): roughly 1 kV to 35 kV; the level at which large data centers take utility power.") [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply: equipment that keeps critical loads powered and conditioned through grid disturbances."), an outdoor skid that combines a medium-voltage UPS, fault ride-through and “AI power smoothing” (Nov 12; shipments mid-2027).
- **Australia writes ride-through into the rules.** The [AEMC](https://www.aemc.gov.au/ "Australian Energy Market Commission: rule maker for Australia's National Electricity Market (NEM).") set a 30 MW threshold for large inverter-based loads, with ride-through standards, effective immediately (Nov 12).
- **800 VDC protection is a different problem.** A Vertiv engineering note, re-pushed on X on Nov 12, explains why converter-fed DC faults may not trip conventional breakers.
- **The SST supply side is forming.** SolidUltra raised €3 million for grid-to-800 VDC SSTs (Nov 9). Heron Power booked 1.5 GW of factory capacity from Intersect (Nov 12).
- **Academia:** fair per-request energy bills for batched LLM serving (StepSplit), and Microsoft data on how idle peak-provisioned inference pools really are (ShadowPrefill).
- **Adjacent:** Howden's grid-gap numbers, and powering off idle serverless nodes.

![Vendor-stated time windows for 800 VDC protection, MV ride-through and backup](fig-protection-ridethrough-windows.png){: w="1440" h="585" }
_Figure 1. Time windows from today's Vertiv items, on one log axis. The fault-clearing and discharge bars come from Vertiv's 800 VDC engineering note and its Nov 12 X post. The ride-through bars are Vertiv's proof-of-concept test conditions for PowerNexus MV UPS. The 4 h bar is Vertiv's stated maximum backup with long-duration batteries. These are vendor statements, not independent tests._

## Key developments

### 1. Vertiv PowerNexus MV UPS puts ride-through and AI power smoothing at the medium-voltage entrance · Nov 12 2026 · industry / data center to grid

Vertiv introduced the [PowerNexus MV UPS](https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-introduces-medium-voltage-power-system-to-help--ai-data-centers-connect-to-the-grid-faster-and-free-indoor-space-for-compute/ "Vertiv PowerNexus MV UPS: outdoor-rated medium-voltage UPS skid with fault ride-through and AI power smoothing; shipments expected mid-2027."), an outdoor-rated skid installed at the point of utility connection. Vertiv says it combines a medium-voltage UPS, fault ride-through and AI power smoothing, and is “designed to … absorb rapid AI load fluctuations before they reach the grid.” It uses a [line-interactive](https://en.wikipedia.org/wiki/Uninterruptible_power_supply#Line-interactive "Line-interactive UPS: the inverter sits in parallel with the utility path and regulates voltage without double conversion, trading some isolation for efficiency.") topology with up to 98.5% peak efficiency. With long-duration batteries, Vertiv says it can provide up to four hours of battery-backed operation, reducing reliance on diesel generators. Output meets [IEC 62040-3](https://webstore.iec.ch/en/publication/64297 "IEC 62040-3: international standard that classifies UPS performance; Class 1 is the tightest output-voltage tolerance during load steps and input disturbances.") Class 1 voltage quality. A [PSCAD](https://www.pscad.com/ "PSCAD: electromagnetic-transient simulation software widely used by utilities for interconnection studies.") model is available for interconnection studies. Shipments are expected to begin in mid-2027.

Vertiv reports proof-of-concept demonstrations with [QTS](https://qtsdatacenters.com/ "QTS Data Centers: US data-center developer and operator owned by Blackstone."), SoftBank and Rosendin in Bologna. It cites stable operation across 0–100% load, Class 1 voltage accuracy during rapid load changes, ride-through of a 100% voltage sag for 150 ms, and ride-through of a 25% overvoltage for 5 s. Vertiv also plans a dedicated medium-voltage lab in Bologna, operational in 2027, covering MV UPS, MV-to-800 VDC and [BESS](https://en.wikipedia.org/wiki/Battery_energy_storage_system "Battery energy storage system: grid- or site-scale batteries with power conversion and controls.").

**Caveats.** This is a launch release. Vertiv gives no smoothing specification: no ramp-rate limit, no MW rating and no response time for the smoothing function. The test results are Vertiv-hosted demonstrations, not third-party certification.

**Implication.** Smoothing hardware in earlier briefs sat at the rack (BBU shelves), in the white space (sidecars) or on the DC bus (Ampt). This product puts smoothing at the utility handoff, the place where an interconnection ramp limit is actually measured. It also bundles ride-through, so the device that hides training steps from the grid is the same device that keeps the hall from tripping off during a fault. For oversubscription, the planning question becomes how much of the step a facility-level buffer can absorb before rack-level caps must act.

- [Vertiv: PowerNexus MV UPS launch (Nov 12 2026)](https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-introduces-medium-voltage-power-system-to-help--ai-data-centers-connect-to-the-grid-faster-and-free-indoor-space-for-compute/)

### 2. Australia's AEMC: 30 MW threshold and mandatory ride-through for large inverter-based loads · Nov 12 2026 · industry / grid interaction

The AEMC published its final rule, [Improving the NEM Access Standards – Package 2](https://www.aemc.gov.au/news-centre/media-releases/aemc-determination-strengthens-framework-address-anticipated-data-centre-impacts-national "AEMC media release, Nov 12 2026: final rule on access standards for large inverter-based loads, including data centers."). It sets a 30 MW threshold for large [inverter-based loads](https://en.wikipedia.org/wiki/Power_electronics "Inverter-based load: a load connected through power electronics (rectifiers, converters) rather than directly through motors or resistive elements; data centers are the main example.") (IBLs), including large data centers. Loads above the threshold must ride through certain system disturbances rather than disconnect. Network businesses must assess the combined effect of nearby large IBLs. [AEMO](https://aemo.com.au/ "Australian Energy Market Operator: runs Australia's electricity and gas markets and the power system.") must issue modelling guidance for large loads. The rule is effective immediately, with a six-month grace period for applicants that have already negotiated access standards. The AEMC cites the 1,500 MW of simultaneous data-center disconnections in Virginia in July 2024. It projects Australian data-center demand rising from 5 TWh to 34 TWh by 2035, about 13% of demand.

The same day, the AEMC opened consultation on a companion rule for operational visibility of large IBLs. It also noted further work on network cost recovery, data-center contracting and connection streamlining.

**Caveats.** The release names the requirements but not the numeric ride-through envelopes; those are in the rule text. Ramp-rate limits are not listed among the headline reforms.

**Implication.** This joins [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: grid operator for most of Texas.")'s computational-load ride-through rule in turning “don't trip together” into a connection condition. Note the scale: 30 MW is a single mid-size AI hall, not just a campus. Cumulative assessment matters for capping design too. If several halls behind nearby nodes share the same firmware cap policy, they can step together, and the network operator will now study that.

- [AEMC: final determination media release (Nov 12 2026)](https://www.aemc.gov.au/news-centre/media-releases/aemc-determination-strengthens-framework-address-anticipated-data-centre-impacts-national)

### 3. Why converter-fed 800 VDC faults may not trip a breaker · Nov 5 2026 (re-pushed Nov 12) · industry / rack and power-rack protection

On Nov 12, Vertiv's X accounts promoted an engineering note by Victor Avelar, [Engineering problems that stand between AI and 800 VDC power](https://www.vertiv.com/en-us/insights/articles/blog-posts/engineering-problems-that-stand-between-ai-and-800-vdc-power/ "Vertiv blog (Nov 5 2026): arc behavior, protection, transients, grounding and maintenance in 800 VDC AI data centers."). The X post states the core numbers: an [SSCB](https://en.wikipedia.org/wiki/Circuit_breaker#Solid-state "Solid-state circuit breaker: a semiconductor switch that interrupts fault current in microseconds, without mechanical contacts.") clears in tens of µs, and a conventional breaker takes 20–100 ms. The note explains why that matters. A converter's control loop limits fault current to near-nominal levels, and capacitor discharge peaks last only hundreds of microseconds. As a result, “conventional breakers may not trip at all.” The choice is SSCBs, which are costly and not yet available at scale, or accepting a temporary bus collapse and relying on redundant buses.

The note also says synchronized training steps, which swing at 10–100 A/ns at the die, reach the power rack as kilohertz-frequency oscillations. It recommends laminated busway, snubber capacitors at tap-offs and conductors sized for skin effect. It adds that no DC equivalent of [IEEE 1584](https://standards.ieee.org/ieee/1584/5826/ "IEEE 1584-2018: guide for calculating arc-flash incident energy in AC systems; there is no finalized DC equivalent.") for arc-flash calculation has been finalized yet.

**Caveats.** This is a vendor engineering blog, not a measurement study, and it was first posted Nov 5. It is included because it has not appeared on this site and it explains the protection layer behind items 1 and 4.

**Implication.** Ramp smoothing and protection now compete for the same microsecond budget. A buffer that answers a GPU step within a millisecond (as Ampt claimed yesterday) has to coordinate with protection that must decide, within hundreds of microseconds, whether a current rise is a load step or a fault. Grounding is an availability choice too. High-resistance grounding keeps a training job alive through a first fault.

- [Vertiv: Engineering problems that stand between AI and 800 VDC power (Nov 5 2026)](https://www.vertiv.com/en-us/insights/articles/blog-posts/engineering-problems-that-stand-between-ai-and-800-vdc-power/)
- [Vertiv on X (Nov 12 2026)](https://x.com/Vertiv/status/2120833988122022289)

### 4. SST supply: SolidUltra raises €3 million; Heron Power books 1.5 GW of factory capacity · Nov 9 and Nov 12 2026 · industry / facility power conversion

French startup [SolidUltra](https://www.solidultra.com/ "SolidUltra: French startup (founded June 2026) developing modular medium-voltage solid-state transformers that output 800 VDC.") announced €3 million from its founding partner, [Watt & Well](https://www.wattandwell.com/ "Watt & Well: French power-electronics group, founding partner of SolidUltra."). It is building a modular [SST](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer: power electronics that replace a line-frequency transformer, here converting medium-voltage AC directly to DC.") that converts medium voltage to 800 VDC in one stage. Its target is 98.5% efficiency, three times lower losses and four times smaller footprint than a transformer-plus-rectifier chain. The design scales from hundreds of kW to 10 MW and beyond, with modules swappable in under 15 minutes. First commercial deployments are targeted for 2028, and the 2032 goal is about 1 GW installed. Separately, [Heron Power](https://heronpower.com/ "Heron Power Electronics: US maker of Heron Link, a modular solid-state medium-voltage power-conversion platform for solar, storage and data centers.") said Intersect reserved 1.5 GW of Heron Link production for solar. Its Morgan Hill factory is designed for over 40 GW a year, with mass production from late 2027. On X, investor Shayle Kann noted this follows a 1 GW reservation from [Vantage](https://vantage-dc.com/ "Vantage Data Centers: hyperscale data-center developer and operator.") for 800 VDC data centers.

**Caveats.** SolidUltra's figures are targets; there is no product yet. Heron's new reservation is for solar, not data centers.

**Implication.** Envision's live SST deployment showed the architecture works in production. These announcements show who might supply it outside China, and when: 2028 at the earliest, in volume. Any SST-based smoothing plan therefore depends on a 2027–2028 supply curve.

- [SolidUltra / GlobeNewswire (Nov 9 2026)](https://www.globenewswire.com/news-release/2026/11/09/3398558/0/en/solidultra-secures-3-million-to-address-ai-data-centers-800vdc-power-challenge.html)
- [Heron Power: Intersect reserves 1.5 GW (Nov 12 2026)](https://heronpower.com/news-stories/intersect-reserves-1-5-gw-of-heron-link-manufacturing-capacity-for-solar)
- [Shayle Kann on X (Nov 12 2026)](https://x.com/shaylekann/status/2120898135837020312)

### 5. Howden: US data-center demand grew 19% a year while grid capacity grew 2% · Nov 11 2026 · industry / grid and risk

Insurance broker [Howden](https://www.howdengroupholdings.com/ "Howden: global insurance broker; publisher of the report Insuring the data centre supercycle.") released [new analysis](https://www.howdengroupholdings.com/news/us-data-centre-power-demand-rising-10x-faster-than-grid-capacity-accelerating-a-switch-to-alternatives "Howden, Nov 11 2026: US data centre power demand rising 10x faster than grid capacity."), based on EIA and 451 Research data. It finds US data-center power demand has grown 19% a year since 2000, against 2% a year for grid capacity. Data centers' share of US grid capacity rose from 0.1% in 2000 to 5% in 2025. Power constraints add 24–72 months to the most constrained builds. To hold a 5% share at current growth, data centers would need about 58% of their power (110 GW) from [behind-the-meter](https://en.wikipedia.org/wiki/Distributed_generation "Behind-the-meter: generation or storage on the customer's side of the utility meter.") sources by 2030, which Howden calls unlikely. Howden also says UPS failures cause most major outages.

**Caveats.** This is a broker's analysis built on secondary data. The lost-revenue range is a Howden estimate.

**Implication.** The 58% figure frames why ramp smoothing and flexibility matter. Every MW that a smoother, more curtailable hall can take from the existing grid is a MW that does not have to be built behind the meter. It also highlights UPS reliability as a risk, just as UPS hardware (item 1) takes on smoothing duties.

- [Howden: research release (Nov 11 2026)](https://www.howdengroupholdings.com/news/us-data-centre-power-demand-rising-10x-faster-than-grid-capacity-accelerating-a-switch-to-alternatives)

### 6. StepSplit: Shapley-fair energy bills for batched LLM requests · arXiv Nov 10 2026 · academia / inference energy accounting

Luo et al. ([HKUST-Guangzhou](https://www.hkust-gz.edu.cn/ "The Hong Kong University of Science and Technology (Guangzhou).")) observe that each decode step's energy is a *shared* part, mostly from reading the model weights, plus a part owned by each request. That structure gives a closed-form [Shapley value](https://en.wikipedia.org/wiki/Shapley_value "Shapley value: the fair way, in cooperative game theory, to split a joint cost by each player's average marginal contribution."). Each request pays its own energy plus an equal share of the shared energy of every step it joins. A 2.5–17.8 minute microbenchmark calibrates each model and GPU configuration. They validate against Shapley values from 529,513 GPU runs. Under static batching with 8–256 requests, the error is 0.4–4.3%, against 13.4–61.3% for token-proportional billing. Under continuous batching with 8–128 requests, it is 0.5–6.4% against 20.6–71.7%. Continuous batching needs a CPU replay of the scheduler. An online ledger hooks into [vLLM](https://docs.vllm.ai/ "vLLM: open-source LLM serving engine with continuous batching and PagedAttention.") at 0.7% of mean step time. Tests cover [H100](https://www.nvidia.com/en-us/data-center/h100/ "NVIDIA H100: Hopper-generation data-center GPU.") and other GPUs, including dense, MoE and hybrid models.

**Caveats.** This is a preprint. It attributes GPU energy only; host, network and cooling overhead are outside the model.

**Implication.** Under a power cap or a demand-response event, someone has to decide whose requests to slow down. Per-request energy that is actually fair is the input that makes such decisions defensible. It also shows that token-proportional accounting can misprice long-prompt work by large margins, which matters for chunked-prefill and prefill-heavy agent traffic.

- [arXiv: 2611.13802](https://arxiv.org/abs/2611.13802)

![StepSplit error ranges](fig-stepsplit-error.png){: w="1200" h="480" }
_Figure 2. Error versus measured Shapley shares, as ranges reported by the authors (arXiv 2611.13802)._

### 7. ShadowPrefill: Microsoft data on idle capacity in peak-provisioned LLM pools · arXiv Nov 9 2026 · academia / inference capacity and oversubscription

Qiu, Mahapatra, Fonseca and Russinovich ([Azure Research](https://www.microsoft.com/en-us/research/group/azure-research-systems/ "Microsoft Azure Research – Systems: systems research group inside Microsoft Azure.") / Microsoft Azure) target per-step model routing in agents. Switching models drops the prefix-cache hit rate from 80–89% to 44–65%, and a switch call takes 1.5–3.2× as long. ShadowPrefill pre-warms the KV cache on the other model using idle capacity and per-iteration [SLO](https://en.wikipedia.org/wiki/Service-level_objective "Service-level objective: a latency or availability target the operator commits to.") slack. Across 24 model pairs, it cuts switch-call latency 8.5–21.4% and routed token cost 22.5–46.1%, while energy per request rises 0.4%.

For power planning, the more useful part is the characterization. The authors replay one week of Azure LLM inference traces on a pool sized for peak. Load swings 3–10× within a day. Instances serving code traffic are completely idle for 72% of the median hour and 85% of the trough hour, but only 8% of the peak hour. Conversation traffic leaves no whole-instance idle time.

**Caveats.** This is a preprint built on simulation plus a testbed. The idle figures come from replaying public Azure traces on an assumed pool, not from fleet telemetry.

**Implication.** This is direct evidence that inference pools are provisioned for a peak they rarely reach. That headroom is what power oversubscription monetizes. It is also what “harvesting” systems like this one quietly consume. If idle slack gets filled with shadow work, oversubscription models built on idle-hour power draw need to be revisited.

- [arXiv: 2611.13176](https://arxiv.org/abs/2611.13176)

### 8. Energy-proportional serverless: power off idle nodes, not just instances · arXiv Nov 10 2026 · adjacent / sustainable computing

Sasinskaya et al. ([TU Berlin](https://www.tu.berlin/en/ "Technische Universität Berlin.")) argue that because serverless functions are stateless, scale-to-zero can extend from function instances to physical nodes. On a four-board Raspberry Pi 4B cluster running [tinyFaaS](https://github.com/OpenFogStack/tinyFaaS "tinyFaaS: lightweight serverless platform for edge and resource-constrained environments."), relay-switched node power cuts mean draw by 39.6% on a bursty Azure-trace workload and by 46.7% on a sparse one, with no detectable change in median latency on the bursty workload. The cost appears in the tail: requests that arrive when every worker is off wait about a minute for a boot. The paper appears at the Mid4CC '26 workshop.

**Caveats.** This is a small testbed of single-board computers, not GPU servers.

**Implication.** The same idea, power-gating whole nodes during trough hours, is the low-hanging counterpart to item 7's idle-hour data. The constraint is boot latency, and a GPU node's boot and model-load time are far longer than a minute.

- [arXiv: 2611.14026](https://arxiv.org/abs/2611.14026)

## Spotlight: the step-sharing rule in one line

StepSplit's closed form charges request $$i$$ its own energy plus an equal share of each step's shared energy:

$$
E_i \;=\; \sum_{t \,\ni\, i} \left( e_{i,t} \;+\; \frac{S_t}{n_t} \right)
$$

Here $$S_t$$ is the shared energy of step $$t$$ (mostly weight reads), $$n_t$$ is the number of requests in that step, and $$e_{i,t}$$ is request $$i$$'s own energy in that step. Bigger batches spread $$S_t$$ thinner, so the same request is cheaper at high load than at low load. Token-proportional billing hides this.

## Bottom line

Smoothing hardware is spreading across the power stack: from rack shelves and sidecars to the DC bus and now the medium-voltage entrance. Regulators are making ride-through a connection condition at 30 MW. On the compute side, Microsoft's traces show how much peak-provisioned inference capacity sits idle, and StepSplit offers a fair way to bill energy when that capacity is shared or capped.

## Glossary

- [**AEMC**](https://www.aemc.gov.au/): Australian Energy Market Commission, the NEM rule maker.
- [**AEMO**](https://aemo.com.au/): Australian Energy Market Operator.
- [**Behind-the-meter**](https://en.wikipedia.org/wiki/Distributed_generation): Generation or storage on the customer side of the meter.
- [**BESS**](https://en.wikipedia.org/wiki/Battery_energy_storage_system): Battery energy storage system.
- [**ERCOT**](https://www.ercot.com/): Texas grid operator.
- [**H100**](https://www.nvidia.com/en-us/data-center/h100/): NVIDIA Hopper data-center GPU.
- [**IEC 62040-3**](https://webstore.iec.ch/en/publication/64297): UPS performance standard; Class 1 is the tightest output class.
- [**IEEE 1584**](https://standards.ieee.org/ieee/1584/5826/): AC arc-flash calculation guide.
- [**Inverter-based load (IBL)**](https://en.wikipedia.org/wiki/Power_electronics): A load connected through power electronics.
- [**Line-interactive UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply#Line-interactive): UPS topology that regulates voltage in parallel with the utility path.
- [**MV**](https://en.wikipedia.org/wiki/Voltage#Medium_voltage): Medium voltage, roughly 1–35 kV.
- [**PSCAD**](https://www.pscad.com/): Electromagnetic-transient simulation tool.
- [**Shapley value**](https://en.wikipedia.org/wiki/Shapley_value): Fair cost split by average marginal contribution.
- [**SLO**](https://en.wikipedia.org/wiki/Service-level_objective): Service-level objective.
- [**SSCB**](https://en.wikipedia.org/wiki/Circuit_breaker#Solid-state): Solid-state circuit breaker.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**tinyFaaS**](https://github.com/OpenFogStack/tinyFaaS): Lightweight serverless platform.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**vLLM**](https://docs.vllm.ai/): Open-source LLM serving engine.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
