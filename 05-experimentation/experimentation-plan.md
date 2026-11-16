# A/B Experiment Brief, Riverty BU Collection, A Fair Way Forward

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | letting a consumer with 2 or more open claims agree one instalment plan covering all her claims, with a clear statement of what happens to reminders on each claim |
| Persona | A consumer with 2+ open claims and variable shift-work income, who opens the portal on her phone during a short break. |
| Expected outcome | agreement rate increases to at least 41.4% per consumer |
| Primary success metric | Per multi-claim consumer, the share of her combinable claims under an agreement within 45 days of first exposure, averaged across consumers |
| Baseline rate | agreement rate 37.6% |
| Guardrail metric | Share of multi-claim consumers who call in within 14 days of first exposure |
| Guardrail boundary | Upper bound of the one-sided 95% CI on (variant minus control) is at most +2.0 pp |
| Second guardrail | · |
| Minimum Detectable Effect | 3.8 |
| Sample size per arm | 2.800 |
| Traffic split | 50 / 50 |
| Test duration | 8 weeks |
| Significance threshold | 0.05 |

## Control vs. Variant
- **Control (A):** Screen 1: Your open claims (entry point)

Header with the BU Collection name and a short reason for the page.
Section “Claim in your agreement”: one claim card for the combinable claim (from current opened link), with a label recognizable by the consumer, balance and an “included” state. Every other combinable claim is listed in “Claims outside your agreement” with the reason “Not part of this agreement.”
Information note, directly under the included claim card and before the total (light grey background, “i” icon, not styled as a card) - describing what happens with the already received letters/reminders
Total row, directly under the information note (it covers only the claim in the agreement).
Affordability input: “What can you comfortably pay in a normal month?” with a currency field. It stands in for B3’s result. It sits below the total and applies only to the claim in the agreement.
One-line reason for asking (minimal, pending B2). It states that the question applies to the claim in the agreement.
Inline error state.
Primary button: “See my plan”.
Section “Claims outside your agreement”, placed under the affordability check, with a short intro line saying these claims are not part of this plan. It holds greyed cards, each with a one-line reason of 12 words or fewer, of two kinds:
Eligible but not included (every other combinable claim): the reason “You can arrange a plan for this one separately.” and a link “Set up a plan for this claim”. The link opens the same flow (Screens 1 to 3) for that claim alone.
Genuinely ineligible (disputed, legally blocked, already in a plan, or otherwise not part of the agreement): the specific reason, for example “Under dispute. We’ll contact you separately.” or “Not part of this agreement.” No link.

Screen 2: Your plan (feature core)

Plan summary: monthly instalment, number of payments, end date, total.
“Covers” line listing every included claim.
Full schedule table with every date and amount, ending in the total.
Missed-payment statement box (placeholder text, pending Legal).
Primary button: “Agree to this plan”.
Back link.

Screen 3: Plan agreed (success/confirmation)

Confirmation heading.
One-line plan summary: instalment, number of payments, end date.
A line naming any claim outside the agreement, with its reason.
“View schedule again” expander.
Missed-payment statement repeated.
Close action.
- **Variant (B):** Screen 1: Your open claims (entry point)

Header with the BU Collection name and a short reason for the page.
Section “Claims in your agreement”: one claim card for every combinable claim, each with a label recognizable by the consumer, balance and an “included” state.
Information note, directly under the included claim card and before the total (light grey background, “i” icon, not styled as a card) - describing what happens with the already received letters/reminders
Total row, directly under the information note (it covers only the claim in the agreement).
Affordability input: “What can you comfortably pay in a normal month?” with a currency field. It stands in for B3’s result. It sits below the total and applies only to the claim in the agreement.
One-line reason for asking (minimal, pending B2). It states that the question applies to the claim in the agreement.
Inline error state.
Primary button: “See my plan”.
Section “Claims outside your agreement”, placed under the affordability check, with a short intro line saying these claims are not part of this plan. It holds greyed cards, each with a one-line reason of 12 words or fewer, of two kinds:
Eligible but not included (every other combinable claim): the reason “You can arrange a plan for this one separately.” and a link “Set up a plan for this claim”. The link opens the same flow (Screens 1 to 3) for that claim alone.
Genuinely ineligible (disputed, legally blocked, already in a plan, or otherwise not part of the agreement): the specific reason, for example “Under dispute. We’ll contact you separately.” or “Not part of this agreement.” No link.

Screen 2: Your plan (feature core)

Plan summary: monthly instalment, number of payments, end date, total.
“Covers” line listing every included claim.
Full schedule table with every date and amount, ending in the total.
Missed-payment statement box (placeholder text, pending Legal).
Primary button: “Agree to this plan”.
Back link.

Screen 3: Plan agreed (success/confirmation)

Confirmation heading.
One-line plan summary: instalment, number of payments, end date.
A line naming any claim outside the agreement, with its reason.
“View schedule again” expander.
Missed-payment statement repeated.
Close action.
- **Held constant (isolation check):** Screen 1: Your open claims (entry point)

Header with the BU Collection name and a short reason for the page.

Information note, directly under the included claim card and before the total (light grey background, “i” icon, not styled as a card) - describing what happens with the already received letters/reminders
Total row, directly under the information note (it covers only the claim in the agreement).
Affordability input: “What can you comfortably pay in a normal month?” with a currency field. It stands in for B3’s result. It sits below the total and applies only to the claim in the agreement.
One-line reason for asking (minimal, pending B2). It states that the question applies to the claim in the agreement.
Inline error state.
Primary button: “See my plan”.
Section “Claims outside your agreement”, placed under the affordability check, with a short intro line saying these claims are not part of this plan. It holds greyed cards, each with a one-line reason of 12 words or fewer, of two kinds:
Eligible but not included (every other combinable claim): the reason “You can arrange a plan for this one separately.” and a link “Set up a plan for this claim”. The link opens the same flow (Screens 1 to 3) for that claim alone.
Genuinely ineligible (disputed, legally blocked, already in a plan, or otherwise not part of the agreement): the specific reason, for example “Under dispute. We’ll contact you separately.” or “Not part of this agreement.” No link.

Screen 2: Your plan (feature core)

Plan summary: monthly instalment, number of payments, end date, total.
“Covers” line listing every included claim.
Full schedule table with every date and amount, ending in the total.
Missed-payment statement box (placeholder text, pending Legal).
Primary button: “Agree to this plan”.
Back link.

Screen 3: Plan agreed (success/confirmation)

Confirmation heading.
One-line plan summary: instalment, number of payments, end date.
A line naming any claim outside the agreement, with its reason.
“View schedule again” expander.
Missed-payment statement repeated.
Close action.

## Hypothesis
> I believe that letting a consumer with 2 or more open claims agree one instalment plan covering all her claims, with a clear statement of what happens to reminders on each claim for A consumer with 2+ open claims and variable shift-work income, who opens the portal on her phone during a short break. will result in agreement rate increases to at least 41.4% per consumer, as measured by a 3.8 change in Per multi-claim consumer, the share of her combinable claims under an agreement within 45 days of first exposure, averaged across consumers within 8 weeks. We will protect Share of multi-claim consumers who call in within 14 days of first exposure throughout the test.

## Shipping criteria
> We will **ship** if Per multi-claim consumer, the share of her combinable claims under an agreement within 45 days of first exposure, averaged across consumers improves by ≥ 3.8 at 0.05 and Share of multi-claim consumers who call in within 14 days of first exposure does not reach Upper bound of the one-sided 95% CI on (variant minus control) is at most +2.0 pp after 8 weeks.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 8 weeks, no results reviewed before this date.
