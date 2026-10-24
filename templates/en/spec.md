SPEC [short name / ID] · Version [0.1] · Status: Draft

START HERE AS PRODUCT OWNER
Replace the brackets with short sentences. Bullet points are enough. Keep anything unknown as “open” with a named owner. Add technical and measurement details together. Examples are guidance, not requirements.

1. Which problem are we solving, and for whom?
The task comes from [team / board / executive team / strategic initiative / other source].
It contributes to [higher-level goal and task link]. Fixed constraints are [goal, date, budget, or mandatory scope].
The Product Owner and team may decide [decision space]. Changes beyond it are confirmed by [responsible person / decision body].
As [target group], I want to [complete a task], so that [benefit].
Today, [observable problem] occurs. This is supported by [feedback, observation, or data; otherwise: still to verify].
Example: customers want to correct their selection so they order the right quantity. Quantity changes are currently cumbersome.

2. What should improve?
By enabling [small change], expect [observable improvement] because [assumption].
Value is indicated when [signal or metric] changes from [baseline / still open] to [target / to agree together].
[Unwanted side effect] must not increase.
Example: more customers reach checkout, while price errors must not increase. Agree on measurement details with the Measurement Partner.

3. What is the smallest useful scope?
This change enables [a few specific capabilities at most].
Deliberately defer [requests outside the scope].
Slice: can the spec be understood with bounded context, implemented without a large system explanation, and verified independently?
If not: [smaller specs with their own tests and required context]. The Product Owner and team confirm the split.
Invest at most [team effort] and [AI budget]. At [review point], decide whether to continue or shape the scope.
Agree on this boundary with [team / responsible person].

4. Show the intended behavior through examples.
AK-01: Given [starting state], when [action], then [visible, testable result].
AK-02: Given [boundary case], when [action], then [expected response].
AK-03: Given [failure case], when [invalid action], then [feedback and unchanged state].
After [further action], [new state] must be visible.
Example: given an item with quantity 1, when it is added again, then one line item with quantity 2 is shown.
Check: what happens when empty, at 0, above limits, without permission, or after repeated clicks? Include only relevant cases. Do not renumber acceptance-criteria IDs later.

5. What still needs a decision?
Open question: [question]. [Name] resolves it by [date]. It blocks [affected implementation / nothing].
Business confirmation by: [Product Owner / Feature Partner, date]. Until then, this spec remains a draft.

ADD WITH THE TEAM
6. Technical agreement—the team leads; the Product Owner clarifies business effects.
Affected interface / inputs: [contract or link].
Results, errors, permissions, and privacy: [rules / open decisions].
Tests: [acceptance-criteria IDs, counterexamples, integration and regression tests].
Business acceptance: [person, scenarios, test version, and date / trigger].
Release, operational checks, and rollback: [plan, owner, and triggers].
For small tasks, a reference to existing standards may be enough.

Reliability & Observability · OPTIONAL
Fill in only relevant details. Low-risk changes need little or no additional information; a reference to applicable standards may be sufficient.
Scale depth to criticality, potential harm, frequency of use, dependencies, and recoverability.
Criticality: [high / medium / low]
Monitoring: [Which metrics, logs, or traces are required?]
Alert when: [Which specific deviation triggers an alert? Clarify response, ownership, and escalation.]
SLO / expected availability: [optional, only when relevant to the component]
Failure behavior: [retry, fallback, rollback, degradation, manual intervention, or another response]
Dashboard / tool: [optional link to Datadog, Grafana, Sentry, or another system]
Accountable people confirm criticality, acceptable risk, alert thresholds, SLOs, escalation, and approval.

7. Evaluate impact—with support from the Measurement Partner.
Primary metric / numerator / denominator: [definition].
Source / events / comparison / period: [plan].
Guardrail metrics and decision rule: [limits, outstanding data].
Scorecard: [link]. [Person] decides continuation at [review point].

8. Record a reliable version.
Owner: [name]. Versioned source spec: [link].
Confirmed version and immutable source: [version + commit link / document revision].
AI tasks, tests, review, and acceptance reference [this version].
The release connects [spec version, verified code version, and evidence].
Change history: [version, date, change, rationale, affected acceptance-criteria IDs, confirmation].
When changes occur, check effects on ongoing AI tasks and explicitly record the agreed version.

QUICK CHECK BEFORE IMPLEMENTATION
Can another person use these examples to tell what correct behavior is?
Are scope, accountability, and investment boundaries clear?
Are critical open questions resolved and rules confirmed by people?
Is everyone using the same spec version?