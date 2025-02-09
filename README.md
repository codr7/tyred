# Typed Relational Database access

## Introduction
*tyred-X* represents the culmination of 26 years of research into finding better ways of interfacing relational databases with general purpose programming languages.

I largely hold this [post](https://web.archive.org/web/20220823105749/http://blogs.tedneward.com/post/the-vietnam-of-computer-science/) responsible. It's a long read, but well worth the effort if you find the subject interesting.

At the time when I first read it, I was already neck deep into a multi mloc commercial reservation system based built on top of an exotic combination of raw SQL, various more or less misguided attempts at adding custom ORM abstractions and Borland Delphi's BDE components.

I have written a ton of implementations in different languages over the years. Some made it all the way into production, which inevitably lead to further refinements of the ideas.

## Design
Rather than mapping concepts between the two domains, the general idea is to bridge ideas from the database into the programming language; tables, columns, constraints, indexes, records, queries etc.

The database is defined in the programming language, where the definition can be used to simplify application code. Once the relations between tables have been defined, there's no need to keep repeating them in code; which allows moving faster when making changes, especially early in the application life cycle.

The framework is transaction aware, and keeps track of what data has been committed. Additionally it emulates nested transactions using savepoints.

Queries may be composed using existing database definitions combined with raw SQL if needed.

## Implementations

The following projects aim to implement the `tyred` framework in different programming languges. Some are more complete than others. Most work currently happens in `tyred-java`, but the goal is to gradually consolidate into similar production ready implementations in (at least) the listed languages.

- [Java](https://github.com/codr7/tyred-java)
- [C#](https://github.com/codr7/hostr/tree/main/src/Hostr/DB)
- [Swift](https://github.com/codr7/swisql)
- [Go](https://github.com/codr7/gstraps/tree/main/db)
- [Common Lisp](https://github.com/codr7/cl-redb)