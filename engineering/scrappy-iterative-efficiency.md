---
title: Sometimes Efficiency Is Just Turning the Suitcase the Other Way
date: 2026-07-27
tags: [engineering-productivity, efficiency, systems-thinking]
---

# Sometimes Efficiency Is Just Turning the Suitcase the Other Way

## Summary
Carlos Arguelles, a ~30-year Engineering Productivity veteran (Amazon, Google, Microsoft), uses a stuck baggage carousel at Sea-Tac to argue that the most persistent inefficiencies at scale are the ones no single person feels enough pain from to own. He shows how a rough, back-of-napkin model can justify investigating a problem long before you have perfect data, and how the right first fix is often the cheapest possible experiment, not a redesign.

Source: [Carlos Arguelles, on Medium](https://carloarg02.medium.com/sometimes-efficiency-is-just-turning-the-suitcase-the-other-way-833e229e4479)

---

## Decisions & insights

### 1. Distributed pain has no owner
At large-company scale, small inefficiencies compound into developer fatigue, wasted infrastructure, slower delivery, and missed business opportunities — but they persist because the pain is spread across thousands of people, each only slightly inconvenienced. No individual or team feels enough of it to take ownership, quantify the aggregate cost, and push a fix through. The irony: fixing the problem often costs a fraction of what the persisting inefficiency is already wasting.

### 2. Three principles for spotting inefficient systems
Arguelles frames the piece around three claims: you don't need to be the domain expert to recognize an inefficient system, you don't need perfect data to decide a problem is worth investigating, and you don't need a perfect solution — be scrappy, iterative, and learn. What you do need is enough understanding to form a hypothesis, enough directional data to estimate whether the impact is meaningful, and enough curiosity to test a simple solution.

### 3. The observation: a carousel that looks busy but has low throughput
Waiting over 30 minutes for luggage at Sea-Tac after a Turkish Airlines flight from Istanbul, he noticed bags were sitting on the carousel in inconsistent orientations — some flat and space-hogging, some on edge and compact. A sensor near the entry point paused the feed whenever the carousel looked full, so poorly-oriented bags that had already circled several times unclaimed were blocking new bags from entering. Lots of activity, very little throughput.

### 4. Scrappy math to size the opportunity
Without real data, he ran a rough model: if bags on their thin edge use 30–60% less belt length than the two common flat orientations, properly-oriented bags would use about 55% of the space the carousel currently used — meaning the carousel could hold roughly 82% more bags before saturating. He's explicit that this is directional, not rigorous ("scrappy math"), but good enough to justify pursuing the idea further.

### 5. Translating carousel capacity into human cost
Applying the same rough logic to his own flight (~266 waiting passengers), he estimated the existing wait already cost about 133 passenger-hours, and that better bag orientation could plausibly cut the average wait from 30 minutes to somewhere near 16.5 minutes — conservatively rounded to a 10-minute savings per passenger, or about 44 passenger-hours saved on a single flight. The point isn't the precision of the number, it's that a napkin estimate is often enough to justify looking closer.

### 6. The fix is scrappy, not a hardware redesign
Rather than proposing an expensive multi-year mechanical redesign, his first suggested fix is a person standing at the entry point turning suitcases onto their thin edge. Swissport (Sea-Tac's baggage handler) lists baggage-handler jobs at $22/hr — adding less than a dime to the cost of a ticket to potentially save 44 passenger-hours. As a customer, he says he'd happily pay that dime to save ten minutes of waiting.

### 7. Validate before you commit
The essay closes by pushing "always be scrappy and iterative when validating an idea" — start with the cheapest experiment that can test the hypothesis (e.g. an A/B trial with and without a bag-turning handler across comparable flights) before deciding whether a permanent, more scalable fix (like a redesigned chute) is worth building. He flags that even a good-sounding idea can have an unintended consequence — e.g. thin-edge bags might be harder for passengers to grab — that only shows up once you actually test it.

---

## Key takeaways
1. If pain is distributed across enough people, no one owns fixing it — even when the aggregate cost dwarfs the fix.
2. A rough, directional estimate ("scrappy math") is enough to justify investigating further; it doesn't need to be rigorous.
3. Start with the cheapest experiment that can validate the hypothesis before investing in a permanent, scalable solution.

## References
- [Sometimes Efficiency Is Just Turning the Suitcase the Other Way (article)](https://carloarg02.medium.com/sometimes-efficiency-is-just-turning-the-suitcase-the-other-way-833e229e4479)
