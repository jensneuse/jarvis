# Chapter: Handle Errors and Nullability Like a Pro

**Duration**: ~4 minutes
**Visual mode**: mixed

---

[VISUAL: Title card — "Principles 4-6: Errors & Nullability"]

Okay, this is where most schemas silently become a nightmare. Principles four through six are all about how your schema communicates failure.

[CUT TO: talking head]

Principle four: make expected errors explicit.

Here's what most people do. A mutation fails, and you get back a generic error in the `errors` array. The client has to parse an error message string to figure out what happened. That's fragile, and it's lazy.

[CODE: explicit-errors.graphql]

Instead, use union types to model every possible outcome. Your `createOrder` mutation returns a union — it's either an `Order`, or an `OutOfStockError`, or an `InvalidAddressError`. The client gets type-safe handling. No string parsing. No guessing.

[DIAGRAM: Two flows side by side. Left: "Generic error" flow with question marks at each step. Right: "Typed result" flow with clear branches for success/failure.]

This is such a simple change and it completely transforms the client developer experience.

[CUT TO: talking head]

Principle five: distinguish your nullability states. This is subtle but important.

There are three different reasons a field can be null. The data genuinely doesn't exist. The value is intentionally null. Or something broke and you got null as a side effect of an error.

[CODE: nullability.graphql]

The `@semanticNonNull` directive helps here. It tells clients: "This field should always have a value. If it's null, something went wrong." That's different from a field like `bio` where null just means the user hasn't written one yet.

[CUT TO: talking head]

And now — principle six. The one I said would've saved me from a production outage.

[VISUAL: Red warning banner — "Null Blast Radius"]

Null blast radius. Here's the problem. In GraphQL, if a non-nullable field fails to resolve, the error doesn't just affect that field. It propagates up to the nearest nullable parent. And if that parent is also non-nullable, it keeps going. It can wipe out entire sections of your response.

[DIAGRAM: Animated tree diagram. A field deep in the tree fails. The red "null" propagates up through non-nullable parents, wiping out larger and larger portions of the response, until it hits a nullable field and stops.]

Imagine you mark `user.email` as non-null. The email service goes down. Now `email` is null — but it's non-nullable, so the error propagates up. Now `user` is null. If `user` is non-nullable on the query, the *entire query* fails. All because of one email field.

[CUT TO: talking head]

The rule is simple. Only mark a field non-nullable when you're absolutely certain the data will always be there. When in doubt, make it nullable. You're containing the blast radius of failures.

Think of it like bulkheads on a ship. If one compartment floods, the bulkheads stop the water from sinking the whole ship. Nullable fields are your bulkheads.
