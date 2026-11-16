# Hypothesis & Success Metrics (Module 3)

## Pre-work · Hypothesis check
- **Role , who you are solving for (from M2):** A 38-year-old with two open claims and variable shift-work income, who opens the portal on her phone during a short break.
- **Goal , what this user is ultimately trying to achieve:** To agree one affordable plan that covers both claims, and to know what happens if a payment is missed.
- **Friction / moment of misery , the specific pain blocking their goal:** She is asked for her income, and cannot tell whether it means this month or a normal month. She closes the portal “meaning to come back” (N-01). She also sees only one claim at a time and cannot tell whether paying one stops letters about the other (N-03; T-202). Nothing explains why income is asked or how long it is kept (T-206).
- **Current workaround , the external tool or manual process they rely on (M2):** Abandon and defer: closes the portal, intends to return, Call an agent instead of finishing online, Pick the option that “looks right” (shortest plan), then miss a payment, Handle claims one at a time (T-202: no way to set up one plan for two claims)
- **Problem Hook , your one-sentence framing of the business crisis (M1):** When a consumer like Mara can’t pay in one go, the digital journey fails her at the exact moment she needs it, so she abandons it or agrees to a plan she can’t keep, and Riverty’s north-star metric (SSR) counts it as a success while the cost returns to agents and recovery.
- **Value Proposition , the outcome your initiative promised to deliver (M1):** Understand your case, choose a plan that fits your real income, and keep it. Do it on your phone in minutes, with a person available if you want one.

## Read the evidence in your case
- **Where does your case say people stall or leave? Does that match the friction you wrote in Module 2?:** partly. The data confirms the friction exists, but the biggest leak is not where the story puts it.

Where people actually leave

Step	Drop from previous step
Outreach → entered portal	62% lost
Entered portal → started instalment journey	78% lost
Started → affordability questions	11.9%
Affordability → income document step	19.3%
Income document → plan review	22.1%
Plan review → agreement	16.9%
Agreement → no missed payment at 60 days	19.0%

In absolute terms, the largest losses are in the portal entry and in the step into the instalment journey (29,640 people enter the portal and never start one). Inside the journey itself, the worst conversion is income document to plan review (22.1% lost, about 1,300 people), followed by the affordability questions (19.3% lost, about 1,400 people).

What matches your friction

Income question (N-01): Two consecutive steps lose around 20% each: affordability questions and the income step. Together, roughly 2,700 people leave between starting the questions and seeing a plan. That fits “can’t tell what income means, so I’ll come back later.” But the data shows where people stop, not why. Ambiguity about “this month or a normal month” is a hypothesis until you see exit-page analytics, session recordings or call reasons.
Missed payments (the “plan I can’t keep” claim): 19% of agreements break within 60 days. That is a real signal and supports the point that the plan doesn’t fit real income. It is not proof of the cause, though. Compare broken-plan rates for variable-income versus fixed-income consumers if you can segment them.
Plan review loss (16.9%): Plausibly linked to the missing explanation of consequences, but nothing in the table tells us.

What the data doesn’t show

Two claims at once (N-03, T-202): The funnel counts people, not claims, so it cannot show whether multi-claim consumers drop more. You need the share of entrants with 2+ open claims and their conversion versus single-claim users.
Data transparency (T-206): No step captures it. It may be a driver of the income-step loss, but this is untested.
The “Call an agent” workaround: Invisible here. Some of the “lost” people may have phoned, so the funnel overstates abandonment and understates agent cost. You’d want call volumes joined to portal sessions.

Where the story overreaches

The hook implies the journey fails at the moment she needs it. For most people, the failure happens earlier: only 22% of those who enter the portal start the journey at all. Either most visitors come to do something else (check balance, pay in full, dispute), or the entry point doesn’t signal that an instalment option exists. Fixing the income question alone would recover at most a few hundred agreements per 100,000 outreach, while the 78% non-start is a far bigger pool, albeit with unknown intent.

Also, the SSR claim (“counts it as a success”) needs a check against the table. Agreements are 3.8% of outreach, and 3.1% survive 60 days. If SSR counts agreement creation, the 0.7-point gap (731 agreements) is the hidden cost. That’s a concrete, defensible number for the hook.

Suggested reframe

