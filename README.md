# co-located data center: What It Actually Costs, When It Beats Cloud, and Where DMIT Fits In

You searched "co-located data center," which usually means one of two things: you're trying to figure out whether colocation makes sense for hardware you already own (or plan to buy), or you're comparing it against cloud/VPS options and want real numbers before committing. Both questions are worth answering properly, because the marketing around colocation tends to be either too vague ("scalability! reliability!") or too narrow (one vendor's price sheet with no context).

This guide breaks down what a co-located data center actually is, where it wins and loses against cloud, what real colocation footprints look like, and how a provider like DMIT — which runs both colocation and cloud out of the same carrier-neutral facilities in Los Angeles, Hong Kong, and Tokyo — fits into the decision. Pricing and plan details below come from DMIT's current public pages, checked against what's live on the site right now.

## What "Co-Located Data Center" Actually Means

A co-located (or "colo") data center is a facility where you rent space, power, cooling, and network connectivity for your own hardware. The provider owns the building, the racks, the power infrastructure, the cooling, and often the upstream network — but the servers, switches, and storage sitting inside the cabinet are yours. You ship them, the provider racks them, and you either manage them remotely or pay for remote-hands service when something needs hands-on attention.

This is different from cloud hosting, where the provider owns the compute layer and you rent VMs or instances by the hour or month. It's also different from dedicated/bare-metal servers, where the provider owns the hardware and rents you exclusive use of it. With colocation, the only thing you're renting is the physical environment and the pipe.

The trade-off is straightforward: colocation costs more up front (you buy the hardware) but tends to cost less per unit of compute over time, especially once a workload is steady and predictable. Cloud costs less to start and scales more easily, but the per-unit price stays higher for as long as you run it.

## When Colocation Beats Cloud (and When It Doesn't)

Colocation makes the most sense when:

- **You already own hardware** or have a strong reason to own it — custom builds, specialized GPUs, storage arrays, or gear you've already amortized.
- **Your workload is steady and predictable.** If you're running the same 10 servers at 60% utilization 24/7, you're almost certainly overpaying on cloud. Colocation turns that into a fixed monthly rack cost plus bandwidth.
- **You need control** over the hardware, BIOS, firmware, or physical security that a cloud provider won't give you. Compliance, data sovereignty, and certain regulated workloads fall here.
- **You want hybrid architecture.** Keep steady-state workloads on owned hardware in colo, burst into cloud when needed. This is one of the more common real-world patterns.

Cloud tends to win when:

- **Traffic is spiky or short-term.** A two-week marketing campaign or a seasonal e-commerce surge doesn't justify buying servers.
- **You need to launch fast.** Cloud gets you live in minutes; colo means shipping hardware, racking, and waiting.
- **Your team is small and ops-light.** Colocation still requires someone to manage the OS, patching, and hardware failures. If you don't have that capacity, managed cloud or managed dedicated is usually a better fit.

The honest version: most teams that ask about colocation are already past the "just use cloud" stage and are trying to figure out the crossover point where owning hardware starts to pay off. That point is usually somewhere between 12 and 24 months of steady, similar-sized usage — but it depends heavily on the hardware, the colo facility, and how much bandwidth you actually consume.

## What Real Colocation Footprints Look Like

DMIT's colocation page lays out three standard tiers, which match what most carriers and colo providers offer:

- **Rack Units (1U–4U):** You rent individual U positions in a shared, secured cabinet. Best for a single server, an edge node, or a small appliance. This is the cheapest entry point and lets you grow into more units without committing to a full cabinet.
- **Half Cabinet:** A lockable half cabinet with dedicated power and bandwidth. Suited to mid-size clusters or storage where you want isolation from other tenants but don't need a full rack yet.
- **Full Cabinet:** A full rack with committed power and bandwidth, for dense or high-power deployments. Private cages are available on request for larger footprints.

DMIT explicitly notes that plans, footprints, power, and bandwidth shown on the colocation page are "for reference only" and that final pricing varies by location and capacity — you need to contact sales for an actual quote. This is normal for colocation; unlike VPS pricing, colo quotes depend on your specific power draw, port speed, bandwidth commitment, and contract length.

What DMIT does publish clearly is the facility-level spec sheet, which matters more than the per-U price for most buyers:

- **Locations:** Los Angeles, Hong Kong (inside Equinix HK2), and Tokyo — all carrier-neutral.
- **Power:** N+1 UPS with diesel generator backup, diverse utility feeds, A/B power options, metered or fixed pricing.
- **Cooling:** Precision cooling with hot/cold aisle containment.
- **Security:** Badge and biometric access, 24/7 CCTV, on-site guards, Tier III-class audited facilities.
- **Network:** Multi-carrier, carrier-neutral fabric with cross-connects to carriers and IXes; 1G / 10G / 100G port options.
- **Operations:** 24/7 remote-hands service covering reboots, part swaps, media handling, scheduled inspections, and emergency response.
- **Install service:** Equipment receiving, racking, structured cabling, labeling, BIOS/IPMI setup, and testing on turn-up.

The facility SLA is 99.99% uptime, which is the standard you'd expect from a Tier III-class site.

## Colocation vs. Cloud: A Quick Decision Framework

If you're trying to decide between the two for a specific workload, the practical questions are:

1. **Do you already own the hardware, or would you have to buy it?** If you'd have to buy, factor in the capital cost plus 3–5 years of refresh cycles.
2. **How steady is the workload?** Steady = colo-friendly. Spiky or unknown = cloud-friendly.
3. **How much bandwidth do you actually use?** Bandwidth is where colo quotes vary wildly. A 1Gbps committed port at a carrier-neutral facility is a very different cost proposition than 1Gbps unmetered at a single-carrier site.
4. **Do you have remote-hands needs?** If your team can't physically reach the facility, the quality of the provider's remote-hands service matters a lot.
5. **What's your latency target?** Colocation in Hong Kong or Tokyo puts you closer to APAC users than most US-based cloud regions; colocation in Los Angeles gives you strong trans-Pacific routing.

## DMIT's Full Cloud Instance Pricing (For Comparison)

If you're weighing colocation against cloud, you need to know what cloud actually costs at the same provider. DMIT runs three network profiles across three locations, and the differences are mostly about routing quality and bandwidth allocation — not raw CPU/RAM.

The plans below are what's currently published on DMIT's cloud instance page. All prices are monthly, with free setup, and include 1 IPv4 + 1 IPv6 (/64 or /48 depending on plan), basic DDoS protection, and root access.

### Los Angeles Cloud Instances

**Premium Network** (Tier 1 + premium transit including China Telecom CN2 GIA — best for China-optimized routing):

| Plan | CPU | RAM | Storage | Bandwidth | Port | Price/mo |
| --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.STARTER | 2 vCores | 2GB DDR4 | 80GB SSD | 3000GB BIDI | 10Gbps | $29.90 |
| LAX.Pro.MINI | 4 vCores | 4GB DDR4 | 80GB SSD | 5000GB BIDI | 10Gbps | $58.88 |
| LAX.Pro.MICRO | 4 vCores | 4GB DDR4 | 160GB SSD | 7000GB BIDI | 10Gbps | $74.99 |

**Eyeball Network** (Tier 1 + reasonable-effort China routing via CMIN2 or similar — middle ground):

| Plan | CPU | RAM | Storage | Bandwidth | Port | Price/mo |
| --- | --- | --- | --- | --- | --- | --- |
| LAX.EB.STARTER | 2 vCores | 2GB DDR4 | 80GB SSD | 5000GB BIDI | 10Gbps | $29.90 |
| LAX.EB.MINI | 4 vCores | 4GB DDR4 | 80GB SSD | 10000GB BIDI | 10Gbps | $58.88 |
| LAX.EB.MICRO | 4 vCores | 4GB DDR4 | 160GB SSD | 14000GB BIDI | 10Gbps | $74.99 |

**Tier 1 Network** (standard internet routing, no China optimization — cheapest):

| Plan | CPU | RAM | Storage | Bandwidth | Port | Price/mo |
| --- | --- | --- | --- | --- | --- | --- |
| LAX.T1.STARTER | 1 vCore | 2GB DDR4 | 40GB SSD | 4000GB (IN+OUT) | Performance-based | $12.90 |
| LAX.T1.MINI | 2 vCores | 2GB DDR4 | 60GB SSD | 8000GB (IN+OUT) | Performance-based | $21.90 |
| LAX.T1.MICRO | 4 vCores | 4GB DDR4 | 80GB SSD | 16000GB (IN+OUT) | Performance-based | $32.90 |

### Hong Kong Cloud Instances

**Premium Network** (CN2 GIA, 1Gbps port):

| Plan | CPU | RAM | Storage | Bandwidth | Price/mo |
| --- | --- | --- | --- | --- | --- |
| HKG.Pro.STARTER | 1 vCore | 2GB DDR4 | 40GB SSD | 800GB BIDI | $79.90 |
| HKG.Pro.MINI | 2 vCores | 2GB DDR4 | 60GB SSD | 1200GB BIDI | $119.90 |
| HKG.Pro.MICRO | 4 vCores | 4GB DDR4 | 80GB SSD | 1600GB BIDI | $159.90 |

**Eyeball Network** (CMI or similar, 2–4Gbps best-effort):

| Plan | CPU | RAM | Storage | Bandwidth | Price/mo |
| --- | --- | --- | --- | --- | --- |
| HKG.EB.STARTERv2 | 1 vCore | 2GB DDR4 | 40GB SSD | 2000GB BIDI | $59.90 |
| HKG.EB.MINIv2 | 2 vCores | 2GB DDR4 | 60GB SSD | 3000GB BIDI | $89.90 |
| HKG.EB.MICROv2 | 4 vCores | 4GB DDR4 | 80GB SSD | 4000GB BIDI | $129.90 |

**Tier 1 Network** (standard routing):

| Plan | CPU | RAM | Storage | Bandwidth | Price/mo |
| --- | --- | --- | --- | --- | --- |
| HKG.T1.STARTER | 1 vCore | 2GB DDR4 | 40GB SSD | 4000GB (IN+OUT) | $12.90 |
| HKG.T1.MINI | 2 vCores | 2GB DDR4 | 60GB SSD | 8000GB (IN+OUT) | $21.90 |
| HKG.T1.MICRO | 4 vCores | 4GB DDR4 | 80GB SSD | 16000GB (IN+OUT) | $32.90 |

### Tokyo Cloud Instances

**Premium Network** (1Gbps port):

| Plan | CPU | RAM | Storage | Bandwidth | Price/mo |
| --- | --- | --- | --- | --- | --- |
| TYO.Pro.STARTER | 1 vCore | 2GB DDR4 | 40GB SSD | 500GB BIDI | $39.90 |
| TYO.Pro.MINI | 2 vCores | 2GB DDR4 | 60GB SSD | 1000GB BIDI | $79.90 |
| TYO.Pro.MICRO | 4 vCores | 4GB DDR4 | 80GB SSD | 2000GB BIDI | $159.90 |

**Eyeball Network** (2–4Gbps best-effort):

| Plan | CPU | RAM | Storage | Bandwidth | Price/mo |
| --- | --- | --- | --- | --- | --- |
| TYO.EB.STARTER | 1 vCore | 2GB DDR4 | 40GB SSD | 2000GB BIDI | $55.90 |
| TYO.EB.MINI | 2 vCores | 2GB DDR4 | 60GB SSD | 3000GB BIDI | $85.90 |
| TYO.EB.MICRO | 4 vCores | 4GB DDR4 | 80GB SSD | 4000GB BIDI | $119.90 |

**Tier 1 Network** (standard routing):

| Plan | CPU | RAM | Storage | Bandwidth | Price/mo |
| --- | --- | --- | --- | --- | --- |
| TYO.T1.STARTER | 1 vCore | 2GB DDR4 | 40GB SSD | 4000GB (IN+OUT) | $12.90 |
| TYO.T1.MINI | 2 vCores | 2GB DDR4 | 60GB SSD | 8000GB (IN+OUT) | $21.90 |
| TYO.T1.MICRO | 4 vCores | 4GB DDR4 | 80GB SSD | 16000GB (IN+OUT) | $32.90 |

### Premium Network (LAX AS3 Series)

DMIT's pricing page also lists a Premium Network series on the LAX AS3 platform, which is still being built out. The plans and prices currently shown:

| Plan | CPU | RAM | Storage | Bandwidth | Port | Price/mo |
| --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 vCore | 2GB | 20GB SSD | 1000GB | 1Gbps | $10.90 |
| Pocket | 2 vCores | 2GB | 40GB SSD | 1500GB | 4Gbps | $16.90 |
| STARTER | 2 vCores | 2GB | 80GB SSD | 3000GB | 10Gbps | $34.90 |
| MINI | 4 vCores | 4GB | 80GB SSD | 5000GB | 10Gbps | $62.90 |
| MICRO | 4 vCores | 4GB | 160GB SSD | 7000GB | 10Gbps | $87.90 |
| MEDIUM | 6 vCores | 8GB | 160GB SSD | 15000GB | 10Gbps | $199.90 |

DMIT warns that the AS3 platform may have reduced disk performance and a lower SLA than its mature platforms while it's being optimized.

### Full Plan Comparison Table

For a single-view comparison, here's every plan currently listed across all locations and networks, with purchase links:

| Plan | Location | Network | CPU | RAM | Storage | Bandwidth | Port | Price/mo | Buy |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.STARTER | Los Angeles | Premium | 2 vCores | 2GB | 80GB SSD | 3000GB BIDI | 10Gbps | $29.90 | [Get LAX Pro Starter](https://bit.ly/DmiT) |
| LAX.Pro.MINI | Los Angeles | Premium | 4 vCores | 4GB | 80GB SSD | 5000GB BIDI | 10Gbps | $58.88 | [Get LAX Pro Mini](https://bit.ly/DmiT) |
| LAX.Pro.MICRO | Los Angeles | Premium | 4 vCores | 4GB | 160GB SSD | 7000GB BIDI | 10Gbps | $74.99 | [Get LAX Pro Micro](https://bit.ly/DmiT) |
| LAX.EB.STARTER | Los Angeles | Eyeball | 2 vCores | 2GB | 80GB SSD | 5000GB BIDI | 10Gbps | $29.90 | [Get LAX EB Starter](https://bit.ly/DmiT) |
| LAX.EB.MINI | Los Angeles | Eyeball | 4 vCores | 4GB | 80GB SSD | 10000GB BIDI | 10Gbps | $58.88 | [Get LAX EB Mini](https://bit.ly/DmiT) |
| LAX.EB.MICRO | Los Angeles | Eyeball | 4 vCores | 4GB | 160GB SSD | 14000GB BIDI | 10Gbps | $74.99 | [Get LAX EB Micro](https://bit.ly/DmiT) |
| LAX.T1.STARTER | Los Angeles | Tier 1 | 1 vCore | 2GB | 40GB SSD | 4000GB | Perf-based | $12.90 | [Get LAX T1 Starter](https://bit.ly/DmiT) |
| LAX.T1.MINI | Los Angeles | Tier 1 | 2 vCores | 2GB | 60GB SSD | 8000GB | Perf-based | $21.90 | [Get LAX T1 Mini](https://bit.ly/DmiT) |
| LAX.T1.MICRO | Los Angeles | Tier 1 | 4 vCores | 4GB | 80GB SSD | 16000GB | Perf-based | $32.90 | [Get LAX T1 Micro](https://bit.ly/DmiT) |
| HKG.Pro.STARTER | Hong Kong | Premium | 1 vCore | 2GB | 40GB SSD | 800GB BIDI | 1Gbps | $79.90 | [Get HKG Pro Starter](https://bit.ly/DmiT) |
| HKG.Pro.MINI | Hong Kong | Premium | 2 vCores | 2GB | 60GB SSD | 1200GB BIDI | 1Gbps | $119.90 | [Get HKG Pro Mini](https://bit.ly/DmiT) |
| HKG.Pro.MICRO | Hong Kong | Premium | 4 vCores | 4GB | 80GB SSD | 1600GB BIDI | 1Gbps | $159.90 | [Get HKG Pro Micro](https://bit.ly/DmiT) |
| HKG.EB.STARTERv2 | Hong Kong | Eyeball | 1 vCore | 2GB | 40GB SSD | 2000GB BIDI | 2Gbps | $59.90 | [Get HKG EB Starter](https://bit.ly/DmiT) |
| HKG.EB.MINIv2 | Hong Kong | Eyeball | 2 vCores | 2GB | 60GB SSD | 3000GB BIDI | 2Gbps | $89.90 | [Get HKG EB Mini](https://bit.ly/DmiT) |
| HKG.EB.MICROv2 | Hong Kong | Eyeball | 4 vCores | 4GB | 80GB SSD | 4000GB BIDI | 4Gbps | $129.90 | [Get HKG EB Micro](https://bit.ly/DmiT) |
| HKG.T1.STARTER | Hong Kong | Tier 1 | 1 vCore | 2GB | 40GB SSD | 4000GB | Perf-based | $12.90 | [Get HKG T1 Starter](https://bit.ly/DmiT) |
| HKG.T1.MINI | Hong Kong | Tier 1 | 2 vCores | 2GB | 60GB SSD | 8000GB | Perf-based | $21.90 | [Get HKG T1 Mini](https://bit.ly/DmiT) |
| HKG.T1.MICRO | Hong Kong | Tier 1 | 4 vCores | 4GB | 80GB SSD | 16000GB | Perf-based | $32.90 | [Get HKG T1 Micro](https://bit.ly/DmiT) |
| TYO.Pro.STARTER | Tokyo | Premium | 1 vCore | 2GB | 40GB SSD | 500GB BIDI | 1Gbps | $39.90 | [Get TYO Pro Starter](https://bit.ly/DmiT) |
| TYO.Pro.MINI | Tokyo | Premium | 2 vCores | 2GB | 60GB SSD | 1000GB BIDI | 1Gbps | $79.90 | [Get TYO Pro Mini](https://bit.ly/DmiT) |
| TYO.Pro.MICRO | Tokyo | Premium | 4 vCores | 4GB | 80GB SSD | 2000GB BIDI | 1Gbps | $159.90 | [Get TYO Pro Micro](https://bit.ly/DmiT) |
| TYO.EB.STARTER | Tokyo | Eyeball | 1 vCore | 2GB | 40GB SSD | 2000GB BIDI | 2Gbps | $55.90 | [Get TYO EB Starter](https://bit.ly/DmiT) |
| TYO.EB.MINI | Tokyo | Eyeball | 2 vCores | 2GB | 60GB SSD | 3000GB BIDI | 2Gbps | $85.90 | [Get TYO EB Mini](https://bit.ly/DmiT) |
| TYO.EB.MICRO | Tokyo | Eyeball | 4 vCores | 4GB | 80GB SSD | 4000GB BIDI | 4Gbps | $119.90 | [Get TYO EB Micro](https://bit.ly/DmiT) |
| TYO.T1.STARTER | Tokyo | Tier 1 | 1 vCore | 2GB | 40GB SSD | 4000GB | Perf-based | $12.90 | [Get TYO T1 Starter](https://bit.ly/DmiT) |
| TYO.T1.MINI | Tokyo | Tier 1 | 2 vCores | 2GB | 60GB SSD | 8000GB | Perf-based | $21.90 | [Get TYO T1 Mini](https://bit.ly/DmiT) |
| TYO.T1.MICRO | Tokyo | Tier 1 | 4 vCores | 4GB | 80GB SSD | 16000GB | Perf-based | $32.90 | [Get TYO T1 Micro](https://bit.ly/DmiT) |
| LAX AS3 TINY | Los Angeles | Premium (AS3) | 1 vCore | 2GB | 20GB SSD | 1000GB | 1Gbps | $10.90 | [Get LAX AS3 Tiny](https://bit.ly/DmiT) |
| LAX AS3 Pocket | Los Angeles | Premium (AS3) | 2 vCores | 2GB | 40GB SSD | 1500GB | 4Gbps | $16.90 | [Get LAX AS3 Pocket](https://bit.ly/DmiT) |
| LAX AS3 STARTER | Los Angeles | Premium (AS3) | 2 vCores | 2GB | 80GB SSD | 3000GB | 10Gbps | $34.90 | [Get LAX AS3 Starter](https://bit.ly/DmiT) |
| LAX AS3 MINI | Los Angeles | Premium (AS3) | 4 vCores | 4GB | 80GB SSD | 5000GB | 10Gbps | $62.90 | [Get LAX AS3 Mini](https://bit.ly/DmiT) |
| LAX AS3 MICRO | Los Angeles | Premium (AS3) | 4 vCores | 4GB | 160GB SSD | 7000GB | 10Gbps | $87.90 | [Get LAX AS3 Micro](https://bit.ly/DmiT) |
| LAX AS3 MEDIUM | Los Angeles | Premium (AS3) | 6 vCores | 8GB | 160GB SSD | 15000GB | 10Gbps | $199.90 | [Get LAX AS3 Medium](https://bit.ly/DmiT) |

A few things worth noting when reading these prices:

- **Tier 1 plans are the same price across all three locations** ($12.90 / $21.90 / $32.90). The difference between LAX, HKG, and TYO on Tier 1 is latency to your users, not the bill.
- **Premium and Eyeball prices jump significantly in Hong Kong and Tokyo** because you're paying for CN2 GIA / CMI routing and lower-latency APAC connectivity. If your users aren't in China or APAC, Tier 1 in LAX is usually the better deal.
- **Bandwidth is the big differentiator within the same location.** Eyeball gives you roughly 1.7–2x the monthly transfer of Premium at the same price point, in exchange for "reasonable effort" China routing instead of CN2 GIA.
- **Port speeds on Tier 1 are "based on performance"** — meaning DMIT doesn't guarantee a specific port speed, and actual throughput depends on node load and network conditions.

## IP Transit and Bandwidth: The Other Half of Colocation

If you're going the colocation route, bandwidth is where most of the recurring cost lives, and DMIT's IP Transit page is worth understanding before you request a colo quote.

DMIT offers three bandwidth models:

- **95th Percentile:** Usage-based billing on the 95th percentile of sampled throughput. You pay for sustained usage, not short peaks. Best for variable or bursty traffic.
- **Committed + Burst:** You reserve a committed rate at a preferred price and can burst above it when needed. Predictable baseline cost with headroom for peaks. Best price per Mbps at scale.
- **Flat / Unmetered:** Fixed monthly price for a full-speed port, no usage metering. Fully predictable budgeting, best for high-volume steady workloads.

Port speeds available are 1G, 10G, and 100G. The IP Transit service also includes:

- **Tier 1 upstream carriers** including Cogent, NTT, GTT, Arelion, Tata, Zayo, Telstra, RETN, PCCW, and Zenlayer (logos shown for identification, not endorsement).
- **Full BGP toolkit** — BGP communities, AS-PATH prepend, selective announcement, traffic engineering, and remote-triggered blackhole (RTBH).
- **IP & ASN management** — IPv4/IPv6 allocations, BYOIP with LOA, ASN application assistance, RPKI ROA, IRR objects, and rDNS delegation.
- **Always-on DDoS protection** with automatic detection, traffic scrubbing, BGP Flowspec, and customizable mitigation policies.

DMIT's aggregate Tier 1 backbone capacity is listed at 7.6Tbps under ideal conditions, with the caveat that this may be adjusted based on network operating conditions.

Like colocation, IP Transit pricing is quote-based and varies by location, port speed, committed rate, and contract terms — you need to contact sales for actual numbers.

## Current Promotions and Discount Codes

DMIT runs periodic promotions, typically tied to holidays. The most recent confirmed event was the **2025 Christmas promotion**, which ended on the date shown on the event page. The codes below are listed for reference, but the event page explicitly states the promotion has ended — they are almost certainly no longer functional:

| Code | Applies To | Discount | Status |
| --- | --- | --- | --- |
| 2025-XMAS-LAX-PRO-EB-ANNUALLY-STARTER-AND-HIGHER-15OFF-RECURRING | LAX Pro & EB annual STARTER+ | 15% recurring + 10% creditback | Ended |
| 2025-XMAS-LAX-PRO-EB-10-OFF-RECURRING | LAX Pro & EB regular plans | 10% recurring + 5% creditback | Ended |
| 2025-XMAS-LAX-T1-ANNUALLY-EXCL-WEE-TINY-20OFF-RECURRING | LAX T1 annual (excl. WEE & TINY) | 20% recurring + 10% creditback | Ended |
| 2025-XMAS-LAX-T1-10-OFF-RECURRING | LAX T1 (excl. WEE) | 10% recurring + 5% creditback | Ended |

DMIT's Terms of Service (Section 18.6) explicitly states that discount codes only apply to new customers, and that using a code not issued to you can result in service suspension and refusal of refund. Don't try expired or someone else's code — DMIT's system identifies accounts by natural person/legal person and will flag the order.

If a new promotion is live when you read this, it'll be linked from the DMIT homepage. The pattern is consistent: recurring discounts on annual billing, plus account creditback distributed monthly over the billing cycle. LAX T1 annual plans have historically seen the deepest discounts (up to 20% recurring).

## DMIT's Refund and SLA Policies (Read Before You Buy)

A few policy details worth knowing up front:

- **Refund window:** Full refund within 3 days of purchase and under 30GB transfer used. Partial refund within 30 days, calculated on either remaining transfer or remaining time (whichever is lower). Renewal orders and credit-funded invoices are non-refundable.
- **Non-refundable cases:** DDoS-targeted services, "network not good enough" complaints, IP geographic location issues, and any abuse-related loss. Also, if you've had 3 refunds on the same product series, further refunds are refused.
- **SLA:** Currently 99%. If SLA drops below 99%, you get half a month's compensation; below 95%, a full month; below 90%, two months. You must notify DMIT within 3 days of the triggering event to claim credits.
- **IP replacement:** For Premium and Eyeball profiles, free replacement every 7 days with IP Care+, or every 15 days without. Without either, immediate replacement costs $5. For Premium Secure, it's $15 per replacement with 30-day spacing. For Tier 1, $5 per replacement with 7-day spacing without IP Guarantee+.
- **Unmanaged service:** Most DMIT services are unmanaged; support ticket reply is guaranteed within 72 hours. If you need managed support, that's a separate conversation.
- **OFAC restrictions:** DMIT does not accept orders from Cuba, Iran, Lebanon, Libya, Myanmar, North Korea, Somalia, Sudan, or Syria.

The refund policy is tighter than most cloud providers — the 30GB transfer cap on full refunds is the main one to watch. If you're testing a plan, keep your transfer under 30GB in the first 3 days to keep the refund option open.

## How DMIT's Colocation and Cloud Fit Together

The reason DMIT is worth considering for a "co-located data center" decision is that they run both sides of the equation out of the same facilities. If you start on cloud and your workload grows to the point where colocation makes sense, you can move to owned hardware in the same building, with the same upstream carriers, the same DDoS protection, and the same network team. That's not a trivial advantage — moving from a cloud provider to a colo provider usually means re-architecting your network, getting new IP space, and rebuilding BGP sessions.

DMIT's colocation is explicitly a quote-based product. The page lists the footprint tiers (1U–4U, half cabinet, full cabinet), the facility specs, and the bandwidth models, but final pricing depends on your specific hardware, power draw, port speed, and bandwidth commitment. The same applies to IP Transit.

If you want to start the conversation, the colocation and IP Transit pages both have a "Let's Plan Your Colocation" / "Let's Design Your IP Transit" contact form. For cloud instances, the plans above are publicly priced and deploy in minutes — you can 👉 [browse DMIT's current cloud plans](https://bit.ly/DmiT) and deploy directly.

## A Practical Recommendation

If you're reading this because you're trying to decide between colocation and cloud at DMIT specifically:

- **Start with cloud if you're not sure.** A LAX T1 STARTER at $12.90/mo gives you a real workload running in a real DMIT facility, with a real refund window. You'll learn more about your actual bandwidth and compute needs in 30 days than from any planning document.
- **Move to colocation when your cloud bill stabilizes.** If you're running 4–6 cloud instances at the MEDIUM tier ($199.90/mo each) and the workload is steady, that's roughly $1,000–$1,200/mo — which is well past the crossover point where a half or full cabinet with owned hardware starts to pay off.
- **Use Hong Kong or Tokyo Premium only if you have APAC users.** The price premium for CN2 GIA / CMI routing only makes sense if your traffic actually goes to or through China. For global or US-centric workloads, LAX Tier 1 or LAX Eyeball is the better value.
- **Get a colo quote before you buy hardware.** DMIT's colocation pricing varies by location and capacity, and the quote will tell you whether the facility you want has space, what power density is available, and what the bandwidth actually costs — none of which you can infer from the cloud pricing page.

The short version: a co-located data center makes sense when you have steady workloads, hardware you own or plan to own, and a need for control or specific geography that cloud can't cheaply provide. DMIT is one of the few providers that lets you start on cloud and migrate to colocation in the same facility, with the same network — which makes the crossover decision a lot easier to actually execute.
