# Colocation Data Centers: What a Rack Really Costs, How Much Power You Get, and When One Server Beats a Cage

Colocation data centers answer three questions at once: is there power left in the building, can the heat be removed, and how long until capacity is live. A GPU-based AI rack now draws more than 250 kW, about ten times what a rack pulled a decade ago, so the checklist that worked for a 5 kW cabinet in 2015 will not tell you whether a facility can host the hardware you bought this year.

What follows is the part most guides skip: where the monthly bill grows past the rent, the density numbers worth bringing to a site tour, and the workloads where signing a colo lease is the wrong move. For readers who need a handful of physical servers rather than a cage, there is a shorter path with published prices, and those are in the table below.

> **Short answer for a lot of readers:** if the requirement is a few single-tenant servers and not a rack, SpinServers lists bare-metal dedicated servers from **$79/mo**, billed month to month with no setup fee, in Dallas or San Jose. Dual 10Gbps ports, IPMI console access and a 99.99% uptime SLA come standard. 👉 [Check the current bare-metal pricing](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278)

## Current SpinServers plans and prices

These are the configurations listed on the provider's own store page. Every plan is month to month with no setup fee, and provisioning runs about 30 minutes when the hardware is in stock.

| Plan (CPU) | RAM | Storage | Bandwidth | Price / month | Order |
| --- | --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5, Dallas (4 vCPU) | 32 GB | 1 TB NVMe | 30 TB | $79 | [View plan](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278) |
| Intel Xeon E3-1280 v5, San Jose (4 vCPU) | 32 GB | 1 TB NVMe | 30 TB | $79 | [View plan](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278) |
| Dual Intel Xeon Gold 6148, Dallas (40 vCPU) | 256 GB | 3.84 TB SSD | 30 TB | $235 | [View plan](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278) |
| Dual Intel Xeon Platinum 8173M, Dallas (56 vCPU) | 512 GB | 7.68 TB SSD | 30 TB | $390 | [View plan](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278) |

Two notes on the table. The San Jose listing costs the same as Dallas at the entry level, which is unusual, since Silicon Valley space normally carries a premium, so confirm the current figure in the cart before you commit. And these are unmanaged machines: you get the hardware, the console and the network, and the operating system and everything above it stays your job, exactly as it would inside a colo cage.

## What a colocation contract actually covers

The provider supplies the building, the power feed, the cooling, physical security and the cross-connects into carrier and cloud networks. You supply the servers, the OS, the software, and the network design that decides how traffic enters and leaves the building.

That last item catches people. Two tenants in the same hall with identical racks can measure very different latency, because one bought private cross-connects and diverse cloud on-ramps while the other routed over the public internet. Colocation hands you the plumbing; the architecture inside it is still yours to design, and so is your own access control on top of whatever the facility runs.

Three commercial models sit under the same roof:

- **Retail colocation** sells a partial rack, a full rack or a cage. It is the most common form you will encounter, usually priced by floor space plus a power allowance, sometimes as a lockable cabinet with a fixed amperage.
- **Wholesale colocation** sells whole halls or large blocks of capacity to organizations with serious power requirements, at rates below the retail standard. Hyperscalers and AI-focused cloud providers lease wholesale space specifically to add capacity faster than they could build it themselves.
- **Managed colocation** is the same lease with the operations outsourced: equipment procurement, monitoring, patching, backups. It differs from a managed data center in that you genuinely lease the physical space.

A carrier hotel is a related animal: a downtown building where a long list of carriers and cloud providers terminate their networks and interconnect, which is why latency-sensitive tenants still pay a premium to sit inside one.

## Where the bill grows past the rent

Base rent buys floor space and a power allowance. Electricity above that allowance, cooling, bandwidth, cross-connects, remote hands and technical support are separate line items. Rates move with the metro and with the facility tier, and billing can be flat monthly or metered by usage.

Contract terms matter more than the headline rate. Multi-year commitments are standard, hardware management stays with you, and the total accumulates over the term while your control over the underlying plant stays limited. The power portion is the least predictable part of the bill, because energy demand charges, continuous cooling load and grid upgrades all feed into it.

Four questions that make two quotes comparable:

1. Is power bundled up to a stated amperage per cabinet, and what is the metered rate above it?
2. What does each cross-connect cost per month, and is there a one-time install fee?
3. Are remote hands included as a block of hours, or billed per call with a minimum increment?
4. When you expand from one cage to two, does the whole contract reprice or only the added capacity?

If the answers add up to more overhead than the workload justifies, a bare-metal server folds power, cooling, bandwidth and hardware into one monthly figure with nothing metered on top. 👉 [Compare the $79 and $235 configurations](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278)

## The density numbers that decide whether a facility can host AI

Conventional air cooling cannot move the heat concentrated in an AI rack. Direct-to-chip liquid cooling removes up to 75% of rack heat load, and rear-door heat exchangers handle roughly 80 kW per rack depending on the unit, which makes them a practical complement to chip-level cooling rather than a replacement. Vertiv's reference architecture for the NVIDIA GB200 NVL72 platform supports up to 132 kW per rack, and its OCP-aligned rack concepts go to 142 kW.

Power delivery is the other half of the problem. The typical path runs medium-voltage AC into the building, 480V or 415V for facility distribution, then another conversion at the rack, often to 54 VDC. Traditional AC distribution starts hitting physical limits somewhere between 350 and 400 kW per rack, where conductor losses, current and the sheer volume of copper compete for space, which is why the industry is moving toward 800 VDC architectures that cut current and reclaim room for compute.

