# One plan for several open claims, Simplified PRD (Riverty BU Collection, A Fair Way Forward)

**Scenario:** Riverty BU Collection, A Fair Way Forward

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** Consumer with 2+ open claims in the instalment journey

## 1. The Big Picture
- **Vision:** A consumer with 2 or more open claims sees everything she owes in one place and agrees one affordable plan for all of it in one visit.
- **Press release:** Today, a Riverty customer with two open claims sees them one at a time. She can’t tell whether paying one changes anything about the other, so she calls an agent (40.0% with 2 claims, 43.0% with 3+, against 25.6% with one claim) or leaves (37.7% and 27.6% agree to a plan, against 52.1% with one claim).

Now she sees all her eligible claims with one combined total, enters her income once, and chooses one monthly amount that fits. Before she confirms, she sees which claims the plan covers and what happens next. It takes one input and three taps on her phone.
- **Success metric:** Agreement rate, starters with 2+ open claims 34.9%
- **Guardrail:** Agreement rate, single-claim starters 52.1%

## 2. The Details
### User stories
- As a consumer with 2+ open claims, I want to see all my eligible claims and one combined total, so that I know what I owe overall without opening each claim.
- All eligible claims are listed with creditor, reference and balance.
- The combined total equals the sum of the listed balances, to the cent.
- Claims are included by default, with no selection step.
- As a consumer with 2+ open claims, I want to enter my income once and choose one monthly amount, so that I can agree one plan that fits what I earn.
- Income is asked once, in one field, not once per claim.
- Every plan option is calculated on the combined total.
- An option that costs more than 30% of the stated income is shown but cannot be chosen (30% is a prototype assumption, to be replaced by the existing affordability rule).
- As a consumer with 2+ open claims, I want to see which claims my plan covers and what happens next, so that I don’t assume a claim is handled when it isn’t.
- The review and confirmation screens name every covered claim.
- The letters sentence is shown, and it comes from one approved text (see Technical Constraints and Edge Cases).
- One agreement reference is shown, not one per claim.
### Screens to build
- #	Screen	UI elements
- 1	Entry point: “Your open claims”	Heading with claim count (“You have 2 open claims”); one card per eligible claim (creditor, reference, balance); combined total as the largest figure; primary button “Set up one plan”; static line “Prefer to talk to someone? [phone number: TBD]”; optional (Should): greyed row for an ineligible claim with its reason
- 2	Feature core: “Choose one plan”	Sticky bar showing the combined total; one numeric field “Monthly income (€)” with inline error; three plan cards (6, 9 and 12 months) each showing monthly amount and number of payments; disabled state with reason for unaffordable cards; review panel after selection (covered claims list, total, monthly amount, first payment date, how each payment is split, letters sentence); button “Confirm plan” (disabled after first tap); back link
- 3	Success: “Your plan is set up”	Confirmation heading; one agreement reference; covered claims list with balances; total, monthly amount and number of payments; first payment date; letters sentence; optional (Should): missed-payment line
### Functional requirements
- ID	Requirement	Measurable rule
- FR1	Eligibility	A claim is included only if it shares portfolio and creditor with the others, is not disputed and is not on a plan. Combined flow starts only with 2 or more eligible claims.
- FR2	Combined view	All eligible claims are listed and the total equals their sum to the cent. Total and primary button are visible without scrolling at 375×667 with 2 claims.
- FR3	Income once	One income field in the whole flow. Valid range: 1 to 99,999. Zero per-claim questions.
- FR4	Options on combined total	Exactly 3 options (6, 9, 12 months). Instalment is the total divided by months, rounded up to the cent. The last payment adjusts so all payments sum exactly to the total. Options update on the same screen with no reload.
- FR5	Affordability	An option above 30% of stated income cannot be chosen. If no option passes, no agreement is created and the screen points to a person.
- FR6	One agreement	One agreement ID linked to all N claims. Each payment is split across claims pro rata by balance (prototype assumption, pending the backend allocation rule).
- FR7	Covered claims and letters statement	The review and confirmation screens name every covered claim and show the letters sentence from a single text constant.
- FR8	Effort ceiling	Entry to confirmation takes at most 1 text input and 3 taps (start, choose plan, confirm).
### Smart behaviors (Situation → Outcome)
- Situation	Outcome
- 1 eligible claim only	Combined flow is not shown. Existing single-claim journey applies (outside this prototype).
- 2+ eligible claims	Screen 1 lists all, all included, one total.
- A claim is disputed or already on a plan	Excluded from the list and the total. Optional: one-line reason shown.
- Income blank, zero or not a number	Inline error, plan cards stay hidden.
- Income changes after a plan was chosen	Options recalculate. If the chosen plan is now unaffordable, the choice is cleared.
- Option costs more than 30% of income	Card disabled with the reason “Higher than we suggest for your income”.
- No option is affordable	No Confirm button. Message sends her to a person. No agreement is created.
- Back from Screen 2	Entered income and selection are kept in memory.
- Page reload	Returns to Screen 1 with fresh demo data. Nothing is saved.
- Confirm tapped twice	One agreement only.
- 3 or more claims	Same flow. List scrolls and the total stays visible.
### Technical constraints
- One HTML file with plain JavaScript. No frameworks, libraries or build step.
- No external APIs, no network calls, no login.
- No persistence: no localStorage, cookies or saved sessions. State lives in memory.
- Synthetic data only, for example claims of €412.00 and €268.50 (total €680.50) plus one disputed claim of €189.00. Never real customer data.
- No real payments, no real agreement creation, no analytics. Events (start, plan chosen, confirmed) go to the console only.
- Letters sentence, missed-payment line and phone number are single constants, visibly marked “TBD: confirm with Collections/Legal”. Riverty styling is TBD until the brand rules are supplied.
- Not built: income document upload (B5), payment date picker (B6), income explainer (B2), shortest-plan-first ordering (B7), chat (B8), agent handoff summary (B4).