“Of every 100,000 people contacted, 3,846 create an agreement, but 731 of those break within 60 days, and about 2,700 leave at the affordability and income steps. We believe income ambiguity and the one-claim-at-a-time design drive both, and we need to validate that with multi-claim segmentation and exit data.”
- **What got better or worse in the case, and does that support the workaround your persona uses?:** this table has no time dimension, so it can’t show what got better or worse over time. It shows which segments do worse than others. Read that way, it supports two of the four workarounds, contradicts none, and leaves two untestable.

Where segments do worse

Segment	vs. comparison	Effect
2 open claims	Agreement 37.7% vs 52.1% (1 claim)	-14.4 pts
3+ open claims	Agreement 27.6%	-24.5 pts
2 / 3+ claims	Agent contact 40.0% / 43.0% vs 25.6%	+14 to +17 pts
2 / 3+ claims	SSR resolved 26.0% / 19.3% vs 40.6%	-15 to -21 pts
Mobile	Agreement 43.8% vs 54.0% (desktop)	-10.2 pts
Variable/shift income	Agreement 41.6% vs 48.1% (fixed)	-6.5 pts
Variable/shift income	Missed payment 22.5% vs 17.4%	+5.1 pts
Claim count is the biggest effect. 35.5% of starters have 2+ claims. If they converted like single-claim users, you’d get roughly 510 more agreements from 8,360 starters.
Income pattern hurts later. It costs fewer agreements up front (about 190 if parity), but it drives broken plans.
Mobile carries 78.5% of starters. Its agreement gap is worth around 670 agreements. Mobile users who do agree miss payments at the same rate as desktop users (18.9% vs 19.2%), so the problem is finishing, not plan quality.

What is not a driver: portfolio type and entry channel barely move anything (differences of about 1 to 2 pts), so you can drop them from the story.

Do the workarounds hold up?

Workaround	Verdict	Evidence
Abandon and defer	Supported, not provable	Mobile and variable-income users convert less, but agent contact barely rises (+0.5 pts mobile, +2.5 pts variable). The missing people aren’t calling, so they are leaving. There is no return-visit data, so “meaning to come back” can’t be tested.
Call an agent	Supported for multi-claim only	Agent contact jumps with claim count but not with income pattern. Whether the call resolves anything is unknown. SSR is lowest where calls are highest.
Pick the shortest plan, then miss	Partly supported, partly contradicted	Variable-income consumers do miss more. But their median instalment is lower (€63.09 vs €68.45), the opposite of what shortest plans would produce. That suggests the problem is timing against irregular income, not instalment size. Debt size could confound this, and there is no plan-length field.
One claim at a time	Consistent, not confirmed	Agreement falls and agent contact rises with claim count. Median instalment rises 51% (2 claims) and 96% (3+), but I can’t tell whether that is larger total debt or combined plans. You need claim count per agreement.

Two warnings

Chat assistant: users convert better (53.3% vs 44.4%) and need fewer agents, but they miss more payments (21.6% vs 18.3%). That could be self-selection. It could also mean the chat gets people to agree without checking affordability, which is your persona’s failure mode. Check this before presenting chat as a win.
SSR: the 34.7% resolved rate is well below the 46% agreement rate. So SSR is not simply counting agreements, and your hook says it counts a plan she can’t keep as a success. Confirm whether SSR is netted against missed payments before using that line.

The shape of your story: the front of the journey fails multi-claim and mobile users (fewer agreements, more calls), and the back fails variable-income users (broken plans). Mara is in all three groups, but this table is one-way splits, so I can’t say how the effects compound. A cross-tab of claim count by income pattern by device would show whether her segment is the worst case or just three overlapping averages.
- **Which user in the case is carrying the pain, and is that the person your Module 2 persona describes?:** mostly yes on the questions people ask, but this table can’t tell us who is asking, and it can’t see the person who never calls.

What the table shows

Three reasons map directly to the persona’s frictions:

Persona friction	Contact reason	Share
Consequences of missing a payment	what_if_i_miss_a_payment	18.6%
One plan for two claims (N-03, T-202)	can_claims_be_combined	17.3%
Why income is asked (T-206)	why_income_is_asked	16.2%

Together that is 52% of contacts and 53% of handle time. The contact total (2,592) is also about 31% of the 8,360 journey starters, which matches the agent-contact rates in your previous table, so this looks like the same population.

Two people are carrying the pain

