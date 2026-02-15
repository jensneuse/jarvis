# Chapter: Design for the Long Game

**Duration**: ~3.5 minutes
**Visual mode**: mixed

---

[VISUAL: Title card — "Principles 7-8: Designing for Longevity"]

[CUT TO: talking head]

Principle seven is one of those things that sounds obvious until you ignore it and pay the price. Assume every field you publish is permanent.

The moment you ship a GraphQL field, some client will start using it. And if that client is a mobile app? Good luck getting users to update. There are iOS apps in production right now querying fields that were "temporary" three years ago.

[VISUAL: Timeline graphic showing a field being published, then clients depending on it, then the painful deprecation process stretching months/years into the future]

So what do you do? First, never expose third-party contracts directly. If you're wrapping a Stripe API or a shipping provider, abstract it behind your own types.

[CODE: abstraction.graphql]

Look at this. Instead of exposing Stripe's payment object directly, you create your own `PaymentInfo` type. Now when you switch from Stripe to a different provider next year, your clients don't notice. They're talking to *your* schema, not Stripe's.

[CUT TO: talking head]

Principle eight: always paginate. Always. Even if the list is small today.

[VISUAL: Small list growing into a massive list, response times climbing on a graph next to it]

I've seen this so many times. "Oh, users only have a few orders." Fast forward two years, you've got power users with thousands of orders, your queries are timing out, and you can't add pagination without breaking every client.

[CODE: pagination.graphql]

Use simple cursor-based pagination. `first` and `after` arguments with sensible defaults. It's not much code.

But here's the real reason this matters beyond performance. If you paginate, your security team can calculate query cost. They can enforce rate limits. Without pagination, a single query could pull your entire database.

[DIAGRAM: Query cost calculation. A query requesting `users(first: 10)` with `orders(first: 5)` each — total cost: 10 + (10 * 5) = 60 units. Compared to unpaginated: `users` with `orders` — cost: ??? (unbounded)]

Think of pagination like a traffic light. It controls how much data flows through per request. Without it, you've got an open highway with no speed limits — it works fine until it suddenly doesn't.

[CUT TO: talking head]

These two principles share a theme: you're designing for a future you can't predict. Abstract third-party dependencies. Paginate everything. Your future self will thank you.
