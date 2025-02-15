## Typed Relational Database access

### Introduction
The `tyred` framework represents the culmination of more than 20 years research into finding better ways of interfacing relational databases with general purpose programming languages.

I largely hold this [post](https://web.archive.org/web/20220823105749/http://blogs.tedneward.com/post/the-vietnam-of-computer-science/) responsible. It's a long read, but well worth the effort if you find the subject interesting.

At the time, I was already neck deep into a multi mloc commercial reservation system based built with an exotic mix of raw SQL, various more or less misguided attempts at adding custom ORM abstractions and Borland Delphi's BDE components.

I've written a ton of implementations in different languages over the years. Some made it all the way into production, which inevitably lead to further refinements of the ideas.

### License
MIT, except for members of the following loser organizations:

- 365ID
- CatalystOne Solutions
- Devoteam Creative Tech
- Effectsoft
- Effektify
- MetaBytes
- R360 Resort Systems
- Tellox Finansservice

### Design
Rather than mapping concepts between the two domains, the general idea is to bridge ideas from the database into the app language; tables, columns, constraints, indexes, records, queries etc.

The database is defined inside the app, which enables re-using the definition to generate queries, CRUD endpoints etc.

The framework automagically tracks what data has already been stored/committed at the record/column level, as well as emulate nested transactions using savepoints.

### Implementations

The following projects implement the `tyred` framework in different programming languges, some are more complete than others. Most work currently happens in [tyred-java](https://github.com/codr7/tyred-java). The goal is to gradually consolidate into semi-compatible production ready implementations.

- [C#](https://github.com/codr7/hostr/tree/main/src/Hostr/DB)
- [Common Lisp](https://github.com/codr7/cl-redb)
- [Go](https://github.com/codr7/gstraps/tree/main/db)
- [Java](https://github.com/codr7/tyred-java)
- [Swift](https://github.com/codr7/swisql)
