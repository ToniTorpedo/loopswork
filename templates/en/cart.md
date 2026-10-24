CART 1.0 – complete example spec

Context and version
SPEC CART · Version 1.0 · Reference version of the LoopsWork learning example
This completed example spec describes the shopping cart rules already shown. Roles, budget, and measurement plan are illustrative assumptions. It is not a real product approval or evidence of a production implementation.
Reference source: https://loopswork.dev/en/docs/#cart-spec
Owner: Online Shop Product Owner (example role). Business confirmation: Feature Partner and Product Owner; technical agreement: Delivery Team; measurement plan: Measurement Partner.
In this learning workflow, CART 1.0 is confirmed once B3 is complete. Add a real confirmation date and immutable Git commit or document revision when adopting it into a project. The website URL alone does not replace that fixed version.

1. Problem and target group
Illustrative task: a department leader owns the strategic initiative “Simplify shopping” and commissions the Product Owner to deliver the cart contribution. This is an additional example assumption. The Product Owner prioritizes scope within the mandate; the team chooses implementation and division of work. Changes to the higher-level goal or budget go to the department leader.
Customers with selected items should be able to correct quantities, remove items, and understand the total price before checkout. The example assumes that cumbersome corrections and unclear shipping costs make checkout harder to start. This learning demo has no real user evidence; in a project, the Feature Partner checks the assumption through user tests and feedback.

2. Expected value and investment boundary
Hypothesis: if customers can easily change quantities and understand the total price, more eligible sessions with a filled cart will start checkout.
Example baseline: 58%. Example target: at least 62% while meeting guardrails. These figures are fictional assumptions, not measurements from this website.
For the first change: at most five team working days and €50 in AI costs. Review at half the budget spent. Team effort is not calendar duration. In this example, the Product Owner may continue, shape scope, or stop within this boundary. The responsible department leader confirms a larger budget or changed strategic goal.

3. Scope and deliberate boundaries
Included: add items, change quantities, remove line items, calculate basket value and shipping costs, display the total, and prevent checkout from an empty cart.
Excluded: discount codes, wishlist, guest-account synchronization, payment, and real order processing.
This website runs the rules locally in the browser. A production cart also needs server-side checks, access control, operations, and approvals. Requirements for a real service below are not existing website features.

4. Agreed rules and acceptance criteria
AK-01 · Add: an existing item does not create a second line item. Given coffee with quantity 1, when the same item is added again, then one line item has quantity 2.
AK-02 · Quantities: only nonnegative whole numbers are valid. Quantity 0 removes the line item. Reject negative and fractional quantities and keep the existing cart unchanged.
AK-03 · Stock: the requested quantity must not exceed available stock. With stock 5, reject quantity 6 without changing the cart. Quantity 5 is valid.
AK-04 · Money and totals: calculate money in whole cents. Basket value is the sum of quantity × valid unit price. Total price is basket value plus shipping. Update displayed totals after every successful add, change, or removal. Server-side prices are authoritative in a real service. Example: 2 × 1,490 cents + 490 cents shipping = 3,470 cents.
AK-05 · Shipping: for a nonempty cart below 5,000 cents basket value, shipping costs 490 cents. At exactly 5,000 cents or above, shipping is 0. Boundary cases: 4,999 → 490 cents shipping; 5,000 → 0. After a quantity change crosses the threshold, apply the new total immediately.
AK-06 · Empty state: after the final item is removed, basket value, shipping, and total are 0. Checkout is disabled and the empty state is clearly explained.
Invalid actions show understandable feedback and leave both items and totals unchanged. Stock limits also apply to repeated additions.

5. Technical contract for a real implementation
Draft: PUT /cart/items/{productId}
Body: { "quantity": 2 } sets the requested absolute quantity.
quantity: 0 removes the line item. Repeating the same set operation does not increase quantity again. The add action in the UI determines the new target quantity.
200: updated cart including server-side totals.
400: invalid quantity. 404: unknown item. 409: insufficient stock. These errors leave the cart unchanged.
The service validates inputs, current price, stock, and permission for the affected cart. This contract does not place an order or reserve stock.
Before production implementation, the team agrees on authentication, 401/403 handling, concurrent changes, transaction boundaries, and the exact response schema. These open technical issues are not implicit freedom for agents. They block the affected production work.

6. Tests, independent review, and acceptance
Tests reference CART 1.0 and the relevant acceptance-criteria IDs. The Reviewer uses the same fixed spec version as the implementing agent.
Automate checks for repeated additions, quantity 0, negative and fractional quantities, stock exactly reached and exceeded, cent calculations, both sides of the shipping threshold, and empty checkout. Check state transitions: after every action, line items, basket value, shipping, and total must agree.
For a real implementation, also test interface errors, unauthorized access, current server-side prices, and concurrent changes according to the confirmed contract.
The Delivery Team provides evidence and a human reviewer checks independently. The Feature Partner accepts real shopping flows: changing quantities, removing the final item, exceeding stock, and crossing the shipping threshold. Record spec version, code version, test cases, and gaps. Silence is not acceptance.
Executable website test cases are learning aids. They do not replace server integration, security review, or business acceptance.

7. Measurement plan and product decision
Primary metric: eligible sessions starting checkout divided by eligible sessions with a filled cart. Exclude test traffic and count repeated events only once per session.
Measurement points: successful quantity changes, cart errors, and checkout starts. Attribute actions clearly; do not collect free-text personal data.
Example measurement window: days 6–18 after activation on day 5, comparing a control group with the new version. The 1,000 sessions per group are illustrative. The Measurement Partner agrees on group assignment, comparability, and required data volume in advance.
Example guardrails: change errors at most 1%; loading time p95 at most 1.5 seconds. Also observe price complaints and completed purchases; agree on their decision thresholds before a real experiment.
On day 20, the Product Owner reviews the Scorecard with the team and partners, decides within delegated authority, and returns findings to the commissioning department leader. The leader decides strategic changes. Missing data or unresolved comparability leads to further investigation rather than automatic expansion. Address urgent harmful findings immediately.
The Scorecard with fictional results is at https://loopswork.dev/en/docs/#scorecard. This website does not collect these shop metrics.

8. Release, operations, and rollback
In the example, activate for a limited user group after business acceptance on day 5, and only with the required approvals. The release links CART 1.0, actual code version, test evidence, acceptance, and Scorecard. Assign measurement data to the release and user group.
The team and release approver check error rate, price accuracy, and data collection. Stop activation and use the agreed rollback path for incorrect prices or harmful findings. Before a real release, clarify and test the switching mechanism, accountable person, and handling of data already changed.
After rollback, code, configuration, and the associated spec version must match.

9. Open questions, accountability, and versioning
Open before real implementation: user evidence (Feature Partner), authentication and concurrent access (team), comparison design and guardrails (Measurement Partner), approval and rollback paths (team and release approver). Resolve each before implementation or the affected work starts; assign real names and dates in the project.
Version 1.0 documents the six rules already agreed in the learning example. This completed version brings them together and explains their use; it does not change the shipping threshold.
AI tasks, tests, review, and acceptance cite CART 1.0 and a fixed commit or document revision. Review a business change as a new draft with differences, rationale, affected acceptance-criteria IDs, and human confirmation. Check effects on ongoing tasks.
The CART 1.1 proposal with a 6,000-cent shipping threshold described on the example page is hypothetical and not part of this version. CART 1.0 with 5,000 cents remains valid until a new agreement is explicitly confirmed.