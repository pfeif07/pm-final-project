# One plan for several open claims, Simplified PRD (Riverty BU Collection, A Fair Way Forward)

**Scenario:** Riverty BU Collection, A Fair Way Forward

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** A consumer with 2+ open claims and variable shift-work income, who opens the portal on her phone during a short break.

## 1. The Big Picture
- **Vision:** A person with several open claims can agree one affordable plan on her phone in a single short break, and knows what happens if she misses a payment.
- **Press release:** Today, a shift worker with two open claims has to settle each one on its own, and one break isn’t long enough to do that. From now on she sees all her claims together and tells us what she can comfortably pay in a normal month. She gets one plan that covers everything, with every date and amount on a single screen.

Before she agrees, we tell her in plain language what happens if she misses a payment. There’s no call and no login, and the whole thing fits in a break.
- **Success metric:** +10% conversion in the multi-claim funnel, from journey started to plan agreed.
- **Guardrail:** call-in rate per 1,000 started multi-claim journeys must not exceed that baseline.

## 2. The Details
### User stories
- As a person with two open claims, I want to see them together with one total, so that I know what I owe before I commit.
- As someone with variable shift income, I want a single plan I can afford for all my claims, so that I don’t have to pay each one separately.
- As someone with tight finances, I want to see the full schedule and what happens if I miss a payment before I agree, so that I don’t take on more cost or pressure by accident.
### Screens to build
- Screen 1: Your open claims (entry point)
- Header with the BU Collection name and a short reason for the page.
- Claim cards, each with creditor label, balance and an “included” state.
- Excluded-claim card, greyed, with a one-line reason.
- Total row.
- Affordability input: “What can you comfortably pay in a normal month?” with a currency field. It stands in for B3’s result.
- One-line reason for asking (minimal, pending B2).
- Inline error state.
- Primary button: “See my plan”.
- Screen 2: Your plan (feature core)
- Plan summary: monthly instalment, number of payments, end date, total.
- “Covers” line listing every included claim.
- Full schedule table with every date and amount, ending in the total.
- Missed-payment statement box (placeholder text, pending Legal).
- Primary button: “Agree to this plan”.
- Back link.
- Screen 3: Plan agreed (success/confirmation)
- Confirmation heading.
- One-line plan summary: instalment, number of payments, end date.
- “View schedule again” expander.
- Missed-payment statement repeated.
- Close action.
### Functional requirements
- Combined view. All combinable claims are shown with balances, and the total equals their sum exactly. Two claims plus the total fit without scrolling at 360×640.
- Eligibility rule. A claim is combinable if it’s open, not in dispute and not already in a plan (assumed rule, to be confirmed with Legal and Collections). Every excluded claim is shown with a reason of 12 words or fewer, and none is silently dropped.
- Affordability gate. No plan is offered with an instalment above the entered amount. If no plan fits, show the no-plan state.
- One plan, one confirmation. The instalments sum exactly to the total of the included claims, with one payment per period. Plan length is 2 to 12 payments (assumed), agreed in a single confirmation.
- Schedule on one screen. Every date, every amount and the total are visible on Screen 2 without opening anything. With up to 12 rows that means a compact table, and scrolling within the same screen is allowed (assumed reading of “one mobile screen”).
- Missed-payment statement. The statement is 60 words or fewer, sits directly above the confirm button, and uses Legal-approved text.
### Smart behaviors (Situation → Outcome)
- Situation	Outcome
- Amount is blank, zero or not a number	Inline error under the field: “Enter an amount per month”. The button stays inactive.
- Amount is at or above the total	Offer the shortest allowed plan (2 payments). No pay-in-full path in the prototype.
- Amount would need more than 12 payments	Show the no-plan state with a prompt to raise the amount. Calling is not the lead action.
- One claim is ineligible	Include the others, show the excluded one with its reason on Screens 1 and 3.
- Only one claim is combinable	Run the same flow with singular wording.
- She goes back from Screen 2	Screen 1 keeps her amount, so she doesn’t re-enter it.
- Rounding leaves a remainder	Put it in the last instalment so the sum still equals the total to the cent.
- She taps “Agree”	Go to Screen 3. No further confirmation steps.
### Technical constraints
- One HTML file with plain JavaScript. No frameworks and no external libraries.
- No external APIs, no network calls and no login.
- All data is hardcoded mock data. Plan maths is computed locally.
- State lives in memory, and the three screens are sections within one page.
- No payment capture, no real consent flow and no persistence between sessions.
- No generated text. Every string is fixed.
- Usable at 360px wide with large tap targets.

