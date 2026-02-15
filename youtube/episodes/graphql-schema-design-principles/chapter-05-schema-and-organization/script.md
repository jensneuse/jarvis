# Chapter: Match Your Schema to Your Organization

**Duration**: ~3.5 minutes
**Visual mode**: mixed

---

[VISUAL: Title card — "Principles 9-10: Architecture & Organization"]

[CUT TO: talking head]

Principle nine: abstract your implementation details. This is where I see the most damage, and it's usually the easiest mistake to make.

You've got a REST API. You point a codegen tool at it. Out comes a GraphQL schema that's just your REST endpoints with GraphQL syntax. Congratulations — you've built a worse REST API.

[DIAGRAM: REST endpoint `/api/v2/users/{id}/profile` becomes GraphQL type with the same structure. Label: "This is not a GraphQL API. This is REST in a trench coat."]

The whole point of GraphQL is that the schema is a *contract* between you and your clients. It should describe what clients can do, not how your backend is wired.

[CODE: abstraction-layer.graphql]

When you abstract properly, you can completely rewrite your backend — swap databases, refactor services, migrate from REST to gRPC internally — and your clients don't know or care. The schema didn't change. That's the power of a good abstraction layer.

[CUT TO: talking head]

And finally, principle ten: match your schema architecture to your organizational structure. This is Conway's Law applied to GraphQL.

[DIAGRAM: Two organizational structures side by side. Left: single team → monolithic schema. Right: multiple teams → federated subgraphs. Each team owns a subgraph and deploys independently.]

If you're one team? Keep it simple. One schema, one service. Don't introduce federation because it sounds cool. It's overhead you don't need.

But if you've got multiple teams? Federation makes sense. Each team owns their subgraph. They define their types. They deploy independently. No more waiting for the "schema team" to approve your changes.

[CODE: federation.graphql]

Here's what that looks like. The products team owns the `Product` type. The reviews team extends it with `reviews`. The inventory team extends it with `availability`. Each team ships on their own schedule.

[DIAGRAM: Three subgraphs flowing into a router/gateway, which presents one unified schema to clients. Labels on each subgraph: "Products team", "Reviews team", "Inventory team".]

Think of it like this. Instead of one massive restaurant menu managed by a committee, each kitchen publishes its own menu, and the host combines them for the customer. The customer sees one menu. But behind the scenes, each kitchen operates independently.

[CUT TO: talking head]

The key insight is this: your schema architecture should make ownership clear. If you can't point at a type and say "that team owns it," you've got a governance problem.