Ask about speed to power while you are at it. Grid capacity and interconnection queues set how fast a facility can hand over live capacity, so the useful question is not how many megawatts the campus advertises but how quickly a specific rack can be energized.

Most of this is irrelevant if your AI work is a handful of inference or training machines rather than a rack-scale deployment. The 56 vCPU, 512 GB configuration sits at the top of the published lineup for that kind of single-tenant density. 👉 [See the highest-core-count bare-metal plan](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278)

## Who should not buy colocation

The honest version of this section matters more than the sales version.

**Regulated and security-sensitive workloads.** Government, healthcare and financial services with strict data protection or sovereignty requirements may find shared infrastructure fails their compliance bar. Owning the facility gives full visibility and lets you tune the risk profile of each workload separately. Some regulated industries do run in certified colo facilities to inherit the certifications, but that call belongs with your compliance team.

**Workloads that scale up and down hourly.** Rapid autoscaling is far easier in cloud than in a physical point of presence, and no colo contract fixes that.

**Early-stage companies.** The residual infrastructure overhead, the cross-connect minimums, the remote hands bills, can outweigh the benefit when a fully virtual setup would do.

**Sub-rack footprints.** Retail colo will happily sell you space for one server, but the administrative and connectivity minimums make that single server expensive next to a dedicated machine that gives you the same single-tenancy without a lease.

## What SpinServers is, and what it is not

SpinServers publishes a bare-metal catalogue, not colo space. The machines sit in Tier III facilities in Dallas and San Jose that carry SOC2, HIPAA and PCI compliance, on a multihomed network under the company's own ASN with DDoS protection in front. You get full IPMI/iKVM console access, dual 10Gbps ports as the baseline rather than an add-on, and free layer-2 private networking between your own servers, which covers the isolation problem that pushes some buyers toward a cage in the first place.

The trade is straightforward. You give up the ability to stand in the room and pull a cable yourself, and you take on the OS and application layer as you would in any colo. You keep single-tenant hardware, a fixed monthly price and no multi-year commitment. Third-party reviews consistently mention provisioning inside the advertised 30 minutes and responsive tickets, and at least one customer who moved from colocation to these servers described the support as the best they had dealt with in a decade, which is a useful signal for anyone leaving a cage behind.

If you genuinely need a private cage or more than a couple of racks, ask them directly whether they will quote it. Build your plan around what is published, not around what a sales page implies.

## Six things to confirm before you sign anything

1. **Deliverable power and date.** How many kW to your rack, and when can it be live? This is now the binding constraint on expansion, not floor space.
2. **Redundant paths.** Separate power and network routes into the building, plus duplicated cooling and server components, so maintenance happens without an outage.
3. **SLA and planned maintenance.** Read the maintenance process alongside the uptime number. A 99.99% promise means little if the window for scheduled work is undefined.
4. **Remote hands billing.** Included hours or per-incident charges, and what counts as an incident.
5. **Cross-connect and cloud on-ramp fees.** These are recurring and rarely in the headline rate.
6. **Expansion pricing.** The rate you sign at one cage is not always the rate at three.

Shared facilities also mean shared physical security. Your provider's mantraps and badge logs do not replace your own access rules, encryption and audit trail.

## FAQ

**Retail or wholesale colocation?** Retail for a rack or a cage, wholesale for halls and blocks of capacity with substantial power behind them. Retail is the common entry point; wholesale is a procurement exercise with its own contract terms.

**How much does colocation cost?** There is no list price. You are quoted per site on space, power allowance, cooling, bandwidth and services, and the same rack can price very differently between a tier-one metro and a secondary market. Ask for an all-in monthly figure that names every line item, then compare.

**Can you run a GPU cluster in a colocation data center?** Yes, if the facility has the power and cooling for it. That means liquid cooling, medium-voltage distribution, and a plan for racks that may draw well over 100 kW. Most facilities built before 2020 were designed around far lower densities.

**How long are colo contracts?** Multi-year terms are normal, and renewal pricing is negotiable at signing. Month-to-month arrangements exist at the small end of retail, usually at a higher rate.

**Colocation or cloud?** Steady, predictable load with hardware you control tends to favor owned or leased physical infrastructure. Spiky, short-lived, autoscaling workloads favor cloud. Most organizations end up with both.

**Colocation or a dedicated server?** A dedicated server is the right starting point when the answer to "how much space do you need" is "one machine" or "five machines". Colocation starts making sense when you need physical control of the hardware, custom components, or a rack's worth of capacity.

## How to decide

- **One to a few servers, single-tenant hardware, fixed monthly cost:** bare metal. At $79/mo with dual 10Gbps and no setup fee, the entry plan is cheaper than the cross-connects alone in most colo contracts.
- **A rack or more, or hardware you must physically own for compliance or custom components:** retail colocation, with the six questions above answered in writing.
- **Whole halls and hundreds of kW:** wholesale, negotiated as a capacity deal rather than a rental.
- **Workloads that triple for six hours and drop back:** cloud, unless you enjoy paying for idle racks.

Two things to settle before you order anything: confirm the exact RAM and storage configuration in the cart rather than on the marketing page, since listings change, and confirm the plan is in stock if the 30-minute provisioning time is part of your timeline. 👉 [Start with the $79 Dallas or San Jose plan](https://www.spinservers.com/index.php?rp=%2Fstore%2Finstant-dedicated-servers-pre-built&aff=278)
