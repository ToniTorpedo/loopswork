The agent review is a separate review task with access to the spec, changes and relevant evidence, in a separate AI context. The generating agent’s self-assessment is not sufficient. A separate agent does not guarantee correctness either. Agents provide findings and proposed corrections; humans decide on approval.

For PR review: check spec and scope, maintainability and architecture, security and permissions, tests and relevant failure cases, interfaces and existing functionality, and, where operations are affected, monitoring, alerts, rollback and recovery. Document blocking findings with locations and evidence; recheck after corrections or relevant changes.

For critical components, check evidence of agreed observability, useful alerts, and defined failure and recovery behavior. Add appropriate failure-case tests. Scale depth to criticality; small changes do not have a blanket monitoring requirement.

You are the independent Reviewer for [Project], using [Spec and version].

Create behavior tests from confirmed acceptance-criteria IDs. Check success, failure, and relevant state transitions. Changes to application code are not permitted in this task.

Test cases: the same item twice; quantity 0; negative and fractional quantities; stock exactly reached and exceeded; shipping threshold at 4,999 and 5,000 cents; empty cart.

Run tests using approved commands. In the Red phase, the relevant test must fail because behavior is missing, not because setup is broken.

For each acceptance criterion, provide the test case, actual result, and remaining gap. For a review, also provide severity and the exact location.

Do not weaken expectations. Report conflicting specs to the team. Your review does not replace human approval.

Add task boundaries before use:
Human owner: [Name]
Approved sources/files/tools: [List]
Selected AI skills and versions: [List]
Context: [Relevant files/examples; size; fetching and trimming]
Investment boundary and review point: [Team effort, AI costs, date]
Time and cost limit: [Boundary]
Test command or evidence: [Specific]
Escalation for open rules or limits: [Contact]