The consumer who persisted enough to call. Her questions are about uncertainty (“what if”, “can I combine”, “why do you need this”), not “I can’t pay”. That fits the story: the journey doesn’t answer these questions, so people ask a human.
The agent. At roughly 12 minutes each, these contacts cost about 510 agent hours. The hook’s “cost returns to agents” claim holds up. The three persona-related reasons account for about 275 of those hours.

Where the persona doesn’t match

Mara is the person who goes quiet, and this table only counts people who called. Earlier data showed variable-income and mobile users convert less without calling more (+2.5 and +0.5 pts). The callers skew toward multi-claim users (+14 to +17 pts), not shift workers. So the person in this table is more the multi-claim consumer than Mara herself.
The income complaint is about purpose, not meaning. “Why is income asked” supports T-206. Nothing here shows “this month or a normal month” confusion (N-01). That may be hiding in “other” (7.4%) or in “wants lower monthly amount” (14.7%), so it needs a reason code of its own.
Some pain isn’t in the persona at all. Document upload problems (12.8%) are the fourth-largest cause of calls and plausibly a mobile issue. Another 13% (amount differs from letter, dispute or wrong claim) are people who may not belong in an instalment journey. Neither group is covered by the story.
“Wants lower monthly amount” cuts against the shortest-plan workaround. If people picked the shortest plan, you’d expect high instalments and complaints about them. That fits the previous finding that the problem looks like timing against irregular income rather than the amount itself.

Suggested fix: keep Mara as the lead, but add the multi-claim consumer as the second voice, since she is the one the data can actually see. To confirm the link, tag contacts with claim count and income pattern, and add a reason code for “this month vs normal month”.

## Step 2 · Craft your hypothesis
- **Qualitative evidence (from M2) , quote the specific friction / moment of misery for your persona:** The only words in it that sound like Mara are “meaning to come back”. The rest is the team’s description of her, so it works as a framing statement, not as qualitative evidence. If you present it as evidence, someone will ask where the verbatims are.

How far each part is backed up

Phrase in the brief	What backs it	Strength
“cannot tell whether it means this month or a normal month”	Nothing directly. The closest signal is 16.2% of calls asking why income is asked, which is about purpose, not meaning.	Hypothesis
“meaning to come back”	Variable-income users convert 6.5 pts lower without calling more, but there is no return-visit data.	Consistent, untested
“sees only one claim at a time... cannot tell whether paying one stops letters about the other”	17.3% of calls ask whether claims can be combined. Agreement falls from 52.1% to 27.6% as claims rise.	Strongest of the four
“Nothing explains why income is asked or how long it is kept”	16.2% of calls ask why income is asked. Nothing covers retention.	Partly supported
- **Quantitative evidence (from M3) , name the metric or data point that confirms the pain; cite the number:** Open claims	Journey starters	Agreement rate	Agent contact (7d)	SSR resolved
1	5,392	52.1%	25.6%	40.6%
2	2,130	37.7%	40.0%	26.0%
3+	838	27.6%	43.0%	19.3%

Combining the 2 and 3+ groups, 2,968 starters (35.5% of all starters) agree at about 34.9%, against 52.1% for single-claim starters. That is a 17-point gap, or roughly 510 agreements lost per 8,360 starters. The rate falls at every step as claims are added, and agent contact and SSR move the same way. The one-plan-for-two-claims pain (N-03, T-202) is the part of Mara’s story with the cleanest quantitative support.

Supporting data points

Contact reasons: 17.3% of agent contacts (448) ask whether claims can be combined. This is the same pain, seen from the call side.
Variable or shift income: 22.5% of agreements are followed by a missed payment within 60 days, against 17.4% for fixed salary (+5.1 pts). It also has a lower agreement rate, 41.6% vs 48.1%. This is the quantitative signal for the “plan she can’t keep” part of the story.

Suggested wording for the deck

“Consumers with 2+ open claims agree to a plan at 34.9%, versus 52.1% for single-claim consumers, and 40-43% of them contact an agent within 7 days (vs 25.6%). Shift-income consumers miss 22.5% of agreed payments within 60 days (vs 17.4% on fixed salary).”

Limits on the claim

