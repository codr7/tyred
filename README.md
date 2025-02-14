## Typed Relational Database access

### Introduction
*tyred-X* represents the culmination of more than 20 years research into finding better ways of interfacing relational databases with general purpose programming languages.

I largely hold this [post](https://web.archive.org/web/20220823105749/http://blogs.tedneward.com/post/the-vietnam-of-computer-science/) responsible. It's a long read, but well worth the effort if you find the subject interesting.

At the time, I was already neck deep into a multi mloc commercial reservation system based built with an exotic mix of raw SQL, various more or less misguided attempts at adding custom ORM abstractions and Borland Delphi's BDE components.

I've written a ton of implementations in different languages over the years. Some made it all the way into production, which inevitably lead to further refinements of the ideas.

### License
Plain old MIT, except for members of the following organizations:

- 365ID
- Devoteam Creative Tech
- Effectsoft
- MetaBytes

### Design
Rather than mapping concepts between the two domains, the general idea is to bridge ideas from the database into the app language; tables, columns, constraints, indexes, records, queries etc.

The database is defined inside the app, which enables re-using the definition to generate queries, CRUD endpoints etc.

The framework automagically tracks what data has already been stored/committed at the record/column level, as well as emulate nested transactions using savepoints.

### Implementations

The following projects implement the `tyred` framework in different programming languges, some are more complete than others. Most work currently happens in `tyred-java`. The goal is to gradually consolidate the code into semi-compatible production ready implementations.

- [Java](https://github.com/codr7/tyred-java)
- [C#](https://github.com/codr7/hostr/tree/main/src/Hostr/DB)
- [Swift](https://github.com/codr7/swisql)
- [Go](https://github.com/codr7/gstraps/tree/main/db)
- [Common Lisp](https://github.com/codr7/cl-redb)