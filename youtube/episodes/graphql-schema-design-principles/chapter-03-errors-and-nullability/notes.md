# Visual & Production Notes: Errors & Nullability

## On-screen visuals (in order)
1. 0:00 — Title card "Principles 4-6"
2. 0:08 — Talking head
3. 0:25 — Code: explicit-errors.graphql showing union return types
4. 0:50 — Diagram: generic error flow vs typed result flow, side by side
5. 1:10 — Talking head
6. 1:25 — Code: nullability.graphql showing @semanticNonNull usage
7. 1:50 — Talking head for transition to principle 6
8. 2:00 — Red warning banner animation: "Null Blast Radius"
9. 2:10 — Animated tree diagram: null propagation climbing up the tree, wiping out nodes
10. 2:45 — Talking head for the email example
11. 3:10 — Ship bulkhead analogy visual
12. 3:30 — Talking head for summary

## B-roll / inserts
- Red pulsing "alert" animation for the blast radius reveal
- Ship cross-section diagram showing bulkhead compartments (brief, 3-4 seconds)

## Diagrams to create
- Side-by-side comparison: generic errors (messy, question marks) vs union types (clean, branched)
- **Key diagram**: Null propagation tree. Start with a deep field failing (red). Animate the red spreading upward through non-nullable fields. Show it stopping at the first nullable field. Then show worst case: entire query going red.
- Ship bulkhead cross-section (simple, stylized)

## Code to show
- `explicit-errors.graphql`: Union return type for a mutation (highlight the union and each error type)
- `nullability.graphql`: @semanticNonNull usage vs regular nullable vs non-nullable (highlight the differences)
