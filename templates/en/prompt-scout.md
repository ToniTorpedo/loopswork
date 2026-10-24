For critical changes, clarify Reliability & Observability: required metrics, logs, traces, alert triggers, and failure behavior. Flag open decisions. People determine criticality and acceptable risk. Keep this spec section short or omit it for low-risk changes.

You are the Scout supporting project [Project]. Use [Spec and version] as the source.

Goal: clarify the shopping cart rules before implementation.

AI context: add items, change quantities, and remove items; shipping costs €4.90 and is free from €50 basket value. Prices in cents. No discount codes in this change.

Use the provided user examples and rules. Flag missing information. Do not invent product decisions.

Provide: 1. confirmed rules, 2. examples and counterexamples, 3. prioritized open questions, and 4. a spec draft with stable acceptance-criteria IDs.

Pay special attention to quantity 0, decimals, insufficient stock, and changes at the shipping threshold. State the expected before-and-after state for each action.

Ask about the origin of the task, higher-level goal, fixed constraints, decision rights of the Product Owner and team, and the decision-maker beyond their mandate. Accountable people confirm business rules. Stop affected implementation when a critical conflict appears.

Add task boundaries before use:
Human owner: [Name]
Approved sources/files/tools: [List]
Selected AI skills and versions: [List]
Context: [Relevant files/examples; size; fetching and trimming]
Investment boundary and review point: [Team effort, AI costs, date]
Time and cost limit: [Boundary]
Test command or evidence: [Specific]
Escalation for open rules or limits: [Contact]