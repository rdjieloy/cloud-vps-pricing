# Cloud hosting server price: what $12, $45 and $89 a month actually buy, what gets added to the bill later, and how to pick a plan you won't outgrow (full Spin Servers table)

Two cloud servers with the same vCPU and RAM count can sit 30% apart on the invoice, and the difference rarely comes from the headline rate. HostAdvice's cloud hosting guide (updated October 2026) puts basic plans at **$5 to $10 a month** and business-oriented configurations at **$50 to $300 or more**. Inside those bands, the bill is set by four things the marketing page usually buries: how much transfer is included and what happens past it, how many IPv4 addresses you get, whether backups and extra storage are priced separately, and whether billing is hourly or monthly.

This article works through the published Spin Servers KVM VPS line, which runs from **$12 to $89 a month**, and then prices the extras that decide whether a $12 plan really costs $12.

> Most readers running a dev box, a staging environment or a small production app should start at Spin Servers' **$12/month plan**: 2 vCPU, 2 GB RAM, 40 GB RAID-10 SSD, 4 TB of monthly transfer, one IPv4 and one IPv6. If the app is already live and taking real traffic, jump to **$45**: it costs $6 more than the $39 tier and doubles both the cores and the disk.
> 👉 [See the current Spin Servers KVM VPS plans and prices](https://bit.ly/Spinservers)

## The full Spin Servers VPS line, as published

Every plan below is listed at a monthly price in USD, on a 1 Gbps port, with one IPv4 and one IPv6 address included.

| Plan | Cores / RAM | SSD + monthly transfer | Price | Order |
| --- | --- | --- | --- | --- |
| KVM 2vCPU 2GB | 2 vCPU / 2 GB DDR4 | 40 GB RAID-10 SSD, 4 TB | $12.00/mo | [ 2 vCPU plan](https://bit.ly/Spinservers) |
| KVM 4vCPU 4GB | 4 vCPU / 4 GB DDR4 | 80 GB RAID-10 SSD, 8 TB | $29.00/mo | [ 4 vCPU plan](https://bit.ly/Spinservers) |
| KVM 6vCPU 8GB | 6 vCPU / 8 GB DDR4 | 120 GB RAID-10 SSD, 8 TB | $39.00/mo | [ 6 vCPU plan](https://bit.ly/Spinservers) |
| KVM 8vCPU 8GB | 8 vCPU / 8 GB DDR4 | 160 GB RAID-10 SSD, 10 TB | $45.00/mo | [ 8 vCPU plan](https://bit.ly/Spinservers) |
| KVM 12vCPU 12GB | 12 vCPU / 12 GB DDR4 | 160 GB RAID-10 SSD, 10 TB | $62.00/mo | [ 12 vCPU plan](https://bit.ly/Spinservers) |
| KVM 16vCPU 16GB | 16 vCPU / 16 GB DDR4 | 320 GB RAID-10 SSD, 15 TB | $74.00/mo | [ 16 vCPU plan](https://bit.ly/Spinservers) |
| Hybrid KVM 32vCPU 32GB | 32 vCPU / 32 GB | 500 GB SSD, 20 TB | $89.00/mo | [ 32 vCPU plan](https://bit.ly/Spinservers) |

Two steps in that ladder are worth more attention than the entry price. The **$39 plan** buys 6 cores, 8 GB and 120 GB of disk. For **$6 more**, the $45 plan gives you 8 cores, the same 8 GB, 160 GB of disk and 2 TB more transfer, so the $39 tier only makes sense if $6 is genuinely the constraint. The same pattern repeats higher up: the **$74 plan** (16 cores, 16 GB, 320 GB, 15 TB) is nearly doubled by the **$89 Hybrid KVM** (32 cores, 32 GB, 500 GB, 20 TB) for $15 more. Unless you have a specific reason to stay on the 16-core tier, the $89 listing is the stronger buy.

Spin Servers also sells pre-built dedicated servers, which matter if you need whole-machine isolation rather than a slice. These listings were read from the official instant dedicated server store and tracked at $79 to $390 a month as of late September 2026. Stock and configuration change, so confirm the current price on the order page.

| Listing | Cores / RAM | Storage + transfer | Price | Order |
| --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5 (Dallas) | 4 vCPU / 32 GB | 1 TB NVMe, 30 TB | $79/mo | [ E3-1280 v5](https://bit.ly/Spinservers) |
| Intel Xeon E3-1280 v5 (San Jose) | 4 vCPU / 32 GB | 1 TB NVMe, 30 TB | $79/mo | [ San Jose listing](https://bit.ly/Spinservers) |
| Dual Intel Xeon Gold 6148 (Dallas) | 40 vCPU / 256 GB | 3.84 TB SSD, 30 TB | $235/mo | [ Gold 6148](https://bit.ly/Spinservers) |
| Dual Intel Xeon Platinum 8173M (Dallas) | 56 vCPU / 512 GB | 7.68 TB SSD, 30 TB | $390/mo | [ Platinum 8173M](https://bit.ly/Spinservers) |

## What the sticker price leaves out

Extra IPv4 addresses are the most common silent line item. Atlantic.Net includes one IPv4 with each server and charges **$3.65/month** for another. UpCloud charges **€3.47/month** for either a floating IP or an additional public IPv4. Cloudzy lists floating IPs at **$2.50/IP/month**. Two spare IPs on a $12 VPS can add 40% to 60% to the monthly total at those rates, which is why the address count on the plan card deserves a second look. Spin Servers lists one IPv4 plus one IPv6 with every VPS plan in the table, so the base configuration covers a normal web stack, and you should ask what a second address costs if you separate mail or terminate TLS on a dedicated IP.

Backups are the second line item, and the pricing models differ enough to break a comparison. UpCloud prices simple backups as a percentage of the server plan: **+10%** for daily backups retained 24 hours, **+20%** for a week, **+40%** for a month, **+60%** for a year, with separate per-GB rates for Cloud Native, GPU and additional storage devices. On a €28 plan, the month plan adds €11.20. Atlantic.Net offers optional daily backups as a paid extra without publishing a rate on the page reviewed. Spin Servers' plan page does not state a backup price either, so if you need scheduled snapshots, get the number in writing before ordering.

Block storage is priced per gigabyte per month, not folded into the plan. UpCloud's MaxIOPS tier is **€0.220/GB/mo**, Standard is **€0.085/GB/mo**, Archive is **€0.056/GB/mo** outside Helsinki, and a custom image costs **€0.330/GB/mo**. A 500 GB Standard volume is €42.50 a month, more than the server itself on the low tiers. That is the mechanism behind most "the same specs cost 30% more here" complaints.

## Three ways providers count transfer

Spin Servers bundles a fixed monthly allowance with each plan, from 4 TB on the $12 tier to 20 TB on the $89 Hybrid, all on a 1 Gbps port. The plan page does not publish an overage rate, so ask what happens at 100% before you commit to a backup target, a media origin or a video workload.

The other models look like this.

**Zero-rated transfer.** UpCloud lists public outbound, public inbound, private outbound and private inbound at **€0.00/GiB**. If your traffic pattern is unpredictable, or your app pulls large payloads between nodes, that removes the entire category from your forecast.

**Allowance with an alert.** Cloudzy meters outbound traffic against each plan's allowance and states that exceeding it triggers a notice rather than throttling. The plans run from 1 TB on the $3.48 tier to 16 TB on the $199.98 tier.

**Allowance, overage, and a ratio clause.** Kamatera's unmetered 5000 Mb package has no speed limit and includes up to 5000 GB a month, with additional data billed per GB. The clause that catches people: **when incoming traffic exceeds 33% of total traffic, you're billed for the entire traffic volume**, calculated on a 2:1 transmit-to-receive ratio. Kamatera notes that roughly 90% of its clients stay under 2000 GB a month. Inbound-heavy workloads such as backup receivers, mirrors or log aggregators should read that sentence twice.

## The first price you see is a term, not a rate

Cloudzy's price page shows every VPS plan at **50% off a struck-through list price** (1 GB at $3.48 against a $6.95 list, 16 GB at $49.98 against $99.95) and separately advertises a discount for annual billing. Treat those as promotional numbers tied to a term, and check what the plan renews at before you build a budget on them. The page does state a **14-day money-back** window, which limits the downside of trying.

Kamatera's billing rules are published in more detail than most. A monthly server is prepaid at creation for the configuration you select, and later upgrades are added as a prorated amount. Terminating a monthly server means paying only for the current month, and if you terminate after a new month begins you aren't charged for it. Hourly servers bill according to whether the machine is powered on, and billing stops at termination. There is a **30-day free trial worth up to $100 on one server**.

UpCloud bills everything by the hour and currently offers a 30-day free trial. It has also published a **price change effective 16 November** covering previous Cloud Server plans, Standard and Archive block storage, and Windows Server licenses. If you are signing up in the first half of November, budget from the new figures rather than today's page. The same announcement says the new Starter plans replace the current Developer plans at an average of 25% less than the previous generation, with a 99.99% SLA.

Spin Servers publishes monthly pricing and a plan ladder. A free trial, a refund window and an hourly option are not stated on the plan page, so those are questions for support rather than assumptions.

## The fine print that decides whether a plan works

Spin Servers closes **port 25 (SMTP) by default on every VPS**. Reopening it requires a support ticket with a justification, and the company reserves the right to deny the request. If you run a mail server, or your app sends transactional email straight from the instance, this is a decision-changing detail. Either route mail through an external relay or confirm the port situation before you order.

The rest of the standard specification is unremarkable in a good way: RAID-10 SSD storage, a 1 Gbps network port, one IPv4 and one IPv6 per plan, and locations in Dallas and San Jose.

## Which plan fits which job

**Dev, test, CI runners, staging environments.** The $12 plan is the right size. Two cores and 2 GB handle a couple of containers or a small Postgres instance, and 4 TB of transfer is far beyond what a test box generates. Paying more here buys capacity you won't use.

**A small production app, or a site that has outgrown shared hosting.** Go to $45 and skip $39. Eight cores and 160 GB of disk for $6 over the 6-core tier is the best value step in the entire line, and 10 TB of transfer covers a content site with images at a scale most small teams never reach.

**Multiple services, build agents, a database plus app plus queue on one box.** The $89 Hybrid KVM gives 32 cores, 32 GB and 500 GB, and it undercuts the $74 tier on a per-core basis by a wide margin.

**Workloads that need a whole machine.** The $79 Xeon E3-1280 v5 listing pairs 32 GB of RAM with 1 TB of NVMe and 30 TB of transfer, which is close to VPS pricing for dedicated hardware. Move to the $235 or $390 listings only when 256 GB or 512 GB of RAM is a hard requirement.

**GPU inference.** None of the plans in the tables above include a GPU, so check whether Spin Servers offers a GPU line before comparing it to GPU VPS pricing elsewhere. For reference, Cloudzy lists a single RTX 4090 at **$506.35/mo promotional ($779 list)** and a single A100 at **$714.35/mo ($1,099 list)**, which sets the scale for that category.

One piece of reverse advice worth taking seriously: HostAdvice's guide argues that if you are on shared hosting and pulling fewer than 100,000 page views a month, the chances are slim you actually need to move to cloud infrastructure. The trigger for moving is a resource ceiling you keep hitting, not the category itself.

## How the entry prices compare

| Provider | Entry price (verified) | What the entry tier includes | Billing notes |
| --- | --- | --- | --- |
| Kamatera | $4/mo | Config-your-own server, 99.9% SLA, 30-day trial up to $100 | Monthly prepay, prorated upgrades, hourly option |
| UpCloud | €3/mo | 1 GB RAM, 1 core, 10 GB storage, zero transfer fees | Hourly billing, 30-day trial, backups +10% to +60% |
| Cloudzy | $3.48/mo promo ($6.95 list) | 1 GB, 1 vCPU, 25 GB NVMe, 1 TB transfer | Promotional rate tied to term, 14-day money-back, free snapshots |
| Atlantic.Net | No plan price published on the page reviewed | 1 IPv4 included, 30-second deployment, RAID-10 SSD | Pay-as-you-go or reserved, extra IPv4 $3.65/mo |
| Spin Servers | $12/mo | 2 vCPU, 2 GB, 40 GB RAID-10 SSD, 4 TB transfer, 1 IPv4 + 1 IPv6 | Monthly, Dallas and San Jose |

Spin Servers costs roughly three times the cheapest entry tiers from Kamatera, UpCloud and Cloudzy, and it bundles more at that floor: two cores rather than one, 2 GB rather than 1 GB, 40 GB of disk and 4 TB of transfer. If the goal is the smallest possible 1 GB box for a side project, this isn't the cheapest option and there's no reason to pretend otherwise. The value shows from 8 cores upward, where 10 to 20 TB of included transfer separates it from providers that meter every gigabyte.

## Questions buyers actually ask

**What is the minimum spend to get something running?** Spin Servers starts at $12/month for a usable 2 vCPU, 2 GB box. Kamatera advertises $4/month and UpCloud €3/month for smaller configurations, so $3 to $12 is the realistic floor for a single small cloud server.

**What happens if I go over the transfer allowance?** It depends entirely on the provider. Cloudzy says it alerts rather than throttles. Kamatera bills per GB past 5000 GB and switches to billing all traffic if inbound exceeds 33% of the total. Spin Servers publishes an allowance per plan without an overage rate, so confirm the policy before signing up for anything bandwidth-heavy.

**Can I pay monthly and cancel whenever?** Spin Servers lists monthly pricing. Kamatera allows termination at any time with billing limited to the current month for monthly servers. Cloudzy offers a 14-day money-back window. Spin Servers' refund terms aren't on the plan page, so ask before you order.

**Do I have to migrate to upgrade?** Spin Servers sells a fixed ladder of plans, and the page doesn't describe an in-place resize. Ask support whether an upgrade keeps the same IP and disk before you plan a growth path around it. Kamatera prorates upgrades on monthly servers, and Cloudzy says most in-panel RAM, vCPU and storage upgrades complete within 60 seconds without downtime.

**Are backups included in the price?** Not at Spin Servers as far as the plan page shows. UpCloud charges 10% to 60% of the plan price depending on retention. Budget backups as a separate line unless the provider states otherwise.

## The short version

A dev box, a staging environment or a first container host maps to the **$12 plan**. A live application with real traffic maps to the **$45 plan**, because the $6 gap over the 6-core tier buys twice the compute. Anything running several services, or a workload where 16 cores already feels tight, maps to the **$89 Hybrid KVM**, which nearly doubles the $74 tier for $15 more.

Before you check out, confirm four things in writing: whether billing is hourly or monthly and what happens to partial months, what the transfer overage rate is, whether port 25 can be opened for your use case, and what the refund window actually covers. Those four answers decide the real cost of cloud hosting far more than the number on the plan card.

👉 [Compare the Spin Servers KVM VPS plans and pick your tier](https://bit.ly/Spinservers)
