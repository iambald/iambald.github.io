---
layout: post
title: Triplebyte Premium - Aligning Incentives
author: Jeff Chen
tags: recruiting,triplebyte,incentive,design,startups
---

[Triplebyte](https://triplebyte.com/) announced [Premium](https://triplebyte.com/try-premium) last week. For those who don't know, Triplebyte evaluates software engineers with an online quiz and technical interview. Engineers who pass the interview process are matched with companies and skip to on-site interviews.

Triplebyte Premium offers a couple new features. In addition, Premium changes Triplebyte's pricing structure from per-hire to yearly with tiers:

> Triplebyte's new annual subscription pricing is based on number of hires and saves you money as soon as you hire more than two people within a year.

I'll argue that this pricing structure fixes the fundamental incentive misalignment between external recruiters and hiring teams. First, let's dig into the problem:

## What's wrong with traditional pricing anyways?

External recruiters typically charge either a flat fee per hire or a percentage of the hire's first-year salary. In both models, a recruiter maximizes their income by **maximizing hires** (or maximizing total first-year salary across all hires, which amounts to the same thing). From a purely monetary perspective, **hiring quality makes no difference to recruiters**. Also, recruiters rarely operate on timescales longer than a few hires - their relationship with a company often ends well before the effects of their hires do. In contrast, a hiring manager cares about much more than headcount - she's rewarded by the long-term success of her team, so she needs to balance pure growth with team fit, short-term developer productivity (by bounding the number of interviews conducted), ..., and much more. Their incentives are fundamentally misalgned.

This misalignment can manifest in many ways: recruiters slipping hints to candidates to help them get through the interview process, or hiring managers frustrated when yet another hyped candidate fails to meet expectations, or constant disagreements about how big a candidate pipeline should be and how wide a net to cast. A recruiter involved in designing the candidate interview loop should always argue for lowering the bar and for interviewing as many candidates as possible.

Triplebyte historically didn't deviate from this model - they've charged a percentage of first-year salary since their founding in 2015. Even as they innovated in other parts of tech recruiting, their incentives remained misaligned with comapnies on the platform.

## How Triplebyte Premium helps

Triplebyte Premium ditches the industry-standard per-hire model for a tier-based annual pricing structure based on number of hires. So what is Triplebyte motivated to do for companies now?

- Triplebyte is rewarded for long-term success: companies won't renew contracts if their candidates or hires are noticably worse than par. This means that Triplebyte is strongly motivated to only surface truly strong candidates.
- They're much less likely to pressure companies to hire - the pressure should only manifest when a company is close to the edge of a pricing tier rather than for every single hire.
- By decoupling pricing from first-year-salary, Triplebyte no longer benefits from upselling candidates to companies. Instead, they can give honest evaluations.

## Towards even better incentive design

While Triplebyte Premium's model takes a big step towards aligning motivations between recruiters and hiring teams, I'd love to see them take a couple more steps:

- Triplebyte should turn off Triplebyte Classic (with its per-hire pricing model) completely. Introducing a premium tier may hurt candidates, since Triplebyte is now incentivized to prioritize its Premium customers.
- SaaS companies give credits when their services are down for more than an agreed percentage (todo). Triplebyte could introduce an SLA for recruiting - giving prorated credits to companies where a new hire is fired with cause within a year.
- Going a step further, Triplebyte could even compensate candidates that pass their interview but fail to get placed with Triplebyte.
- On the other end of the spectrum, Triplebyte could create positive reinforcement by collecting a (small) fee when Triplebyte hires hit tenure milestones or are promoted.
- I haven't yet seen details about Premium's pricing tiers. This is a delicate balance - too many tiers reduces to the old per-hire model, but too few tiers could cause a decline in Triplebyte's quality as they strive to be just "good enough" to retain companies.

All in all - I'm really excited to see Triplebyte continue to innovate. They've already gone a long way helping to match candidates from diverse backgrounds with top tech companies - and they're now working to fix the incentive misalignment between recruiting and hiring companies.

<br>

*(I've used Triplebyte both as a candidate and hiring manager - I work at [Ladder Life](https://www.ladderlife.com), which is an active Triplebyte customer.)*
