# Speaker Notes — Are Taxi Rides Just a Game?

**Math 30.04 Final Project · Flash Talk · ~13 minutes**

## Speaker assignments

| Person | Slides | Time |
|---|---|---|
| **Julia** (opens) | 1, 2, 3 | ~2:45 |
| **Mithun** (model setup) | 4, 5 | ~3:30 |
| **Charles** (analysis & equilibria) | 6, 7, 8 | ~4:15 |
| **Lourdes** (limitations & wrap) | 9, 10, 11 | ~3:45 |

Notes are embedded inside the PPTX (look in the "Notes" pane below each slide in PowerPoint or Keynote). The full text is duplicated below in case you want to edit / share / print.

---

## Slide 1 — Title (Julia, ~30 sec)

Hi everyone, we're Group [X]. I'm Julia, and this is Charles, Lourdes, and Mithun. Our project asks a question that anyone who's ever taken a cab has felt the tension of: are taxi rides just a game? We're looking at the strategic interaction between drivers and passengers around tipping in New York City, using evolutionary game theory and real ride data. I'll get us started with the motivation.

---

## Slide 2 — Overview & Motivation (Julia, ~75 sec)

Every time you get in a taxi, there's a small game being played. The driver wants to maximize earnings — they can do that two ways: drive efficiently and earn a tip, or take a longer route and run up the meter. The passenger wants the cheapest, fastest ride, but they also feel social pressure to tip for good service.

Why does this matter? Millions of these interactions happen every day in NYC. The outcome isn't just about a few dollars — it affects routing efficiency, congestion, and driver wages. Tipping is completely voluntary, so the real question is: does the cooperative norm survive, or does it collapse under self-interest?

That's exactly what evolutionary game theory is built for — analyzing whether a strategy survives competition. We restricted our analysis to Manhattan, weekday rush hour, credit-card rides — the densest, most competitive setting. I'll hand it over to talk through what's been done before.

---

## Slide 3 — Literature Review (Julia, ~60 sec)

Two papers framed our approach. Norris et al. 2023 applied static game theory to restaurant tipping and found that observable service characteristics — speed, friendliness, group size — drive tipping decisions. But they didn't look at how the equilibrium evolves over time.

Kang 2021 argued tipping is sustained by social norms even when the underlying economic incentives shift — people keep tipping out of habit and pressure, not pure reciprocity.

Our contribution is the dynamic piece. Nobody has done an evolutionary treatment of taxi tipping with real ride data. We set up replicator dynamics, calibrate the parameters from NYC TLC trip records, and test whether the cooperative equilibrium actually holds. Mithun is going to walk through the model.

**[HAND OFF TO MITHUN]**

---

## Slide 4 — Game Design & Payoff Tables (Mithun, ~90 sec)

This is a two-population asymmetric game. On the driver side: Tip-Max means drive efficiently and earn the tip τ. Meter-Max means take the long way and earn extra meter fare m. On the passenger side: Tip or No-Tip.

Look at the driver payoff table. A meter-maxing driver gets m+τ when paired with a tipper, m when paired with a non-tipper. A Tip-Max driver gets τ or 0. Row by row, meter-maxing pays m MORE than Tip-Max no matter what the passenger does. Hold onto that observation — it drives the whole story.

The customer side is more interesting. A tipping customer paired with a Tip-Max driver gets reciprocity s₀, plus a social signaling reward α·ln(n) where n is the passenger count, minus the tip τ. Paired with a meter-maxer, they get −k for wasted time minus τ. The key thing is that α and β — the social rewards and penalties for tipping — only matter in multi-passenger rides, because ln(1) = 0. In a solo cab ride, there's no audience and no signaling motive.

---

## Slide 5 — Model: Replicator Dynamics (Mithun, ~2 min — math-heavy, take your time)

Replicator dynamics is the standard tool from evolutionary game theory. The equations on the left say strategies with above-average fitness grow over time — the strategies that pay better get more players.

Driver fitness difference: Tip-Max minus Meter-Max equals τy minus (m + τy), which equals NEGATIVE m. This is a CONSTANT — it's negative as long as m is positive. That means Meter-Max strictly dominates Tip-Max no matter what the passengers are doing. The driver dynamics always push toward all meter-maxing. This is huge.

The passenger side is more nuanced. Their fitness difference is x times the social signaling term (s₀ + (α+β)·ln n), minus τ. This is linear in x — so there's a passenger threshold x* equal to τ divided by that signaling term. Above x*, passengers prefer to tip; below it, they don't.

On the right — why would anyone tip a stranger they'll never see again? This is indirect reciprocity. When other passengers are watching, tipping builds reputation; stiffing in front of others has a social cost. That's the α and β terms. In a solo ride, you're invisible — no signaling motive, just s₀.

Charles will walk through what the phase diagrams actually look like.

**[HAND OFF TO CHARLES]**

---

## Slide 6 — Phase Diagram I: Cooperative (Charles, ~90 sec)

This is the cooperative scenario — small m, strong social signaling. The arrows in the background are the velocity field of the replicator dynamics. The blue curves are sample trajectories starting from different initial conditions.

Notice x — the share of Tip-Max drivers — still drifts toward zero, because m is still positive. But because the passenger threshold x* is LESS than 1, passengers keep tipping even as drivers shift toward meter-max. The system converges to (0, 1) — all meter-maxing drivers, all tipping passengers.

This is the world where tipping culture survives — not because it's reciprocal, but because the social cost of stiffing in front of other passengers outweighs the dollars saved. Tipping persists as a pure social norm, decoupled from actual service quality. Now let's look at what our actual data says — next slide.

---

## Slide 7 — Phase Diagram II: Norm Collapse (Charles, ~90 sec)

