# Visual & Production Notes: Design for Capabilities

## On-screen visuals (in order)
1. 0:00 — Title card with "Principles 1-3" and subtitle
2. 0:08 — Talking head
3. 0:20 — Diagram: database tables vs. client workflows, arrow showing design direction
4. 0:45 — Talking head for restaurant analogy
5. 1:10 — Code: client-centric schema example showing graph traversal
6. 1:40 — Talking head
7. 2:00 — Code: purposeful duplication example with three user types
8. 2:25 — Diagram: three type boxes with shared/unique fields highlighted
9. 2:50 — Talking head for summary

## B-roll / inserts
- Brief restaurant kitchen analogy visual (stylized icon or illustration)

## Diagrams to create
- "Design direction" diagram: DB tables on left, client workflows on right, big arrow going right-to-left labeled "Start here"
- "Purposeful duplication" diagram: three boxes (Viewer, UserProfile, TeamMember) with overlapping and unique fields, Venn-diagram style

## Code to show
- `client-centric.graphql`: Graph traversal query example (highlight the nested structure)
- `purposeful-duplication.graphql`: Three separate types for user concepts (highlight how each has context-specific fields)
