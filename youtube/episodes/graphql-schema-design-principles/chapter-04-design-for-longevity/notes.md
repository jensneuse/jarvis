# Visual & Production Notes: Design for the Long Game

## On-screen visuals (in order)
1. 0:00 — Title card "Principles 7-8"
2. 0:05 — Talking head
3. 0:25 — Timeline animation: field published → clients adopt → deprecation pain
4. 0:50 — Code: abstraction.graphql showing wrapper types
5. 1:15 — Talking head
6. 1:30 — Animation: small list growing into huge list, response time graph climbing
7. 1:50 — Code: pagination.graphql showing cursor-based pagination
8. 2:20 — Diagram: query cost calculation with vs without pagination
9. 2:50 — Talking head for summary

## B-roll / inserts
- Mobile app update prompt being dismissed (illustrating users not updating)
- Traffic light metaphor (brief, 2-3 seconds)

## Diagrams to create
- Timeline: field lifecycle from publication to permanent dependency
- Growth animation: list size vs response time correlation
- Query cost calculation: bounded (paginated) vs unbounded (unpaginated) side by side

## Code to show
- `abstraction.graphql`: Wrapper type hiding a third-party contract (highlight the abstraction layer)
- `pagination.graphql`: Cursor-based pagination pattern (highlight first/after arguments and defaults)
