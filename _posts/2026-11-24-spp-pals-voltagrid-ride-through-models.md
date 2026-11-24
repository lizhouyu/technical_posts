---
title: "SPP’s USD 25/MWh flex service; a 2,582 MW behind-the-meter plant; ride-through models still unvalidated"
date: 2026-11-24 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [grid, flexibility, demand-response, ride-through, AIDC-infra, industry, academia, oversubscription, interconnection, ramp-smoothing]
description: "A 5-minute cut. SPP’s 19 November FERC filing proposes Price Adaptive Load Service, a non-firm product that would dispatch participating load to zero when the locational marginal price exceeds a USD 25/MWh bid cap, with no added resource-adequacy obligation, and a companion cap on regionally funded delivery-point upgrades. The same day, TCEQ issued air permits for VoltaGrid’s 2,582 MW behind-the-meter gas plant next to a Vantage data-center campus. Cheerla (arXiv 2611.27169) finds no held-out validation of a frozen, facility-specific data-center dynamic model. Lyu et al. (2611.27576) cut daily cost 6.5% by sizing mixed accelerators under grid envelopes — in a 125–185 kW simulation."
---

## At a glance

- **Flexible load in [SPP](https://www.spp.org/ "Southwest Power Pool: the regional grid operator for all or parts of 14 central US states.") would be cut to zero above USD 25/MWh.** On 19 November, SPP filed [Price Adaptive Load Service](https://elibrary.ferc.gov/eLibrary/filelist?accession_number=20261119-5243 "FERC eLibrary accession 20261119-5243: SPP, Revisions to Add Price Adaptive Load Service, docket ER27-578, filed 19 November 2026.") at [FERC](https://www.ferc.gov/ "Federal Energy Regulatory Commission: the US regulator of interstate electricity transmission and wholesale markets."): a standing non-firm product that would dispatch participating demand to zero when the [locational marginal price](https://en.wikipedia.org/wiki/Locational_marginal_pricing "Locational marginal price (LMP): the marginal cost of supplying the next megawatt-hour at a specific grid node.") exceeds a USD 25/MWh bid cap, with no added resource-adequacy obligation, plus a cap on regionally funded hook-up costs. These are proposals, not accepted tariffs.
- **Texas authorized 2,582 MW of behind-the-meter gas next to a Vantage campus.** On 19 November, [TCEQ](https://www.tceq.texas.gov/ "Texas Commission on Environmental Quality: the state environmental regulator.") issued NSR Permit 182467 to [VoltaGrid](https://www.voltagrid.com/ "VoltaGrid: a US developer of on-site natural-gas generation for large loads; named Voltagrid LLC on the TCEQ documents.") for ABI-1 in Shackelford County: 620 natural-gas engines totaling 2,582 MW, a [behind-the-meter](https://en.wikipedia.org/wiki/Distributed_generation "Behind-the-meter: generation that serves on-site or adjacent load rather than being sold as grid supply.") plant to serve a nearby [Vantage Data Centers](https://www.vantage-dc.com/ "Vantage Data Centers: a wholesale data-center operator.") campus.
- **The models that now gate [ride-through](https://lizhouyu.github.io/technical_posts/posts/caiso-20mw-pjm-fast-energization-gfm-halls/ "Ride-through: remaining connected through a grid fault or voltage sag.") lack a held-out test.** Cheerla (arXiv [2611.27169](https://arxiv.org/abs/2611.27169 "Cheerla, Which Data-Center Load Models Can Be Trusted?, arXiv 2611.27169, submitted 20 November 2026. A preprint, not peer reviewed.")) reviewed 160 documents and found no successful held-out validation of a frozen, facility-specific data-center dynamic model against a measured disturbance.

## Key developments

### 1. SPP proposes a USD 25/MWh non-firm product, and a cap on who pays for hook-ups · 19–23 Nov 2026 · industry / grid

SPP’s 19 November filing (docket ER27-578, FERC accession 20261119-5243) would add Price Adaptive Load Service as a standing non-firm option. [POWER Magazine](https://www.powermag.com/five-grid-operators-respond-to-ferc-with-distinct-plans-for-large-load-integration/ "POWER Magazine, updated 23 November 2026, on SPP’s PALS and Load Safe Harbor Limit."), in a 23 November update that adds SPP to its six-operator comparison, reports that qualifying demand would be dispatched to zero when locational marginal prices exceed a USD 25/MWh bid cap, and that participating non-firm loads would take on no added resource-adequacy obligation. That cap is one-tenth of the USD 250/MWh re-dispatch trigger in [ISO-NE](https://www.iso-ne.com/ "ISO New England: the grid operator for the six New England states.")’s [13 November filing](https://lizhouyu.github.io/technical_posts/posts/iso-ne-tariff-1200a-racks-gpu-excursions/ "16 November Daily Brief: ISO-NE would re-dispatch non-firm and interim large loads when area energy prices reach USD 250/MWh."). A companion Load Safe Harbor Limit would cap regionally funded delivery-point upgrades at the lesser of USD 500,000/MW or USD 25 million per request; costs above that would be directly assigned to the customer for up to 40 years. The ER27-578 record carries a placeholder effective date of 12/31/9998. Nothing here is an accepted tariff.

Implication: The cheap path onto SPP is a hard cap, not a soft ramp. [Oversubscription](https://lizhouyu.github.io/technical_posts/posts/power-oversubscription-brief/ "Power oversubscription: contracting or operating more IT load than the upstream power path can supply at coincident peak.") and [ramp smoothing](https://lizhouyu.github.io/technical_posts/posts/aidc-power-ramp-smoothing/ "Power ramp smoothing: using storage, caps or scheduling so that fast AI load steps do not appear as equally fast ramps at the grid.") become the tools that make a USD 25/MWh floor operable — or campuses look behind the meter instead.

**Sources:** [FERC eLibrary, accession 20261119-5243](https://elibrary.ferc.gov/eLibrary/filelist?accession_number=20261119-5243 "Primary docket record for ER27-578, including the placeholder effective date."); [POWER Magazine, updated 23 Nov](https://www.powermag.com/five-grid-operators-respond-to-ferc-with-distinct-plans-for-large-load-integration/ "Source of the USD 25/MWh dispatch-to-zero rule, the no-adequacy-obligation statement, and the Load Safe Harbor Limit terms.").

### 2. TCEQ authorizes 2,582 MW of behind-the-meter gas for a Vantage campus · 19 Nov 2026 · industry / hall–grid

The permit face for NSR 182467, PSDTX1692 and GHGPSDTX266 is dated 19 November 2026 and expires 19 November 2036. TCEQ’s [technical review](https://records.tceq.texas.gov/cs/idcplg?IdcService=TCEQ_EXTERNAL_SEARCH_GET_FILE&Rendition=Web&dID=10265116&searchType=External "TCEQ technical review for VoltaGrid LLC, ABI-1 EGU: source of the 620-engine, 2,582 MW, 709 MW prior authorization, Vantage, and behind-the-meter statements.") authorizes VoltaGrid to expand ABI-1 in Abilene, Shackelford County, from 210 engines and 709 MW under Standard Permit 180842 — which will be voided — to 620 natural-gas engines and 2,582 MW of baseload capacity. The review states that the plant “is proposed to provide prime power to itself and to a nearby facility owned and operated by an external third party (Vantage Data Centers LLC)” and “is a ‘behind the meter’ power plant to support a data center.” This is an air-construction permit, not an interconnection study or an in-service date.

Implication: A 2,582 MW behind-the-meter plant is the other answer to tight interconnection and price-triggered flex products. It does not remove ride-through, ramp, or oversubscription problems inside the campus; it shifts fuel, emissions, and adequacy risk off the regional tariff and onto the site.

**Source:** [TCEQ technical review](https://records.tceq.texas.gov/cs/idcplg?IdcService=TCEQ_EXTERNAL_SEARCH_GET_FILE&Rendition=Web&dID=10265116&searchType=External "Primary source for capacity, engine counts, Vantage, behind-the-meter language, and authorized CO2e."); issuance and expiry as stated on the TCEQ permit face.

### 3. No held-out test yet supports the models that gate ride-through · submitted 20 Nov 2026 · academia / ride-through

Dileep Cheerla, an independent researcher in Lewisville, Texas (arXiv [2611.27169](https://arxiv.org/abs/2611.27169 "Cheerla, arXiv 2611.27169, submitted 20 November 2026."), a preprint, not peer reviewed), audited 160 documents and finds two comparisons of a standard library model with measured data-center events: both reported a mismatch under default parameters, neither stated an acceptance criterion, and per-event refitting was never tested on an unseen event. In the sources reviewed, there is “no successful held-out validation of a frozen, facility-specific data-center model against an independent measured disturbance,” and 25 of the 33 model–phenomenon combinations with any evidence involve no electrical measurement. The new rules’ distinctive features — memory of repeated dips, recovery within 0.5–3 s, proportional reduction during the sag, and overvoltage response — are, he argues, ones current phasor models cannot represent or have never been tested against. Operator procedures he examined include no comparison of the submitted model with a measured facility response.

Implication: The [23 November brief](https://lizhouyu.github.io/technical_posts/posts/ercot-batch-zero-vrt-cap-efficiency-terl/ "23 November Daily Brief: ERCOT’s preliminary Batch Zero voltage ride-through tests showed a 31% pass rate and a 69% fail rate, mostly from load loss.") on [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: the grid operator for most of Texas.")’s 31% preliminary Batch Zero pass rate sits on this evidence gap. If energization is gated on models that have not been held-out tested, a high fail rate may say as much about the models as about the halls.

**Sources:** [arXiv 2611.27169](https://arxiv.org/abs/2611.27169 "Abstract and PDF.") and the [HTML full text](https://arxiv.org/html/2611.27169v1 "Source of the 160-document audit, the two library-model comparisons, the 25-of-33 measurement gap, and the 0.5–3 s recovery statement.").

### 4. Mixed accelerators cut a 6.5% bill under a grid envelope — in a 125 kW case · submitted 20 Nov 2026 · academia / capping and flexibility

Chenghao Lyu, Ying Yu, Wangkun Xu and Fei Teng at [Imperial College London](https://www.imperial.ac.uk/ "Imperial College London.") (arXiv [2611.27576](https://arxiv.org/abs/2611.27576 "Lyu, Yu, Xu and Teng, Unlocking Heterogeneous Accelerator Flexibility in AI Data Centers, arXiv 2611.27576, submitted 20 November 2026.")) jointly size two accelerator classes and allocate training, delay-tolerant batch work, and same-hour inference across two sites subject to hourly grid envelopes. Their UK-inspired benchmark gives London a 125 kW peak envelope and Edinburgh a 185 kW envelope. Class H is calibrated to a 700 W training GPU; Class S to a 350–400 W inference accelerator. Against a fixed-capacity spatio-temporal schedule (GBP 5,653.8/day), the proposed design (GBP 5,288.6/day) cuts daily cost 6.5% with no envelope-violation penalty. An unconstrained run pushes London 5.04 kW over the cap for four hours; staying inside costs 0.25%. During the evening bind, 7.29% of southern queries are rerouted to Edinburgh.

Implication: Hardware mix and same-hour routing can be the instruments that keep a site inside a tight cap — which is what a PALS-style floor or a limited interconnection will demand. The envelopes are 125 kW and 185 kW. This is a stylized two-site optimization, not a measured hall.

**Sources:** [arXiv 2611.27576](https://arxiv.org/abs/2611.27576 "Abstract: 6.5% and 0.25% claims.") and the [HTML full text](https://arxiv.org/html/2611.27576 "Source of Table I, the 125/185 kW envelopes, the 5.04 kW exceedance, the 0.25% shadow cost, and the 7.29% reroute.").

## Spotlight: the model is now the interconnection gate

Ride-through is no longer a best-practice slide. ERCOT is already withholding Initial Energization from Batch Zero projects whose models do not demonstrate the required performance. Cheerla’s review finds no held-out comparison of a frozen facility-specific model with a measured disturbance, and no such comparison in the operator procedures he examined. The gap to close is a measured-event validation protocol with an acceptance criterion.

## Bottom line

SPP would let flexible campuses connect as non-firm load that must drop to zero above USD 25/MWh, while capping how much of the hook-up bill can be socialized. Texas has authorized a 2,582 MW behind-the-meter plant as the off-grid alternative for a Vantage campus — an air permit, not a switch-on. The models that now gate ride-through have not been held-out tested, and a 6.5% saving in a 125 kW case is not a hall result. SPP’s terms are still a filing.

## Also noted

- [Applied Digital](https://ir.applieddigital.com/news-events/press-releases/detail/165/applied-digital-secures-new-150-mw-18-year-lease-with "Applied Digital press release, 23 November 2026, 8:00 a.m. ET.") (23 November) signed an 18-year, 150 MW critical-IT lease with an unnamed investment-grade hyperscaler (about USD 5.4 billion of base-term revenue).
- [OpenAI](https://developers.openai.com/api/docs/changelog "OpenAI API changelog, 17 November 2026: 30% and 40% discounts for two-hour and eight-hour background completion windows.") (17 November) added two-hour and eight-hour [background completion windows](https://developers.openai.com/api/docs/guides/background "OpenAI docs: the 2h window is 30% below Standard token rates; the 8h window is 40% below.") in the Responses API public beta, at 30% and 40% below Standard token rates — a delay-tolerant inference handle, not a measured campus ramp service.
- Bera et al. (arXiv [2611.25176](https://arxiv.org/abs/2611.25176 "Bera, Chaudhary, Pandit, Newlun, Nguyen, Byrne and Mitra, Reliability-based Sizing of Energy Storage for Large Load Integration, arXiv 2611.25176, submitted 18 November 2026. CIGRE US National Committee Grid of the Future 2026.")) size and site energy storage for large-load additions on the RTS-GMLC test system; a CIGRE symposium paper, not a field trial.

## Glossary

- [**ABI-1**](https://records.tceq.texas.gov/cs/idcplg?IdcService=TCEQ_EXTERNAL_SEARCH_GET_FILE&Rendition=Web&dID=10265116&searchType=External): VoltaGrid’s ABI-1 Electric Generating Unit in Shackelford County, Texas.
- [**AIDC**](https://lizhouyu.github.io/technical_posts/posts/aidc-power-stack-and-shortlist/): AI data center.
- [**BTM**](https://en.wikipedia.org/wiki/Distributed_generation): Behind-the-meter generation, serving on-site or adjacent load.
- [**CO2e**](https://en.wikipedia.org/wiki/Carbon_dioxide_equivalent): Carbon-dioxide equivalent.
- [**FERC**](https://www.ferc.gov/): Federal Energy Regulatory Commission.
- [**ISO-NE**](https://www.iso-ne.com/): ISO New England.
- [**LMP**](https://en.wikipedia.org/wiki/Locational_marginal_pricing): Locational marginal price.
- [**LSHL**](https://www.powermag.com/five-grid-operators-respond-to-ferc-with-distinct-plans-for-large-load-integration/): SPP’s proposed Load Safe Harbor Limit.
- [**NSR**](https://www.tceq.texas.gov/): New Source Review, the US air-construction permit process.
- [**Oversubscription**](https://lizhouyu.github.io/technical_posts/posts/power-oversubscription-brief/): Contracting or operating more IT load than the upstream path can supply at coincident peak.
- [**PALS**](https://elibrary.ferc.gov/eLibrary/filelist?accession_number=20261119-5243): SPP’s proposed Price Adaptive Load Service.
- [**PUE**](https://en.wikipedia.org/wiki/Power_usage_effectiveness): Power usage effectiveness.
- [**Ride-through**](https://lizhouyu.github.io/technical_posts/posts/caiso-20mw-pjm-fast-energization-gfm-halls/): Remaining connected through a grid fault or voltage sag.
- [**SPP**](https://www.spp.org/): Southwest Power Pool.
- [**TCEQ**](https://www.tceq.texas.gov/): Texas Commission on Environmental Quality.

---

_How useful was today’s brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
