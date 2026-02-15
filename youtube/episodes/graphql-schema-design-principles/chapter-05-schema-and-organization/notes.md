# Visual & Production Notes: Schema & Organization

## On-screen visuals (in order)
1. 0:00 — Title card "Principles 9-10"
2. 0:05 — Talking head
3. 0:20 — Diagram: REST endpoint → GraphQL type 1:1 mapping (labeled "REST in a trench coat")
4. 0:45 — Code: abstraction-layer.graphql
5. 1:10 — Talking head
6. 1:25 — Diagram: single team → monolith vs multiple teams → federation, side by side
7. 1:55 — Code: federation.graphql showing subgraph examples
8. 2:30 — Diagram: three subgraphs flowing into gateway → unified schema
9. 2:55 — Talking head for restaurant analogy
10. 3:15 — Talking head for ownership summary

## B-roll / inserts
- Brief "trench coat" visual gag (optional, could be a simple illustration)
- Restaurant menu analogy visual (multiple kitchen menus combining into one customer menu)

## Diagrams to create
- REST-to-GraphQL 1:1 mapping (looks bad, mechanical, labeled negatively)
- Org structure comparison: single team with monolith vs multi-team with federation
- **Key diagram**: Federation architecture — three subgraphs (Products, Reviews, Inventory) flowing through a router into one client-facing schema. Animate: build each subgraph one at a time, then show them combining.
- Restaurant analogy: multiple kitchens → one host → one menu for customer

## Code to show
- `abstraction-layer.graphql`: Proper abstraction hiding backend details (highlight the separation)
- `federation.graphql`: Three subgraphs extending the same entity (highlight @key and entity extensions)