## 3. The Logistics
### Features out
- Combining across portfolios or creditors.
- Different terms per claim inside one plan.
- Discounts, settlements or negotiated reductions.
- Any change to the single-claim journey.
### Edge cases & safety guard
- Unhappy path	Rule
- Only one claim stays eligible after the exclusions	Fall back to the existing single-claim journey.
- Rounding	Payments always sum exactly to the total. The last payment absorbs the difference.
- Income very low	If no option passes the 30% rule, no agreement is created.
- A covered claim is disputed or paid after agreement	Outside the prototype. Backend needs a rule and an agent fallback before launch.
- Letters statement missing or unapproved	Show the conservative text (“Letters about these claims may still arrive until your first payment is received”), never a blank and never “letters will stop”.
### Decision log
- Gate the combined flow at 2+ eligible claims and leave single-claim screens untouched. This protects the single-claim base (52.1%, floor about 49.1%) and keeps the A/B read clean.
- Fixed menu of three durations, with no date picker, negotiation or ordering logic. It stops scope creep into B6, B7 and discount logic. The prototype only has to prove that one plan on one total is understood and chosen.
### Evals
- #	Target	Pass rule
- 1	Accuracy and safety triggers	100% of at least 20 test scenarios (2 and 3 claims × 3 durations × 4 incomes) give instalments that sum exactly to the total and correct affordability states. Zero agreements created when no option is affordable. Zero screens showing unapproved consequence wording.
- 2	Time-on-task	Median of 3 minutes or less on a phone from Screen 1 to confirmation. At least 8 of 10 testers finish unaided in 1 input and 3 taps.
- 3	Moment-of-misery comprehension	At least 9 of 10 testers correctly say which claims the plan covers, and correctly say whether any claim is not covered. At least 9 of 10 can restate the letters sentence.

## MoSCoW scope
- **Must:** One agreement covering several claims (backend): one agreement linked to N claims, with each payment allocated across them by a fixed rule.; One view of all eligible claims with each balance and a combined total, replacing the one-claim-at-a-time screen.; Plan options calculated on the combined total, reusing the existing affordability and income step once, not once per claim.; One agreement covering several claims (backend): one agreement linked to N claims, with each payment allocated across them by a fixed rule.
- **Should:** Show claims that are not in the plan, with the reason.; What happens if I miss a payment, in the combined plan terms.; Pause reminders and letters for the claims in the plan (backend).; What happens if I miss a payment, in the combined plan terms.; Deselect claims (default is all eligible claims included).; Per-claim breakdown of how each instalment is allocated.
- **Could:** Plain statement on the review and confirmation screens of which claims are covered and what happens to letters for them.; One confirmation listing every claim in the agreement and the total instalment.; Read-only view of the combined agreement in the existing agent tool.; Confirmation by email or SMS listing the claims in the plan.; Merging two existing active plans into one.; Editing or removing claims on a live plan.
- **Won't (now):** Combining across portfolios or creditors; Different terms per claim inside one plan.; Discounts, settlements or negotiated reductions.; Changes to the single-claim journey.