The numbers show the pain exists and where it concentrates. They do not show why. The cause is still a hypothesis until it is tied to qualitative evidence.
Claim count and income pattern are separate one-way splits. No row describes Mara herself (variable income, 2 claims, mobile), so I can’t quantify her exact segment. A cross-tab would give you that number.
The income-meaning confusion (N-01) has no metric behind it yet. Don’t cite the 16.2% “why income is asked” figure for it, since it measures purpose questions, not “this month or a normal month”.
- **Persona , role, goal, and the friction you confirmed in the reconciliation steps:** Field	Draft
Role	A consumer with 2 or more open claims who enters the instalment journey. Device and income pattern are unknown until the cross-tab.
Goal	Agree one plan that covers everything she owes, and know what happens if she misses a payment.
Friction	She sees one claim at a time and can’t tell whether paying one stops letters about the others (N-03, T-202). She has no way to combine claims in the portal, so she asks “can these be combined?” and “what if I miss a payment?”
Workaround	Calls an agent: 40.0% (2 claims) and 43.0% (3+) contact an agent within 7 days, vs 25.6% for single-claim starters.
Outcome	If she stays online, she agrees to a plan at 37.7% (2 claims) or 27.6% (3+), vs 52.1% for one claim. Of those who agree, about 21% miss a payment within 60 days.
Problem hook (draft)	“When a consumer owes on several claims, the journey treats each one separately. She calls an agent or leaves, and the plans she does agree are higher (median €88.73 for 2 claims, €114.84 for 3+) and break about 21% of the time.”
Value proposition (draft)	One plan for everything you owe, a clear answer on what happens if you miss a payment, and a person available if you want one.
- **Problem you are solving , one sentence describing the specific friction this initiative removes:** This initiative removes the need for a consumer with two or more open claims to set up, understand and keep a separate plan for each one, by letting her agree a single affordable plan for everything she owes and see what happens if a payment is missed.
- **Strategic outcome , what behaviour change do you expect, and how does it map to retention / revenue / churn?:** the behaviour change is that multi-claim consumers finish one combined plan online instead of leaving or calling.
- **Primary success metric (initiative signal) , the leading indicator that tells you the gap is closing:** e hypothesis is narrower and much more testable. it also gives a clear success measure and give you the clear
- **Guardrail metric (product signal) , the metric that must NOT drop; it protects your existing base:** This is the metric that protects the existing base. Single-claim starters are 5,392 of 8,360 journey starters (64.5%) and the best-performing group in the data. The initiative changes the journey for people with 2+ claims, so the risk is that the added complexity (claim selection, combined-plan screens, extra explanation) slows down the people who already finish.

Why this one

It is the largest, healthiest group. Single-claim starters produce about 2,810 of the roughly 3,840 agreements in the table (5,392 × 52.1%). A 2-point drop there costs about 108 agreements, which would cancel out a large share of the 130-255 you hope to gain from multi-claim starters.
It is the cleanest control. If single-claim agreement moves, the change comes from the new journey or from outside factors, not from the multi-claim effect you are trying to measure.
It reacts quickly. You will see it within days, like the primary metric.

Suggested threshold (my proposal, to agree with the team)

Hold single-claim agreement at or above about 50% in the test group, i.e. no more than a 2-point drop from 52.1%, and no worse than the control group.
At 5,392 starters the baseline is only precise to roughly ±1.3 pts, and a test split in half is noisier. So set the threshold as “not worse than control by more than 2 pts” and run long enough to read it, not on a single week.
- **Decision window , how much time or data before you scale, pivot, or kill? minimum threshold to proceed?:** decide on the leading metric after a fixed minimum sample, scale in stages, and confirm plan quality at day 60. The numbers below are my proposals, not facts from your data. Your tables don’t say what period they cover, so I give sample sizes and a formula (weeks = required starters ÷ weekly 2+ claim starters) instead of dates.
- **Draft your full hypothesis sentence , one to three sentences; quote the metric, name the persona, name the outcome:** Based on 2+ claim starters agreeing to a plan at 34.9% versus 52.1% for single-claim starters, and 17.3% of agent contacts asking whether claims can be combined, I believe that letting the Multi-Claim Caller agree one plan for everything she owes will lead more of her to finish online instead of leaving or calling, as measured by a 5 to 10 point rise in 2+ claim agreement rate (34.9% to 40-45%). I will protect single-claim agreement (52.1%, no worse than control by more than 3 pts) and 60-day missed payments for 2+ claims (about 21.3%, must not rise), and will make a go/no-go decision after 4 full weeks and about 1,460 multi-claim starters per arm.