## 3. The Logistics
### Features out
- Shortest plan shown first (B7).
- Chat assistant (B8).
- Agent handoff summary (B4).
- Photo upload and document skip (B5, in NEXT).
- Payment date matched to pay day (B6, in LATER).
- Full income explainer (B2, in NEXT). Only a one-line reason in the prototype.
- Reminder changes (T-207).
- Settlements, discounts, hardship routes and pay-in-full.
- Combining claims across different creditors.
- Choosing which claims to include (V2).
### Edge cases & safety guard
- No plan fits her amount. She gets a clear next step that isn’t a call.
- Claim balance changes mid-journey. Show a message and ask her to restart, rather than showing stale numbers.
- No claim is combinable. Say so plainly, with each reason, and don’t show an empty plan.
- She leaves mid-flow. Nothing is saved in the prototype, which is a known gap until save-and-resume (T-204).
- Safety and hallucination guard. The prototype has no generated content. Every figure is computed from the mock data, and the schedule sum is checked against the total before display, with a failure blocking the screen. The missed-payment text is one fixed, Legal-approved string, and nothing may be added about consequences that isn’t in it. The prototype never claims that collection letters stop, because that status isn’t in scope.
### Decision log
- Affordability is asked before any plan is shown, and only plans that fit are offered. This costs one extra step, but it prevents her picking the lowest-months plan and missing the second payment (N-02), which is the main call-in risk.
- Claims are included by default, with no claim picker. A picker is slower on a break and invites partial settlements. Letter status was moved to Should, so the prototype stays silent on it rather than guessing.
### Evals
- Accuracy: 100% of schedules sum to the claim total to the cent across 20 mock cases, including rounding and the 12-payment limit. Tolerance is zero.
- Time-on-task: median 4 minutes or less from Screen 1 to confirmation on a 360px viewport, with at least 4 of 5 test users completing it unassisted (assumed targets).
- Safety and comprehension: 0 of 30 test inputs produce a plan above the stated amount, and at least 9 of 10 testers can correctly state what happens if a payment is missed.

## MoSCoW scope
- **Must:** Combined claims view. All of her combinable open claims are shown together, with each balance and a total.; Claim eligibility rule. Define which claims can be combined, and show any excluded claim with a plain reason.; One combined instalment plan. A single schedule with one payment per period covers every included claim, agreed in one confirmation.; Affordability input. The plan is built from B3’s affordability result, so she is never offered a plan that doesn’t fit.; Full schedule before she agrees. Every date, every amount and the total are shown on one mobile screen.; Missed-payment statement. Before confirming, she sees in plain language what happens if she misses a payment, with wording approved by Legal.; Per-claim status after agreement. For each claim, she sees whether collection letters stop, and the payment allocation across claims is visible.; One-step confirmation with a summary she can see again. She confirms in a single action and can reopen the summary afterwards.
- **Should:** Save and resume. The plan survives the back button and interruptions (T-204). It would be a Must if sessions are short and frequently broken, so I’d push to get it into sprint one.; Two or three duration options with the monthly cost of each shown, so she can trade payment size against length.; Specific message for combination failures, with a next step that doesn’t automatically mean calling.; Confirmation by App or email with the full schedule.; Funnel and call-in instrumentation: events for each step, plus call-in tracking by cohort. Treat it as a release gate, because without a baseline the +10% target and the guardrail can’t be proven.
- **Could:** Let her choose which claims to include, or exclude one.; Add a newly arrived claim to an existing plan.; Show progress and remaining balance across claims after agreement.; Add payment dates to her calendar.; Self-service plan changes after agreement.
- **Won't (now):** Shortest plan shown first (B7). It nudges her toward plans she is likely to miss.; Chat assistant (B8). It is large, compliance-heavy, and a second route to the agent.; Agent handoff summary (B4). It serves Ops, not her conversion.; Photo upload and document skip (B5). It’s separate work in NEXT.; Payment date matched to pay day (B6). It’s in LATER.; Income explainer (B2). It’s in NEXT. For sprint one, only a minimal one-line reason for the income question is needed, if Legal requires it.; Reminder changes (T-207). This is out of scope, but the plan depends on reminders working.; Settlements, discounts or hardship routes, and combining claims across different creditors. (Assumed out of scope.)

