# AI Synthesis, Product Health & Insights Summary (Module 2)

## Responses
- **Assumption to validate #1:** Customers would prefer self service over direct contacts
- **Assumption to validate #2:** Process is too complex for customers
- **Assumption to validate #3:** customer does not know what needs to be paid
- **Moment of misery / red flag #1 (e.g., “user gave up after 3 tries”):** Honestly I prefer to call. A person can tell me if this is going to cost me more.
- **Moment of misery / red flag #2:** I opened it on my break. It asked for my income and I did not know if they meant this month or a normal month. I closed it and meant to come back.
- **Moment of misery / red flag #3:** Portal shows each claim separately. There is no way to set up one plan for two claims.
- **Product Health & Insights Summary (Claude's output):** Product Health & Insights Summary
Executive Summary

The platform is largely functional, but gaps in data consistency, document handling, and reminder timing are interrupting consumer journeys at the moments that matter most. The larger issue is experiential: consumers cannot tell what a plan will cost, what happens if they miss a payment, or how their data will be used, so they hesitate, choose poorly, or abandon the journey. Agents and compliance stakeholders are affected by the same opacity, which carries a growing risk of failed plans, repeated work, and complaints that clients are tracking.

Thematic Synthesis
1. Technical Stability and Data Integrity

Most defects cluster around moments where consumers must provide information or rely on figures. The most significant is document upload failure on mobile, which is the likely channel for shift workers and others completing the journey on a break. Data inconsistency between the portal and letters is concentrated in purchased portfolios, where the underlying records are also less reliable. Smaller flow defects, such as lost answers and mistimed reminders, compound the problem by forcing rework or creating avoidable missed payments.

Income document upload times out on mobile (T-201): Critical. 853 journeys in the sample month requested a document that never arrived, which blocks plan setup at a key step.
Portal amount differs from the letter (T-203, N-07): Critical. 531 journeys were affected, 343 of them in purchased portfolios (about 65%). Consumers withhold agreement until someone explains the discrepancy, and the mismatch undermines credibility.
Reminder before first instalment sent after the due date (T-207): High. This directly causes missed payments and feeds plan failure and complaints.
Back button clears affordability answers (T-204): Medium. Consumers must re-enter sensitive financial information, which increases drop-off.
Inconsistent data across acquired portfolios (N-11): Medium. Phone and address history is unreliable in some portfolios, which limits contact quality and confidence in the data.
2. Onboarding and Plan Selection UX

Consumers struggle to translate their situation into the questions and choices the portal presents. Ambiguous wording around income leads to abandonment, while plan options appear to steer people toward unsuitable choices. Consumers with several open claims are poorly served because each claim is handled in isolation, leaving them uncertain how actions on one affect the other.

Ambiguous income question (N-01): High. Consumers cannot tell whether “income” means current or typical earnings, and some leave without finishing.
Plan options misread as a “right answer” (N-02): High. A consumer chose the shortest term, found the amount unaffordable, and missed the second payment.
No way to combine multiple claims into one plan (T-202, N-03): High. Consumers see one claim at a time and cannot tell whether paying one stops contact about the other.
Back-navigation and re-entry burden (T-204): Medium. Covered above as a stability defect, but it also erodes confidence in the journey.
3. Trust, Clarity, and Explainability

Consumers are being asked for sensitive information and commitments without enough context about why it is needed, how it is used, or what the consequences are. This is most visible among consumers with several claims or tight finances, and it extends to the chat assistant, which can confirm a plan quickly without setting out the downside of missing a payment. Compliance has flagged that decisions must be explainable to both consumers and agents, which the current experience does not support.

No explanation of why income is requested or how long it is kept (T-206, N-06): High. Consumers fear that entered figures could be used against them, which discourages honest input.
Chat confirms plans without showing missed-payment consequences (T-208, N-05): High. Speed creates confidence, but consumers remain unsure what happens if they pay late.
Plan recommendations not explainable to consumer or agent (N-12): High. A compliance requirement that current outputs, showing only a number, do not meet.
Consumers seek human reassurance on cost (N-04, N-07): Medium. Some prefer phone contact because they trust a person to tell them whether a decision will cost more.
4. Agent Effectiveness and Support Load

Agents work without visibility into the digital journey, so they re-collect information consumers have already provided and cannot diagnose why a plan was offered when it fails. This adds call time and frustration for consumers, and it makes failed plans harder to understand and prevent. The client’s focus on complaints and broken plans raises the commercial stakes.

Agents cannot see consumer-entered data or plan rationale (T-205, N-08, N-09): High. Roughly half of calls begin by repeating details already supplied online, and failed plans cannot be traced to their cause.
Rising broken plans visible in client reporting (N-10): High. Complaint volume is a client success measure, so unresolved journey issues carry a reputational and contractual risk.
Minor Technical Debt

Inconsistent portfolio data quality for lower-volume attributes, minor reminder-content wording issues, and incidental screen-level friction not tied to a specific journey failure.
- **Did the AI catch the specific moment of misery / pain point you found in Step 1?:** yes, mainly
- **Did it smooth over a critical frustration into a generic bullet point?:** yes, looked good in this case.
- **Did the AI try to suggest features or a roadmap despite the constraints?:** no, it did not
- **Logic leak / hallucination #1 (e.g., “AI suggested a new search bar feature, roadmap leak”):** _(not filled in)_
- **Logic leak / hallucination #2:** _(not filled in)_
