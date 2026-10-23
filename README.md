# virtual server rent: What $2.50 and $29 a Month Actually Buy, All 28 VPS Plans Compared, and the Refund Fine Print

Renting a virtual server in late 2026 splits into two markets that barely talk to each other. One sells a 512 MB sandbox for $2.48 a month and has it online in under a minute. The other sells a $29 to $999 a month machine whose entire justification is the route its packets take toward mainland China.

Neither shelf is better. Which one you belong on comes down to a single question: are your users, customers or players sitting behind China Telecom, China Unicom or China Mobile? If yes, the cheap shelf will disappoint you at the worst possible hour. If no, paying for premium China routing is money spent on nothing.

What follows is the cost landscape for virtual server rent in 2026, where GoMami's China-route plans sit inside it, every plan the company currently lists, and the fine print that decides whether the sticker price is the real price.

> **The short version.** If your traffic comes from mainland China, the plan most people start on is HKG Pulse Mini: 2 vCPU, 4 GB RAM, 60 GB NVMe, 1 TB of traffic on a 1 Gbps port, listed at $59/month. The cheapest route onto the same network at list price is JPN or SIN Pulse Nano at $29/month. There is also a promotional path: LAX Pulse Nano has been advertised at roughly $23.20/month with the `Hi,LAX` code, which would make it the lowest monthly entry to the whole lineup, though promo validity changes and needs checking in the cart. If you want a cheap sandbox for a bot, a cron job or a staging site, rent elsewhere for $2.50 to $9.
> 👉 [See every GoMami plan and the current price on each one](https://bit.ly/Gomami)

## What does virtual server rent cost in 2026?

Roughly $2.50 to $10 a month for a small commodity box, $29 to $100 for China-optimized routing, and $100 and up for real concurrent production load. Those bands hardly overlap, and understanding the gap between them is more useful than comparing spec sheets line by line.

The low end is crowded and genuinely cheap. Cloudzy advertises $2.48/month for 512 MB of DDR5, 1 vCPU, 20 GB NVMe and 1 TB of traffic on a 40 Gbps uplink, with a 14-day money-back window across 13 regions. ML Cloud starts at $8.99 for 2 vCPU, 2 GB and 50 GB NVMe. LikeVPS starts at $9.60 with a 25-country footprint. KernelHost sells KVM VDS from €4.99. If price per gigabyte of RAM is your only metric, that shelf wins and there is nothing to argue about.

The upper band is where things get specific. A $29/month machine with 2 GB of RAM looks like terrible value as hardware, and by that measure it is. What you are buying is the path the packets take.

| Provider type | Entry price | Typical entry spec | Refund window | What you're paying for |
| --- | --- | --- | --- | --- |
| Commodity VPS (Cloudzy) | $2.48/mo | 1 vCPU, 512 MB, 20 GB NVMe, 1 TB | 14 days | Cheap compute, 13 regions |
| Commodity VPS (ML Cloud) | $8.99/mo | 2 vCPU, 2 GB, 50 GB NVMe | Not stated | Simple hourly or monthly billing |
| Commodity VPS (KernelHost) | €4.99/mo | KVM VDS, dedicated allocation | Not stated | Isolated resources |
| China-route VPS (GoMami) | $29/mo | 2 vCPU, 2 GB, 40 GB NVMe, 500 GB | 24 hours, first purchase only | CN2 / AS9929 / CMIN2 return routing |

One more variable that never shows up in the headline price: billing period. GoMami's documentation states that annual billing typically saves 15% to 20% compared with monthly, with the exact discount varying by product line. That is a wide enough range that you should look at the cart rather than do arithmetic from a review.

## Why GoMami starts at $29 when commodity boxes start at $2.50

Because the expensive component is the return path, not the RAM. GoMami Networks, LLC sells what it calls China Mainland Optimized Pro routing over three premium backbones: China Telecom's CN2, China Unicom's AS9929 and China Mobile's CMIN2. Every plan in every line runs that stack, and the entry price reflects it.

The official documentation gives per-node latency expectations rather than one blanket number: Hong Kong under 30 ms, Tokyo under 50 ms, Singapore under 70 ms, with a note that real figures vary by local ISP and time of day. The homepage compresses all of this into "RTT <50ms across mainland China," which is roughly fair for Hong Kong and generous for Singapore.

Port speeds run from 1 Gbps on the entry plans up to 10 Gbps on LAX Pulse Titan. That is unusual for this category, where China-optimized plans often come on far narrower ports.

The hardware choices are also out of character for the price tier. Hong Kong's Turin line runs AMD EPYC 9575F (Zen 5, up to 5.0 GHz) with PCIe Gen5 U.2 storage and DDR5-6400 memory. The Peak X5 line runs a desktop Ryzen 9 9950X at up to 5.7 GHz. Third-party Geekbench 6 results cited for the Turin chip land around 2892 single-core, close to a desktop 9950X and well above what a shared VM normally delivers. Independent benchmark write-ups also report sustained throughput around 2.16 Gbps to Singapore at 40.4 ms and roughly 1.76 Gbps toward Shenzhen Telecom on Hong Kong Turin hardware. Treat those as third-party test figures rather than guarantees.

One structural detail worth knowing before you compare lines: the Asia nodes use premium return routing with direct forward paths, while Los Angeles runs premium in both directions. For website and API traffic, the return path is what users actually feel, which is why the Asia nodes are positioned as the general-purpose choice.

## Every GoMami plan currently listed: 28 VPS plans across six product lines

GoMami's store pages do not publish prices, so the monthly list prices below are the figures reported consistently across independent sources between June and October 2026. Confirm the actual number in your cart before paying, especially on Peak X5, where the homepage and third-party listings disagree.

Two dedicated servers sit outside the VPS count and are listed separately at the end of this section.

### Hong Kong: HKG Turin (AMD EPYC 9575F, up to 5.0 GHz)

| Plan | vCPU / RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| HKG.Turin.Mini | 2 / 4 GB / 100 GB | 1 TB / 2 Gbps | $69 | [ Order](https://gomami.io/aff.php?aff=415&pid=14) |
| HKG.Turin.Air | 4 / 8 GB / 140 GB | 2 TB / 2 Gbps | $129 | [ Order](https://gomami.io/aff.php?aff=415&pid=15) |
| HKG.Turin.Pro | 6 / 16 GB / 180 GB | 5 TB / 5 Gbps | $299 | [ Order](https://gomami.io/aff.php?aff=415&pid=16) |
| HKG.Turin.Ultra | 12 / 32 GB / 220 GB | 10 TB / 5 Gbps | $599 | [ Order](https://gomami.io/aff.php?aff=415&pid=22) |

Pro and Ultra are marked Windows-ready; Mini and Air are Linux-only. This is the line to pick for MySQL, PostgreSQL, Redis or anything else where a single thread carries most of the work. It is also the line with the most generous storage per dollar.

### Hong Kong: HKG Peak X5 (AMD Ryzen 9 9950X, up to 5.7 GHz)

| Plan | vCPU / RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| HKG.Peak.X5.Mini | 2 / 4 GB / 40 GB | 1 TB / 2 Gbps | $59 homepage, $69 third-party | [ Order](https://bit.ly/Gomami) |
| HKG.Peak.X5.Air | 4 / 8 GB / 60 GB | 2 TB / 2 Gbps | $99 | [ Order](https://bit.ly/Gomami) |
| HKG.Peak.X5.Pro | 6 / 16 GB / 80 GB | 5 TB / 5 Gbps | $199 | [ Order](https://bit.ly/Gomami) |

The Mini price is genuinely inconsistent: GoMami's own homepage shows $59, third-party listings show $69. Same core count as Turin Mini but 40 GB of storage instead of Turin Mini's 100 GB. It is the pick for game servers and other frequency-sensitive workloads, and the weakest pick if disk space matters.

### Hong Kong: HKG Pulse (AMD EPYC 7763, up to 3.5 GHz)

| Plan | vCPU / RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| HKG.Pulse.Nano | 2 / 2 GB / 40 GB | 500 GB / 1 Gbps | $49 | [ Order](https://gomami.io/aff.php?aff=415&pid=26) |
| HKG.Pulse.Mini | 2 / 4 GB / 60 GB | 1 TB / 1 Gbps | $59 | [ Order](https://gomami.io/aff.php?aff=415&pid=4) |
| HKG.Pulse.Air | 4 / 8 GB / 80 GB | 2 TB / 1 Gbps | $119 | [ Order](https://gomami.io/aff.php?aff=415&pid=5) |
| HKG.Pulse.Pro | 8 / 16 GB / 100 GB | 5 TB / 3 Gbps | $269 | [ Order](https://gomami.io/aff.php?aff=415&pid=6) |
| HKG.Pulse.Ultra | 12 / 32 GB / 300 GB | 10 TB / 3 Gbps | $499 | [ Order](https://gomami.io/aff.php?aff=415&pid=25) |

Pro and Ultra are Windows-ready. One caveat: the store page lists Pulse Ultra at 12 vCPU on a 3 Gbps port, while another GoMami page shows 16 vCPU and 5 Gbps. If that specification matters to your workload, confirm it at checkout.

### Japan: JPN Pulse (AMD EPYC 7773X / 7K83)

| Plan | vCPU / RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| JPN.Pulse.Nano | 2 / 2 GB / 40 GB | 500 GB / 1 Gbps | $29 | [ Order](https://gomami.io/aff.php?aff=415&pid=13) |
| JPN.Pulse.Mini | 2 / 4 GB / 60 GB | 1 TB / 1.5 Gbps | $49 | [ Order](https://gomami.io/aff.php?aff=415&pid=10) |
| JPN.Pulse.Air | 4 / 8 GB / 80 GB | 2 TB / 1 Gbps | $89 | [ Order](https://gomami.io/aff.php?aff=415&pid=11) |
| JPN.Pulse.Pro | 8 / 16 GB / 100 GB | 5 TB / 3 Gbps | $169 | [ Order](https://gomami.io/aff.php?aff=415&pid=12) |
| JPN.Pulse.Ultra | 12 / 32 GB / 300 GB | 10 TB / 3 Gbps | $338 | [ Order](https://gomami.io/aff.php?aff=415&pid=24) |

### Singapore: SIN Pulse (AMD EPYC 7763)

| Plan | vCPU / RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| SIN.Pulse.Nano | 2 / 2 GB / 40 GB | 500 GB / 1 Gbps | $29 | [ Order](https://gomami.io/aff.php?aff=415&pid=21) |
| SIN.Pulse.Mini | 2 / 4 GB / 60 GB | 1 TB / 1 Gbps | $49 | [ Order](https://gomami.io/aff.php?aff=415&pid=17) |
| SIN.Pulse.Air | 4 / 8 GB / 80 GB | 2 TB / 1 Gbps | $89 | [ Order](https://gomami.io/aff.php?aff=415&pid=18) |
| SIN.Pulse.Pro | 8 / 16 GB / 100 GB | 5 TB / 3 Gbps | $169 | [ Order](https://gomami.io/aff.php?aff=415&pid=19) |
| SIN.Pulse.Ultra | 12 / 32 GB / 300 GB | 10 TB / 3 Gbps | $338 | [ Order](https://gomami.io/aff.php?aff=415&pid=23) |

Japan and Singapore are priced identically tier for tier, which makes the choice a geography question rather than a budget one. Both put Pro at $169 with Windows-ready status, the cheapest Windows option anywhere in the lineup.

### Los Angeles: LAX Pulse (AMD EPYC 7K62, dual-direction premium routing)

| Plan | vCPU / RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| LAX.Pulse.Nano | 2 / 2 GB / 40 GB | 1 TB / 1 Gbps | $29 | [ Order](https://gomami.io/aff.php?aff=415&pid=27) |
| LAX.Pulse.Mini | 2 / 4 GB / 60 GB | 2 TB / 1 Gbps | $59 | [ Order](https://gomami.io/aff.php?aff=415&pid=28) |
| LAX.Pulse.Air | 4 / 8 GB / 80 GB | 4 TB / 2 Gbps | $129 | [ Order](https://gomami.io/aff.php?aff=415&pid=29) |
| LAX.Pulse.Pro | 6 / 16 GB / 100 GB | 8 TB / 3 Gbps | $259 | [ Order](https://gomami.io/aff.php?aff=415&pid=30) |
| LAX.Pulse.Ultra | 12 / 32 GB / 300 GB | 15 TB / 5 Gbps | $599 | [ Order](https://gomami.io/aff.php?aff=415&pid=31) |
| LAX.Pulse.Titan | 12 / 32 GB / 600 GB | 30 TB / 10 Gbps | $999 | [ Order](https://gomami.io/aff.php?aff=415&pid=32) |

LAX is the newest line, and oddly it appears on the store but not on the homepage or in the official purchase guide, both of which still list only Hong Kong, Japan and Singapore. Traffic allowances are roughly double the Asian nodes at the same price, and none of the LAX plans carry the Windows-ready tag.

### Hong Kong: HKG Forge (dedicated servers, EPYC 7663, 56C/112T)

| Plan | RAM / NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- |
| HKG.Forge.Mini | 128 GB / 960 GB | 10 TB / 2 Gbps | Not shown on store page | [ Order](https://bit.ly/Gomami) |
| HKG.Forge.Air | 256 GB / 4 TB | 20 TB / 2 Gbps | Not shown on store page | [ Order](https://bit.ly/Gomami) |

These are whole machines on a TYAN B8033 board, not VPS instances. Third-party reports put Mini at either $399 or $599 and Air at either $699 or $899, both plus a $68 setup fee. The numbers conflict, so treat them as unconfirmed and check the order page. Traffic overage here is billed at $0.06/GB rather than throttled, and extra IPs cost $10 each up to four per server.

## Three things the spec sheet doesn't tell you

The 600 Gbps DDoS figure is an optional add-on rather than a default. Windows exists only on Pro and Ultra tiers. And traffic overage throttles you instead of billing you, with one exception.

**DDoS protection.** The homepage says "up to 600 Gbps mitigation capacity," which reads as though every plan ships with it. The documentation says something narrower. Best-effort protection is included by default on all instances, and 600 Gbps advanced scrubbing is a paid upgrade. Under the default tier, if an attack affects other customers, the IP gets blackholed for 30 to 60 minutes and released automatically with no manual override. If your service is a visible target, budget for the upgrade rather than assuming the marketing number covers a $29 Nano.

**Windows.** Only HKG Turin Pro and Ultra, HKG Pulse Pro and Ultra, JPN Pulse Pro and Ultra, and SIN Pulse Pro and Ultra are flagged Windows-ready on the store. Everything below that runs Linux, and the supported templates are the ordinary set: Ubuntu 22.04 and 24.04, Debian 11 and 12, CentOS Stream 9, AlmaLinux 8 and 9. Anything else goes through custom ISO mounting.

**Traffic overage, and what doesn't count.** The documentation says bandwidth may be throttled after the monthly quota, with specifics depending on the plan, and the quota resets each billing cycle. Third-party reviews consistently report throttling to roughly 20 KB/s until reset. The server stays up, it simply stops being useful. You can buy your way out instead: 100 GB for $6, 1 TB for $60, 5 TB for $300, up to 20 TB for $1,200, applied instantly from the dashboard. The exception is Forge, which bills $0.06/GB rather than throttling. Separately, and this is easy to miss, only outbound traffic is billed. Inbound traffic is free.

## The 24-hour refund is narrower than the headline suggests

It is a real full refund, but it applies to first purchases only, is limited to one per user, and must be requested within 24 hours of purchase. Renewal orders don't qualify. Neither do accounts that burned existing credit, nor an IP blackholed by a DDoS attack.

The part people skip: once a refund is approved, the server and its data are deleted immediately and permanently. Back up before you file. Refund timing depends on how you paid. Alipay lands in 1 to 3 business days, cards take 5 to 10, crypto 1 to 3.

Against Cloudzy's 14-day money-back guarantee on every plan, 24 hours is a narrow window. It is enough time to run a latency check against your own users and a disk benchmark. It is not enough time to discover that performance degrades on the third evening. Plan the trial around what you can actually measure in a day.

Promo codes go in at the cart step, not when you select a plan. Third-party sources mention two consistently: `GOMAMI365` for annual billing, roughly 20% off, though sources disagree on whether it covers the whole store or only Turin; and `Hi,LAX` for 20% off the LAX Pulse line, which an October 2026 write-up still showed bringing Nano down to about $23.20/month. Whether either applies today is a cart question.

👉 [Compare monthly and annual pricing on the GoMami order page](https://bit.ly/Gomami)

## Who shouldn't rent from GoMami

Anyone whose audience isn't in China, anyone who needs a sub-$20 box, and anyone who needs Windows on a cheap plan. Those three groups should look elsewhere, and no amount of clever framing changes it.

A personal blog, a Telegram bot, a staging environment, a WireGuard endpoint for yourself: none of that needs premium return routing, and $2.50 to $9 a month handles it. Paying $49 for a 2 GB Nano to run a cron job is money set on fire.

The same logic applies if all your users are in North America or Europe. LAX Pulse's dual-direction CN2, 9929 and CMIN2 path is legitimate engineering, but a reader in Frankfurt gains nothing from it.

And if Windows is a hard requirement on a tight budget, be aware that the cheapest Windows-ready plan here is JPN Pulse Pro or SIN Pulse Pro at $169/month, with HKG Pulse Pro at $269 and HKG Turin Pro at $299 above them. Cloudzy, for comparison, lists Windows Server 2022 and 2025 among its OS options on a plan grid that starts at $2.48/month. Different product, different routing, but the gap is worth knowing before you commit.

## How ordering works, and where people get stuck

You log in, pick a location and product line from the sidebar, hit Order Now on a plan, choose the billing cycle on the Configure page, continue to the cart, enter any promo code there, then check out. Payment options are account credit, credit card, Stripe Alipay and crypto.

Deployment is automatic and typically completes in 1 to 5 minutes, with the IP and root credentials arriving by email. The control panel covers the things you'd actually use: real-time CPU, memory and network graphs, OS reinstalls, restarts, VNC, rescue mode and password resets.

Three places people trip up. The promo code field lives on the cart page, so closing the tab after choosing a plan costs you the discount. Billing cycle selection happens one screen earlier than most people expect, so switching to annual after adding to cart means starting over. And service is suspended on the due date with no grace period, then terminated after five days overdue, so if you're testing month to month, set a reminder instead of trusting a warning email.

👉 [Start with the HKG Pulse Mini plan at $59/month](https://gomami.io/aff.php?aff=415&pid=4)

## FAQ

**Is there a free trial?** The site doesn't list one. The closest equivalent is the 24-hour refund window on a first purchase, which works as a one-day test as long as you file the request through the billing ticket system before the window closes.

**What happens when I hit the traffic limit?** The server is throttled rather than suspended or billed, and the quota resets at the start of the next cycle. You can also buy a traffic pack from the dashboard and have it applied immediately.

**Does inbound traffic count against the quota?** No. Only outbound traffic is billed. If you're serving large uploads or running a proxy with symmetric flow, that matters more than the headline allowance suggests.

**Can I install Windows?** Only on Pro and Ultra plans in the Hong Kong Turin, Hong Kong Pulse, Japan Pulse and Singapore Pulse lines. LAX plans aren't marked Windows-ready, and lower tiers are Linux-only.

**Does it accept Alipay?** Yes, through Stripe Alipay, alongside cards and crypto. Account credit can be applied to an order at checkout.

**What happens if my IP gets attacked?** Default protection is best-effort and automatic. If an attack affects other customers, the IP is blackholed for 30 to 60 minutes and released on its own, with no manual intervention available. The 600 Gbps scrubbing tier is a separate paid option.

**Why isn't LAX on the homepage?** The store lists it, the homepage and official purchase guide don't. Treat it as a newer line whose documentation hasn't caught up, and check the store directly rather than relying on the site navigation.

## Which virtual server rent plan to actually pick

Barely need China routing: rent a $2.50 to $9 commodity box and ignore this entire article.

Need China-facing latency on a tight budget: JPN or SIN Pulse Nano at $29/month. Same triple-network return routing, 500 GB of traffic, lowest list-price entry to the platform. If the `Hi,LAX` code is live, LAX Pulse Nano at roughly $23.20/month beats it on price and gives you 1 TB instead of 500 GB, at the cost of a US location and no Windows option.

Running a normal website or small app for Chinese visitors: HKG Pulse Mini, $59/month for 2 vCPU, 4 GB RAM, 60 GB NVMe and 1 TB. It's the plan most people land on, and annual billing with a working code brings it toward the $47 to $50 range.

Bottlenecked on single-thread speed, as with a database or game server: HKG Turin Mini at $69/month with 100 GB of NVMe, or Peak X5 Mini if you want the 5.7 GHz clock and can live with 40 GB of disk.

Serving both Chinese and North American users, or pushing real bandwidth: LAX Pulse, where Nano starts at $29 with 1 TB and Titan reaches 30 TB on a 10 Gbps port for $999.

Before paying, do two things. First, run a ping and a traceroute from your own connection to the target node at the hour your users are actually online, since GoMami's own documentation recommends testing latency and routing per node before purchase. Second, confirm the cart total after any promo code, because the list prices above come from consistent third-party reporting rather than a price field on the store page.

👉 [Check current GoMami plans and pricing before you order](https://bit.ly/Gomami)
