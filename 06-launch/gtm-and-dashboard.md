# GTM Launch Plan, Riverty BU Collection, A Fair Way Forward

| Field | Value |
|---|---|
| Feature | letting a consumer with 2 or more open claims agree one instalment plan covering all her claims, with a clear statement of what happens to reminders on each claim |
| Goal | Conversion |
| Launch tier | S, Minimal |

## Goal & Audience
- **Goal:** Conversion, it can be meassured in conversion rates relatively fast
- **Target audience:** consumers with 2+ open claims who have not agreed a plan and are reachable by email or letter.
Secondary audience: clients, for information only.

## Launch Tier
- **S, Minimal**, 1. Reach. About 2,968 consumers per month start an instalment journey with 2 or more open claims (2,130 with 2 claims, 838 with 3 or more - confirmed by data) per month. They arrive through existing reminder letters and emails, so the feature reaches everyone who enters the journey without a separate campaign.

2. Expected impact (conversion among entrants). The ship threshold is +2.0 pp, about 59 extra consumers agreeing a plan per month. The test target is +3.8 pp, about 113. Planning range: about 60 to 115 extra agreements per month, worth 5,300 EUR to 10,200 EUR per month (Finance to confirm by 2026-12-15). These are planning figures, not a forecast.

3. Upside not in the estimate (more entrants). Phase 3 add the new option to reminder-emails and reminder-letters to raise the number of multi-claim consumers who enter the journey. This effect is unproven, so it is measured against a holdout and scales only if contacted consumers beat the holdout by at least +2.0 pp.

4. Communication effort. Existing channels (reminder-emails, reminder-letters), no external spend, about 35 internal person-days across Marketing (Claudia), Legal (Andreas), reminders (Andrea), Engineering and OPS (confirmed by Peter on 2026-11-11). Letters carry the longest lead time (template change, print cycle).

5. Risk is managed by gates, not by scale. Mobile drop-out between “See my plan” and “Agree to this plan”, and call-in among contacted consumers (+2.0 pp over holdout), are stop rules. The board approves the phased approach.

6. Revisit trigger. Reconsider the tier if the measured lift exceeds +3.8 pp, if monthly reach more than doubles, or if the value per agreement justifies heavier investment.

## Channels
1. **Owned: email reminder/letters to consumers with multiple claims, informing about new option - they are the ones that need this (maybe also through push notifications)**
2. **Owned: Release notes to clients - informing about new options that suffer a lot**
3. **Earned: after first data is collected - press release to reach new clients - after phase 3 data is collected**

## Enablement & Assets
In-flow content (consumer-facing): claim overview labels, information note about earlier reminders, reason texts, plan summary and confirmation. Written by Claudia, approved by Andreas, built by Joakim, tested in Phase 1 and 2.
Claudia to set up Client Success Manager-one-pager of process, communication updates, campaigns to push notifications
Claudia to support Sales for Slides for benefits and expected results
Claudia to define the marketing texts- Explaining as much as possible in the flow while not distracting

## Ownership, Budget & Timeline
- **Ownership & budget:** Me (Product Manager) to document the process for internal usage
Claudia (Marketing) to set up the communication to consumers and clients
I do not see any additional external costs - everything can be done interanlly (internal costs arise)
Andreas (legal) to sign of on wording in letters, emails and App
Andrea (reminer-PO) to surpress reminders if agreement was signed before Jan 2027
Andrea (reminder PO) to include additional marketing texts in letters and emails
Me to hand over to OPS and call-center (client success managers) 2 weeks before go-live
board to sign off phased approach and marketing
Karsten to track data and build up monitoring of KPIs
- **Timeline:** Phase 0, readiness (PM, Claudia, Andreas, Andrea, Karsten). Gate: Legal-approved copy, suppression tested end to end, tracking and holdout live, call-centre briefed, confirmed in writing.
Phase 1, implementation and Friendly User Test (in-flow only, no new mention). Gate: at least 200 consumers entered the overview, stop rules not triggered (this is a safety check)
Phase 2, User Acceptance Test (selected client, new mention, holdout inside the group). Gate: stop rules not triggered, agreement rate at or above holdout. Don’t use this result for the +2.0 pp gate, since one client may not represent the base.
Phase 3, wider reach and clients (email, then letters, release notes). Gate: contacted consumers beat the holdout by at least +2.0 pp.

## Success Metrics
- **Metrics:** Start point (all metrics): the day the consumer receives the reminder (email delivered or letter dispatched) that carries or precedes the combined-plan option.

Primary (conversion): share of consumers with 2+ open claims who receive a reminder and sign one multi-claim agreement within 10 days of receiving it.

Entry (supporting): share of those consumers who enter the claim overview within 10 days of receiving the reminder.

Conversion among entrants (supporting): of those who entered the overview within 10 days, the share who sign a multi-claim agreement within the same 10-day window.

Phase 3 gate: contacted consumers (new mention) beat the holdout (normal reminder, no new mention) by at least +2.0 pp on the primary metric.
- **Bad signal to watch for:** Stop rule 1: mobile drop-out between “See my plan” and “Agree to this plan” exceeds 61% + 5 pp, measured over at least 200 consumers. Stop rule 2: call-in within 14 days among contacted consumers exceeds the holdout by more than +2.0 pp. Stop rule 3: reminders or letters received after an agreement was signed exceed 0.5% of agreements. Action: the PM pauses the next phase within 3 working day and reviews with Legal and OPS. The board is informed.
- **Likely post-launch decision:** increase reach