Here's the same kind of phase diagram, but the parameters are calibrated to our real NYC data: τ around $3.50 and m around $4.40. So m is BIGGER than τ. Look what changes. The driver velocity is much larger and more negative — every trajectory rapidly pushes x toward zero. Once x is low enough, passengers face Δf less than zero and stop tipping. Every starting point converges to (0, 0) — full norm collapse.

Now here's the puzzle. The model predicts (0,0). But in our data, the tip rate is around 27 percent — far from zero. Why? Because real-world tipping is propped up by external scaffolding the basic model doesn't capture: the default 20/25/30 percent buttons on the in-cab payment screen, driver ratings on app platforms, social pressure with strangers in the cab. Those mechanisms keep the system off the (0,0) attractor.

---

## Slide 8 — Nash vs ESS Summary (Charles, ~75 sec)

Quick summary of the equilibrium analysis. (0, 0) — all meter-max, no tipping — is both a Nash equilibrium AND an ESS. Stable, robust. (1, 1) — all Tip-Max, all tippers — looks cooperative, but it fails the ESS test because Δf for drivers equals negative m. Any meter-maxing mutant invades immediately. (0, 1) — all meter-max but all tipping — can be Nash if signaling is strong enough, but it's fragile. And the interior mixed equilibrium is an unstable saddle point.

The punchline at the bottom: the cooperative norm is NOT an ESS in the baseline model. The only robust attractor is full collapse. Anything we observe in reality that looks like tipping cooperation is being propped up by mechanisms outside this model.

Lourdes will take us through what our analysis couldn't capture and what comes next.

**[HAND OFF TO LOURDES]**

---

## Slide 9 — Limitations (Lourdes, ~75 sec — don't read every card, hit the * ones)

Six things we want to be transparent about.

**\*** First, binary strategies — real drivers and passengers don't choose tip-or-not in a yes/no way, they choose how much.

Second, replicator dynamics assumes well-mixed populations — random pairings. In reality cabs and passengers self-select by neighborhood, app, time of day.

**\*** Third — this is the big one — the TLC data only records credit-card tips. Cash tips are invisible. So our findings strictly apply to credit-card-paying passengers, not all riders.

**\*** Fourth, the in-cab payment screens have default 20-25-30 percent buttons. Prior research shows those defaults inflate observed tip rates dramatically — our τ is conflated with that mechanism. This is probably the single biggest reason real-world tip rates stay high.

Fifth, we estimate m from data using a fast-quartile fare baseline as the comparison — we haven't done sensitivity analysis on that choice yet.

Sixth, app platforms like Uber and Lyft use rating systems that fundamentally change the strategic landscape — we don't capture those.

---

## Slide 10 — Future Work + Empirical Finding (Lourdes, ~90 sec — slow down, this is the empirical headline)

The chart on the left is our headline empirical finding. 13 quarters from early 2023 through early 2026 — about 6.5 million Manhattan rush-hour credit-card rides. Tip rates were stable around 26.5 percent through 2023 and 2024.

Then on January 5, 2025, NYC introduced the new CBD congestion fee — a flat $1.50 surcharge for entering the central business district. And you can see the tip rate jumps 1.28 percentage points immediately, and stays elevated for the next 12 months.

Why does this happen? The flat fee replaces what used to be discretionary meter-maxing. Our m parameter — the meter-max premium — dropped from $5.04 in November 2024 to $3.46 in February 2025. The driver can't run up the fare the same way, and the equilibrium shifts toward more cooperative outcomes. It's basically a natural experiment that lines up with what the model predicts.

For future work — stochastic dynamics with finite populations, extending to rideshare platforms where ratings change the payoff structure, and applying this framework to other gig-economy settings where informal norms substitute for contracts.

---

## Slide 11 — Conclusion (Lourdes, ~60 sec)

To wrap up — four take-aways.

First: tipping is more fragile than it looks. The cooperative equilibrium isn't an ESS once you take m seriously.

Second: in our data, m exceeds τ in EVERY quarter, so the basic model predicts (0, 0) — full norm collapse.

Third: what we actually observe in the world is held up by external scaffolding — default prompts, ratings, social pressure — not by pure reciprocity.

Fourth: there's a policy lever here. Nudging the system above x* through default prompts and transparency genuinely shifts the equilibrium — we saw that in the congestion-fee data. Evolutionary game theory tells us when informal norms can hold the line and when regulation is needed.

Thanks for listening. Happy to take questions.

---

## Q&A prep — likely questions

**"Why didn't you use Dynamo?"** — We needed to fit parameters from 6.5M trip records, so a GUI tool wasn't practical. We implemented replicator dynamics directly in Python (scipy.integrate.odeint) and validated against the analytical equilibrium.

**"How did you estimate m?"** — Within each quarter, we took the fastest-pace quartile of trips as the "efficient" baseline. For each trip, the excess fare relative to its distance bin is the meter-max premium. We took the mean of the positive-excess subset as m.

**"What about cash tippers?"** — TLC doesn't record cash tips, so we restricted to credit-card payments. That's a self-acknowledged limitation — our findings apply to CC-paying customers, who make up ~85% of recent NYC Yellow Cab trips.

**"Did you control for tourism / seasonality?"** — We sampled the middle month of each quarter (Feb, May, Aug, Nov) to spread observations across the year. We also restricted to weekday rush hour, which is much less tourism-influenced than weekends.

**"What's the practical takeaway for policy?"** — The Jan 2025 congestion fee was effectively a policy intervention that compressed the meter-max premium and pushed the equilibrium toward more cooperative outcomes. The model suggests this kind of fare transparency may be more effective than relying on tipping norms alone.
