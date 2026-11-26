# KVM VPS: How Much RAM and How Many vCores You Actually Need, What Annual Pricing Really Costs, and Which SixtyNet Plan Fits (Full Plan Table + Checklist)

KVM VPS pricing runs from about **$3.19/month** for a 256 MB box on a 36-month prepay up to roughly **$1,000/month** for 64 vCores and 256 GB of RAM. What separates those two numbers is RAM, billing term, and whether the network is generic transit or something built for a specific route. The word "KVM" itself costs nothing: it's open source and baked into the Linux kernel, so every host on this list ships it for free.

SixtyNet, the host linked from this page, sits in the middle of that range at **$200 to $2,500 per year**, billed annually, from a single Los Angeles location, with a specialty in residential IP addresses. Below you get three things: a rule for matching RAM and cores to a workload, the real arithmetic behind cheap annual pricing, and a checklist to run before you pay for twelve months up front.

## Quick pick: what most readers should buy

> **LAX-STARTER** — 2 vCPU, 2 GB RAM, 40 GB NVMe, 5 TB traffic, DDoS protection, **$200.00/year** (list $240.00, save 17%), about $16.67/month equivalent.
> Enough for a small WordPress site, a Docker host running three or four containers, a VPN, or a monitoring box.
> Not for you if you need a residential IP (the LAX plans don't carry the port 80/443 restriction), a European location, or the ability to walk away after 30 days.
> 👉 [Check the LAX-STARTER annual price at SixtyNet](https://sixtynet.net/aff.php?aff=39)

## Every SixtyNet plan on the pricing page

All plans below are billed annually. Prices are as listed at the time of writing, with the pre-discount figure shown in brackets.

| Plan | vCPU / RAM | NVMe storage | Traffic | Annual price | Order |
| --- | --- | --- | --- | --- | --- |
| LAX-STARTER | 2 / 2 GB | 40 GB | 5 TB | $200.00 ($240.00) | [Order LAX-STARTER](https://sixtynet.net/aff.php?aff=39) |
| LAX-MEDIUM | 8 / 8 GB | 160 GB | 20 TB | $800.00 ($960.00) | [Order LAX-MEDIUM](https://sixtynet.net/aff.php?aff=39) |
| LAX-LARGE | 8 / 16 GB | 320 GB | 40 TB | $1,600.00 ($1,920.00) | [Order LAX-LARGE](https://sixtynet.net/aff.php?aff=39) |
| IRVINE-PRO-STARTER (2C config) | 2 / 2 GB | 40 GB | 5 TB | $350.00 ($420.00) | [Order IRVINE-PRO](https://sixtynet.net/aff.php?aff=39) |
| IRVINE-PRO (4C config) | 4 / 4 GB | 80 GB | 10 TB | listed under the same group | [Order IRVINE-PRO](https://sixtynet.net/aff.php?aff=39) |
| Los Angeles China Unicom-Premium | 2 to 16 / 2 to 16 GB | 40 to 320 GB | 5 to 40 TB | $2,500.00 ($3,000.00) | [Order China Unicom-Premium](https://sixtynet.net/aff.php?aff=39) |

Three things the table compresses:

- **The LAX line is the general-purpose one.** It lists DDoS protection and no residential IP, so ports 80 and 443 behave normally.
- **The Irvine and China Unicom groups show one headline price across several configurations.** The page displays 2, 4, 8 and 16-core builds under a single figure, so confirm which configuration maps to which price on the order page before you pay. NVMe IOPS are listed at 12,500 on the smaller builds and 25,000 on the larger ones.
- **Residential IP plans close ports 80 and 443.** SixtyNet states this directly on the pricing page as an IP risk-control measure. You cannot serve a public website from those plans.

Both the Irvine and China Unicom groups carry an extra clause worth reading twice: the Irvine plans refund to website balance rather than to your card.

## What KVM is, and where it differs from OpenVZ

KVM turns the Linux kernel itself into a hypervisor, so a physical machine can run several virtual machines that each behave like separate hardware. Three differences matter when you're comparing hosts.

**Each VM has its own kernel.** That means you can install any operating system, including Windows Server, FreeBSD, or a custom ISO you upload yourself. OpenVZ is container-based and only runs Linux.

**Resources are dedicated, not pooled.** A KVM VPS gets an allocated slice of CPU and RAM. OpenVZ containers share the node's resources, so a noisy neighbour on the same box can affect your throughput.

**Every VM gets its own virtual hardware and its own IP address.** That's why a KVM box with two IPs (SixtyNet's larger builds, Koddos's KVM C and D) can run two separate services on separate addresses.

One naming trap: "KVM" also refers to a remote console feature (Keyboard, Video, Mouse) that lets you access a server as if you were sitting in front of it. If you searched for KVM because you want out-of-band console access during a broken boot, that's a control panel feature, not a virtualization type, and you should confirm your host offers it. OVHcloud spells out the distinction in its own FAQ, which suggests enough people ask.

## The three ways a "cheap" price is calculated

**1. The billing term does most of the work.** Rad Web Hosting advertises a 1 vCPU / 256 MB / 4 GB plan at $3.19/month. The same plan is $8.00/month on a monthly term. Same hardware, 2.5x the price, and the difference is a 36-month commitment paid up front. SixtyNet doesn't offer a monthly option on the plans above at all: $200/year works out to $16.67/month, but $200 leaves your account on day one.

**2. The spec floor tells you what you're actually getting.** That $3.19 plan has 256 MB of RAM and 4 GB of disk. Koddos's cheapest KVM plan, at $12.95/month with no contract, gives you 512 MB and 10 GB. Neither will run cPanel, Plesk, or a Docker stack with a database and a cache in it. SixtyNet's smallest plan starts at 2 GB and 40 GB, which is why its entry price is $200 rather than $40.

**3. Extras are priced separately, and they add up.** Windows licensing is an add-on at OVHcloud. cPanel is listed as optional across Koddos's range. Backups are included at OVHcloud and Liquid Web but you should confirm per host rather than assume.

Put the arithmetic together and a year of SixtyNet's LAX-STARTER costs $200. Two years costs $400. A monthly-billed Koddos KVM B with similar specs (2 cores, 2 GB, 40 GB, 1 TB traffic) runs $29.95/month, or $359.40 for a year, with no commitment. SixtyNet is cheaper per month by a wide margin and more expensive in flexibility, because your exit window is three days.

That window is the number to internalise. SixtyNet's refund policy gives a full refund, minus handling fees, within **3 days of invoice creation**, and only if your used transfer quota stays under **5 GB**. Refunds go back to the original payment method. Pull a database backup, run a speed test, and you can burn through 5 GB before lunch.

👉 [Review the SixtyNet plans and annual pricing before committing](https://sixtynet.net/aff.php?aff=39)

## Market benchmark: what other hosts charge

Pulled from provider pages at the time of writing. No links, no promo codes, just the numbers so you can place SixtyNet's pricing.

| Host | Entry spec | Price | Term |
| --- | --- | --- | --- |
| Rad Web Hosting | 1 vCPU / 256 MB / 4 GB | $3.19/mo ($8.00 monthly) | 36-month prepay |
| Koddos | 1 core / 512 MB / 10 GB | $12.95/mo | Monthly, no contract |
| Liquid Web | 1 vCPU / 4 GB / 120 GB | $17/mo | Monthly |
| Liquid Web | 3 vCPU / 2 GB / 60 GB | $22/mo | Monthly |
| Vyper Hosting | 2 vCores / 4 GB / 50 GB NVMe | £8.00/mo | Monthly |

The Liquid Web pair is the most instructive line in that table. The $17 plan has one vCPU and 4 GB. The $22 plan has three vCPUs and 2 GB. Paying $5 more buys you two extra cores and half the memory, because one is built for databases and caches and the other for CI pipelines and video encoding. Counting cores and assuming more is better gets you the wrong server.

Set against that, SixtyNet's LAX-STARTER at $16.67/month equivalent gives you 2 vCPU, 2 GB and 5 TB of traffic. On cores and traffic it beats the $17 Liquid Web plan. On commitment it loses badly: Liquid Web bills monthly, SixtyNet bills yearly.

## Match the plan to the workload

**Static site or small blog.** 1 vCPU and 1 GB is enough, 20 to 40 GB of disk. SixtyNet's smallest plan doubles both, which costs you nothing extra in practice but is more than the job needs. If you want to spend $5 a month instead of $17, a monthly-billed host is the right call here.

**WordPress with a database, plus email.** 2 vCPU and 2 GB is the realistic floor, with 40 GB of NVMe. LAX-STARTER fits exactly. Below 2 GB, MySQL and PHP start competing for memory during traffic spikes and you'll be tuning swap instead of writing posts.

**Docker with several containers.** 4 GB of RAM. Each container carries its own overhead and a database container alone will sit on 512 MB to 1 GB. Rad's ladder prices a 4 vCPU / 4 GB / 64 GB build at $23.54/month on a 36-month term, or $59.00 monthly. SixtyNet jumps from 2 GB to 8 GB with nothing in between, so if you land on 4 GB as your target, the LAX-MEDIUM at $800/year is more machine than you asked for.

**Game server or CI runner.** Cores and clock speed matter more than memory. Liquid Web's $22 CPU plan (3 vCPU, 2 GB) is the shape you want. SixtyNet's LAX-MEDIUM gives 8 cores and 8 GB for $66.67/month equivalent, which is reasonable for a busy game server but overkill for a hobby one.

**Anything that needs to look like a home connection.** This is SixtyNet's actual specialty: scraping, social accounts, ad verification, anything where a datacenter IP gets flagged. The China Unicom-Premium and Irvine groups exist for this. Remember the port restriction, and remember the Irvine group refunds to account balance rather than cash.

**Where to stop.** A single WordPress site doing under 20,000 visits a month does not need 8 GB. Moving from LAX-STARTER to LAX-MEDIUM costs an extra $600 a year and buys capacity you won't use until something changes about your traffic or your stack.

👉 [Compare the SixtyNet configurations side by side](https://sixtynet.net/aff.php?aff=39)

## Six checks before you pay for a year

1. **Renewal price.** SixtyNet's $200 is already a discounted annual rate against a $240 list. Ask what the second year costs before you treat $200 as your ongoing budget.
2. **Commitment length.** Annual only, no monthly option on these plans. There is no partial refund if you leave in month four.
3. **The refund terms.** Three days from invoice creation, 5 GB of transfer used, handling fees deducted. That's the whole safety net.
4. **Ports 80 and 443.** Closed on residential IP plans by policy. If you plan to host a website, buy from the LAX line.
5. **Windows licensing.** OVHcloud charges extra for Windows, and KVM itself supports it. Confirm the licence cost on the order page rather than assuming it's bundled.
6. **Control panel and backups.** cPanel and Plesk are paid add-ons at most hosts. SixtyNet's page doesn't state backup policy in the plan listings, so open a ticket and ask before you migrate data.

## FAQ

**Can a KVM VPS run Windows?**
Yes. Every VM has its own kernel, so Windows Server, FreeBSD, and custom ISOs all install normally. The licence is usually a separate line item, as it is at OVHcloud.

**Is "KVM" the same as the KVM console?**
No. KVM virtualization is the hypervisor. The KVM console is a Keyboard/Video/Mouse remote session in your control panel, useful when a bad config locks you out of SSH. They share an acronym and nothing else.

**Is 1 vCPU enough?**
For a low-traffic WordPress site or a single-purpose service, yes. For CI jobs, video transcoding, or a Minecraft server with a handful of players, no. The existence of a $3.19 plan with one core and 256 MB tells you how small the floor goes; it also tells you that 256 MB won't host a control panel.

**Does "unlimited traffic" mean unlimited?**
It depends on the host. OVHcloud advertises unlimited traffic with bandwidth up to 3 Gbps, excluding its Asia-Pacific datacenters. SixtyNet doesn't use that language at all: each plan carries a hard cap, from 5 TB on LAX-STARTER to 40 TB on LAX-LARGE and the top China Unicom build. A cap is easier to budget against than a fair-use clause.

**Can I host a public website on a residential IP plan?**
No. Ports 80 and 443 are closed on SixtyNet's residential plans to keep the IPs clean. Use the LAX plans for anything the public needs to reach.

## Which one to order

If you're running a small site, a VPN, or a handful of containers and you can live with a US West Coast location: **LAX-STARTER at $200/year**, and treat the first three days as your trial period.

If you need 8 cores and the traffic allowance that comes with them: **LAX-MEDIUM at $800/year** works out to $66.67/month, and the 20 TB cap is the reason to pick it over two smaller boxes.

If your work depends on residential IP addresses rather than on serving pages: the **Irvine or China Unicom-Premium** groups, with the port restriction and the balance-only refund understood up front.

Before you pay, confirm two things: the renewal rate for year two, and the exact configuration attached to the price you're looking at on the multi-config groups. Both take one support ticket.

👉 [Start from the SixtyNet plan list and pick the RAM tier that matches your stack](https://sixtynet.net/aff.php?aff=39)
