# Chapter: Hook

**Duration**: ~45 seconds
**Visual mode**: mixed

---

[DIAGRAM: A GraphQL schema that's clearly just a mirror of database tables — columns become fields, table names become types, foreign keys become connections. Looks mechanical, auto-generated.]

You've got your database. You run some codegen tool. Out comes a GraphQL schema. Ship it.

And six months later, your frontend team hates you. Every query needs three round trips. Nobody can figure out which type to use. And you can't change anything without breaking the mobile app that hasn't been updated since launch.

[CUT TO: talking head]

I've worked with teams at eBay, SoundCloud, Paramount, Shutterstock — companies running GraphQL at serious scale. And the number one mistake I see? Designing schemas around your backend instead of your clients.

Today I'm walking you through 10 principles that fix this. These aren't theoretical — they come from real production systems serving millions of requests.

[VISUAL: Quick flash of all 10 principle names appearing on screen, then fading]

And principle number six? That one would've saved me from a production outage. More on that in a minute.
