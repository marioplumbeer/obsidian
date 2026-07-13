---
title: 20 AI Agents Replaced a 10-Person Sales Team — Jason Lemkin's SaaStr Experiment
date: 2026-07-13
tags: [startups, sales, go-to-market, ai-agents, saastr]
---

# 20 AI Agents Replaced a 10-Person Sales Team — Jason Lemkin's SaaStr Experiment

## Summary

[Jason Lemkin](https://www.saastr.com/author/jasonlkn/), founder and CEO of [SaaStr](https://www.saastr.com/) (the largest B2B founder community, ~$90M+ invested in 200+ founders), replaced his ~10-person sales team with 1.2 humans and 20 AI agents — and the business performs about the same, just far more efficiently. This is a second sit-down with Lenny Rachitsky, a year and a half after their first, and it's a hands-on field report rather than theory: what agents SaaStr actually deployed, how long training took, where humans still win, and why "playbooks are broken even though the plays still work."

Source: [We replaced our sales team with 20 AI agents—here's what happened next | Jason Lemkin (SaaStr)](https://www.youtube.com/watch?v=I-R1bc1rlFs) — Lenny's Podcast

---

## Decisions & insights

### 1. The trigger: two paid, loyal reps quit on-site at SaaStr Annual
Going into SaaStr's 10,000-person annual event, two well-paid sales reps quit at the event itself — the latest in what Lemkin says was the third time this has happened across the eight sales teams he's built. He'd already seen one general-purpose agent (an internal "digital Jason" clone built on [Delphi](https://www.delphi.ai/), used for [saastr.ai](https://saastr.ai)) close a $70K sponsorship on its own, unprompted, with no sales training. That was the proof point: "We're done with hiring humans in sales. We're done. We are going to push the limits with agents."

### 2. Same output, radically fewer people
SaaStr went from 2-3 SDRs and up to 5 AEs (8-9 people) to 1.2 humans (one full-time AE, plus 20% of chief AI officer Amelia's time) and 20 AI agents — selling both event sponsorships (~$70-80K each) and tickets (low hundreds of dollars to $2K). Net revenue and productivity are unchanged: "It's not better. It's not worse. But it's so much more efficient, and it scales because software scales." The physical office now has ten desks labeled with agent names instead of people — Reply for Replit, Quali for Qualified, Arty for Artisan.

> "We're done with hiring humans in sales. We're done."

### 3. The plays still work — the playbooks don't
Every classic GTM motion (outbound, webinars, podcasts, events) still works, but growth has decelerated so much since 2021 that old-school execution no longer produces enough ROI. Meanwhile companies with high demand — [Vercel](https://vercel.com/), [Replit](https://replit.com/), [ElevenLabs](https://elevenlabs.io/) — are running the same plays differently: hyper-PLG-focused, picking which leads to even respond to. Historically only 3-5% of prospects were "in market" for a category in a given year; in many AI categories today it's over 50%, because adoption pressure is company-wide, not niche. That's the real driver of the current AI-tools boom — "it's not one law firm looking at [an AI tool]. It's everyone."

### 4. SDRs and inbound qualifiers are becoming extinct within a year
The classic email-cadence SDR and the human who qualifies inbound leads ("what do you do, how much will you pay") add no value AI can't already replicate, and Lemkin expects both roles ~90% displaced within 12 months. AEs are safer for now (70% of the role intact by end of next year, in his estimate) but he expects that to fall to 40-50% as agents get better at closing when there isn't much to negotiate. Field/door-knocking sales and true enterprise relationship-selling are the least exposed — leadership roles are safe because "we've yet to produce an autonomous CEO."

### 5. How to become part of the resilient 20%
Lemkin estimates roughly 20% of GTM people will successfully make the transition; the rest are "panicking" without having tried anything. His prescription: pick one painful problem (support, SDR, inbound qualification), pick one vendor, and personally do the ingestion, training, and QA yourself for 30 days — uploading your website/wiki/docs, correcting the agent's mistakes daily, iterating until it's solid. "It is not that hard, guys. It's just different." Anyone who does this once — even badly — becomes "hyper employable," because almost nobody at large companies has actually done it themselves (he describes a $10B+ public company's 20-person team that had never trained an agent hands-on).

### 6. Buy, don't build — unless you're Vercel
None of SaaStr's GTM agents were built in-house, despite Lemkin being a self-described top-1% [Replit](https://replit.com/) power user who's shipped a dozen apps himself (a valuation calculator used 800K times in 90 days; a pitch-deck reviewer that's reviewed ~3,000 decks). GTM tooling moves too fast to maintain internally unless, like Vercel, you have engineers who genuinely want to build it. The real evaluation criterion isn't the feature matrix — it's whether the vendor will actually show up and train the agent with you. Two vendors turned SaaStr down outright (one wanted $100K up front, one didn't want the PR risk if it failed publicly); [Artisan](https://www.artisan.co/) and [Qualified](https://www.qualified.com/) won by offering hands-on help with nothing guaranteed.

### 7. The actual agent lineup at SaaStr
- **General/support agent** — a Delphi-based digital clone ("digital Jason") that started as a novelty and organically took over 24/7 event support (refunds, venue questions, "who's speaking") after Intercom-based human support was taking two weeks to respond.
- **Outbound** — [Artisan](https://www.artisan.co/) (YC-backed AI BDR startup), trained on ~400K contacts to win back lapsed attendees; sent ~60,000 emails.
- **Inbound qualification** — [Qualified](https://www.qualified.com/) (founded by Salesforce's former CMO [Kraig Swensrud](https://www.qualified.com/about-us)), which closed a sponsorship at 11pm on a Saturday and qualifies/routes 24/7.
- **Reactivation** — [Salesforce Agentforce](https://www.salesforce.com/agentforce/), pointed specifically at leads human reps had already written off as not worth their commission; got a 70% response rate on that "worthless" list.

### 8. Making AI-written emails actually good
The fix for bad AI sales emails is almost always a bad vendor or bad training, not a bad model. The method: take your best salesperson's actual best email, upload it as the training example, and let the agent A/B-test variants from that baseline plus whatever CRM/visitor data it can pull for light personalization. Lemkin's blunt aside: most human SDR emails are worse than people assume — when [Adobe](https://www.adobe.com/) acquired his prior company (EchoSign), sales leader Sam Blonde (later CRO of [Brex](https://www.brex.com/)) told him the inherited reps' emails were "the worst emails I've ever read." AI trained on a genuinely good template beats a mediocre human by default. In hundreds of thousands of sends, SaaStr found disclosing "this is an AI" made no measurable difference to response rates.

### 9. Where humans still clearly beat AI
For a short list of the highest-value targets — SaaStr's whiteboard of the ~50 biggest possible sponsors, worth $500K+ for a two-year deal — there's no AI involved at all; three senior humans divide the list and work it personally, because the ROI per touch justifies fully bespoke effort. [Jen Abel](https://www.lennysnewsletter.com/p/master-founder-led-sales-jen-abel), co-founder of Jellyfish, makes this case for founder-led enterprise sales generally: she writes her own emails "artisanally" specifically because everyone else is now sending AI. But Lemkin's counter is that this only scales to a handful of elite reps and elite accounts — most companies can't attract "a team of Jens," and most volume, even at the high end, is better served letting AI fill the gaps a human simply won't work (he tells a story of trying to buy a $10K product himself and waiting three days for a rep who wouldn't answer two simple questions without a call).

### 10. Running 20 agents needs a full-time human orchestrator
Amelia, SaaStr's "chief AI officer," spends 10-15 hours a week reviewing agent outputs — a heavier load than expected, because "agents work all night and they work weekends and they work on Christmas." Segmenting which agents own which slice of the contact base (inbound vs. outbound vs. reactivation) is a real, unsolved problem once you're running more than a couple of agents; there's no "master agent that manages agents" yet. Lemkin's hiring advice: don't post a "GTM engineer" job externally — promote an internal person who has already taught themselves to build in tools like Replit, since the role barely exists as a hireable external category yet.

### 11. Forward-deployed engineers are the new differentiator
Borrowing the term from [Palantir](https://www.palantir.com/), the FDE's job is to guarantee the agent works *before* the customer pays — inverted from the old SE model, where a handful of engineers were shared thinly across a team of reps. Lemkin cites an AI vendor that closed a $3M deal where the FDE did the entire technical deployment and sales only handled procurement. Vendor selection should include a specific test: get the FDE on the phone before signing, and "if Lenny rocks and the other vendor won't help you, don't do it" — the best vendors today, he notes, are turning away business they don't think they can make successful.

### 12. What's permanently different vs. still unsettled
Support is permanently changed — 50-80% AI-handled across most vendors, full stop. Cadence-based SDR and inbound-qualifier roles are on the same trajectory within 12 months. Phone and SMS outreach remain genuinely unresolved: legal/regulatory limits on robocalling and automated SMS are real, and Lemkin expects startups to keep pushing those boundaries rather than most of the volume shifting there in the near term.

### 13. AI is producing more work, not less
Tools like [Momentum](https://momentum.io/) and [Attention](https://attentive.ai/) auto-log every rep interaction into the CRM in real time — a level of transparency that ended one rep's job within a day of rollout, because it revealed he'd done nothing in 30 days. Lemkin's broader point: AI doesn't reduce a good operator's workload, it raises the ceiling on how much output is expected — "I'm working the hardest I've ever worked... it's more work." His holiday-break prescription for finding your own opportunities is the "incognito mode test": visit your own product as a fresh, anonymous user, try support and sales end-to-end, and go fix whichever step made you wince the most.

### 14. Layoffs are being blamed on AI more than caused by it
Lemkin's clearer framing: openings just aren't backfilled with humans anymore — he says he's personally never fired anyone except for misconduct — but broader layoffs framed as "AI-driven" are frequently downsizing decisions that predate the tooling and use AI as the public justification. Practical career advice that follows: don't leave a job with happy customers chasing a hotter AI startup, since (per his account of a friend who cycled from a $100K to $800K to $200K role) the next seat may simply not exist. Owner.com's Kyle Norton is cited as a concrete before/after: reps there are being pushed from roughly $300-500K in ARR per rep a few years ago toward $3-5M per rep today with AI support.

---

## Key takeaways

1. AI has already made the classic cadence-based SDR and inbound-lead-qualifier roles close to obsolete; AE roles are next but slower.
2. The only way to become "hyper employable" in this transition is to personally train an agent yourself for 30 days — nobody gets there by delegating it.
3. Buy GTM agents, don't build them, and pick the vendor based on their forward-deployed engineer, not their feature list.
4. A well-trained agent beats a mediocre human easily; it doesn't need to beat your best human, and often it's trained on your best human anyway.
5. Running many agents is a full-time orchestration job — the "chief AI officer" role, not a side task.
6. Humans still win on the highest-value, lowest-volume relationships; AI wins everywhere there's more volume than a human is willing to personally work.

## References
- [We replaced our sales team with 20 AI agents—here's what happened next | Jason Lemkin (SaaStr) (video)](https://www.youtube.com/watch?v=I-R1bc1rlFs)
