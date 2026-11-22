# MT5 VPS: What $15/Month Built-In Hosting Gets You, How Much RAM Each Terminal Eats, and Where a €5 Windows VPS Fits (Full Plan Table)

MT5 VPS comes in two shapes, and they are priced on different scales. MetaQuotes sells hosting from inside the terminal at $15 a month, dropping to $10 a month on a 12-month prepay, with a 24-hour free trial. A third-party Windows VPS such as AvaHost starts at €5.00 a month on monthly EUR billing, and you install MetaTrader 5 yourself over Remote Desktop.

Which one you want comes down to how many terminals you plan to keep alive. One account with one EA is hard to beat at $15 with zero setup. Three accounts, a Strategy Tester that runs overnight, or a Python process feeding orders is cheaper and more flexible on a rented Windows box.

> **Quick pick:** one account, one EA, no interest in server administration, take the built-in MetaTrader VPS at $15/month. Several accounts, backtests, or Python on the same machine, take AvaHost's Windows VPS from €5.00/month with RDP access and a 99.9% uptime commitment on power and network.
> 👉 [See AvaHost's current VPS plans and pricing](https://my.ava.hosting/aff.php?aff=15562)

## AvaHost's VPS range: the tiers and who each one fits

AvaHost runs six VPS tiers between €5.00 and €40.00 a month, all on KVM virtualisation with isolated vCPU and RAM allocations, NVMe storage and a dedicated IPv4 address per instance. The published endpoints of the range are specified; the four tiers in between step up vCPU, RAM and NVMe proportionally, and the live plan selector on the order page shows each configuration before checkout.

| Plan | vCPU / RAM / NVMe | MT5 terminals | Price (EUR, monthly) | Order |
| --- | --- | --- | --- | --- |
| VPS One | entry tier, exact figures in the plan selector | 1 terminal running 1–2 EAs (vendor's description) | €5.00/mo | [Start on VPS One](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Two to VPS Five | each step adds vCPU, RAM and NVMe proportionally | scales with RAM at roughly 1 GB per terminal (estimate) | between €5.00 and €40.00 | [See the mid tiers](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Ultra | 8 vCPU / 16 GB RAM / 160 GB NVMe | about 14 terminals by the 1 GB rule (estimate) | €40.00/mo | [Compare VPS Ultra](https://my.ava.hosting/aff.php?aff=15562) |

Terminal counts for the upper tiers are my arithmetic, not AvaHost's claim: the vendor only states that the entry plan suits a single MetaTrader instance with one or two EAs on a limited symbol set, and that each step up the range raises vCPU, RAM and NVMe together.

AvaHost has been a hosting provider since 2002. The VPS line ships without a control panel by default, which for a trading server is the right default since MetaTrader goes on over RDP and needs nothing else. Plesk, cPanel, ispmanager and DirectAdmin are paid extras at the order stage. Payment runs through card (Visa, Mastercard), PayPal, bank transfer, WebMoney and around twenty cryptocurrencies, with all prices denominated in EUR on a monthly cycle. DDoS protection is included on every plan, and support runs 24/7 by ticket and live chat.

## Check the latency before you commit to a long prepay

AvaHost's uptime FAQ names one datacenter: Chișinău. Most retail MT5 brokers keep their trade servers in Equinix campuses in London (LD4 or LD5), New York (NY4) or Frankfurt, so a VPS in Moldova is not in the same building as your broker and the sub-millisecond same-city advantage that hosting sellers advertise does not apply here. What you get instead is a fixed, wired, always-on connection from a datacenter in place of your home ISP, which is the part that actually matters for an EA running at 3am.

Whether the distance is acceptable is measurable in ten seconds. Open the MT5 login dialog, look at the ping shown next to your broker's server name, and judge from there. A swing or trend system will not notice the difference between 5 ms and 40 ms in its fills. A scalper firing on every tick will.

AvaHost bills monthly, so the cost of answering that question is one month rather than a year. That is a real advantage over any prepay discount you might be offered elsewhere.
👉 [Take VPS One for a month and ping your broker](https://my.ava.hosting/aff.php?aff=15562)

## Built-in MetaTrader VPS vs a rented Windows server

MetaQuotes' version is three clicks: hit the VPS icon in the platform, pick a service plan, transfer your environment to the cloud. Expert Advisors, custom indicators and signal subscriptions move with it, and MetaQuotes states you will not spend EA and program activations when moving to its cloud. Broker-side the path is the same, either the "Open MQL5 Virtual Hosting" icon in the top menu or a right-click on your account in the Navigator panel and "Register a Virtual Server".

The rented Windows route asks for more. You install MetaQuotes' build or your broker's branded installer, copy EA and indicator files into the MQL5 data folder, and enable Algo Trading. Two operational details trip up first-timers. Close the Remote Desktop window and everything keeps running; choose Sign out from the Start menu and the Windows session ends, which closes the terminal and stops your EA. Add each terminal to the Windows startup folder so it comes back logged in after a reboot or a host failover.

Resources differ too. MetaQuotes allocates up to 3 GB of RAM and 16 GB of disk per virtual platform with several CPU cores, which it describes as enough for multiple EAs and indicators running together. That is a per-platform ceiling; AvaHost's Ultra tier gives you 16 GB of RAM and 8 vCPU, enough for a dozen terminals or a serious optimisation run, and you allocate it yourself.

Support scope is the last difference worth knowing. AvaHost commits to 99.9% uptime on power and network at its datacenter and explicitly excludes downtime caused by your applications, software or broker connectivity, which is an honest boundary. MetaQuotes advertises 99.99% uptime and 0–5 ms latency with 96% of broker servers reachable in under 10 ms and 84% under 3 ms. Those are vendor figures from the company selling the service, not independent measurements.

## How much does one MT5 terminal actually need?

Budget about 1 GB of RAM per terminal, and more if you run tick-level strategies or hold long M1 histories. MT5 is a 64-bit application and keeps more in memory than MT4 did, so the old half-a-gigabyte-per-terminal arithmetic no longer holds.

Cores are a different story. Live trading barely touches the CPU. The Strategy Tester does, and it hands one local testing agent to each vCPU, so an 8-vCPU plan finishes an optimisation roughly eight times faster than a single core. A single-pass backtest stays single-threaded, which is why paying for cores only makes sense if you optimise often. The tester also consumes every core it is given, so a live scalper sharing that box will feel it. Run optimisations outside your EA's trading hours, or keep a cheap second server for research.

## The 12-month cost, worked out

MetaQuotes' own price table is worth reading as a ladder rather than a number:

| Term | Total (USD) | Per month (USD) | Discount |
| --- | --- | --- | --- |
| 1 month | 15 | 15 | — |
| 3 months | 39 | 13 | 13% |
| 6 months | 65 | 10.83 | 27% |
| 12 months | 120 | 10 | 33% |

A full year on the monthly plan costs $180. The annual plan costs $120, so the saving is $60 per virtual platform. The six-month plan deserves attention: at $10.83 a month it is only $0.83 more per month than the annual rate while cutting your commitment in half. If you are still unsure whether the built-in platform handles your EA's resource appetite, that is the better trade.

Two conditions are attached to the trial. The 24-hour free trial switches you to a paid plan automatically when it ends, so cancelling is something you have to do rather than something that happens to you. The full-refund window is also the first 24 hours.

AvaHost on the same basis: VPS One at €5.00 a month is €60 for a year, VPS Ultra at €40.00 is €480. No prepay discount is published, so the annual figure is simply twelve monthly payments. Per terminal the arithmetic favours the rented box once you pass a couple of accounts, since each MetaQuotes subscription covers one virtual platform. At twelve terminals on VPS Ultra you are near €3.33 per terminal per month against $15 each on the built-in plan, before you count the Strategy Tester cores.
👉 [Compare the AvaHost tiers against your terminal count](https://my.ava.hosting/aff.php?aff=15562)

## Is a "free" MT5 VPS actually free?

IG offers the MetaTrader VPS free to clients who maintain a $1,000 account balance; the product page adds a second condition, at least one trade a month, and quotes the service's normal value at $15 a month. The help page states only the balance requirement, so treat the stricter version as the one that applies.

This is a rebate on capital you keep at one broker, not a free product. If you already fund an account at that level and trade monthly, it is the cheapest MT5 hosting available anywhere, and nothing in this article beats it. If you would have to move $1,000 across to qualify, you are paying for the hosting with money parked at a single venue, and a €5 VPS is the cheaper arrangement.

## Picking a tier from what you actually run

One account and one EA. Either the built-in VPS at $15 monthly, because setup takes minutes and you can cancel inside 24 hours if the execution disappoints, or AvaHost's VPS One at €5 if you want full Windows control and the ability to install a second terminal later without buying anything new.

Three to six accounts on the same broker, some copy trading, light optimisation. Look for 4 GB of RAM or more and 4 vCPU. On AvaHost that is one of the middle tiers; on the built-in service it means one subscription per platform.

Overnight genetic optimisation. Cores first, memory second. The 8 vCPU tier is the one where a run that takes a night on a laptop finishes over lunch.

Python plus live terminals. Third-party hosting only. The `MetaTrader5` Python package connects to a Windows terminal running on the same machine, so Python has to be installed on the VPS beside the terminal, not on your laptop. Libraries such as pandas and scikit-learn install as usual; size the RAM for the datasets you load. No built-in MetaTrader hosting gives you that.

## Three things to confirm before you pay

1. Where your broker's trade server sits, and what ping you get to it. The MT5 login dialog shows the server name and the latency; nothing else settles the location question as quickly.
2. Whether the Windows Server licence is included in the price on the tier you pick, and which Windows version you get. AvaHost sells a Windows VPS line, but the plan pages do not spell out the licensing terms in the text reviewed here, so ask support before ordering.
3. The exact vCPU, RAM and NVMe figures for the tier in the plan selector. The published range gives you €5.00 at the bottom and 8 vCPU / 16 GB / 160 GB at €40.00 at the top; the four tiers between them are defined by the selector, and that is where you should read your configuration rather than from a summary.

If your setup is one EA on one account, the built-in MetaTrader VPS is the least work for $15, and the annual plan brings it to $10 a month once you are sure. If you run multiple terminals, optimise regularly, or want Python next to the terminal, a monthly-billed Windows VPS keeps your options open and costs less per account. AvaHost's six tiers start at €5.00 and top out at 8 vCPU and 16 GB, with monthly EUR billing, so a wrong guess costs one month.
👉 [Pick your AvaHost tier and check the live configuration](https://my.ava.hosting/aff.php?aff=15562)
