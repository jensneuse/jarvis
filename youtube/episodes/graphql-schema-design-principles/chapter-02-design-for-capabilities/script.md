# Chapter: Design for Capabilities, Not Data

**Duration**: ~3 minutes
**Visual mode**: mixed

---

[VISUAL: Title card — "Principles 1-3: Design for Capabilities"]

Let's start with the foundation. Principle one: capability-based design.

[CUT TO: talking head]

Before you write a single line of schema, ask yourself: what does the client need to accomplish? Not "what data do I have" — what can the user *do*?

[DIAGRAM: Left side shows a database with Users, Orders, Products tables. Right side shows client workflows: "Browse catalog", "Check order status", "Manage profile". Arrow from right to left, labeled "Design direction".]

You document use cases. You map out workflows. You cluster those into subdomains. And *then* you design your types and fields.

Think of it like building a restaurant. You don't start with the kitchen equipment and then figure out the menu. You start with what your customers want to eat, and you build the kitchen around that.

[CUT TO: talking head]

This leads directly into principle two: client-centric design. Structure your schema around how clients *traverse* data, not how you store it.

[CODE: client-centric.graphql]

Here's what I mean. Instead of making the client fetch a user, then separately fetch their orders, then separately fetch order items — you let them walk the graph. User, dot orders, dot items. One query. That's the whole point of GraphQL, and yet so many schemas break this by modeling around their microservices instead of the client experience.

[CUT TO: talking head]

Now, principle three might surprise you: purposeful duplication is okay.

[CODE: purposeful-duplication.graphql]

Look at this. You have a `Viewer` type for the logged-in user. A `UserProfile` type for viewing someone else's profile. A `TeamMember` type for team contexts. They share some fields, sure. But they're conceptually different things.

[DIAGRAM: Three boxes labeled Viewer, UserProfile, TeamMember. Each has some shared fields (name, avatar) and unique fields. Highlighted text: "Same data, different contexts".]

Don't collapse these into one `User` type with a bunch of nullable fields that only apply sometimes. That's confusing for every client developer who touches your API. Separate types make it obvious which fields exist in which context.

When you're designing for clients and you see the same entity appearing in different workflows with different needs — duplicate the type. Your schema gets clearer, not messier.
