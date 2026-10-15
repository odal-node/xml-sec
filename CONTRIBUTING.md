# Contributing

**This is a fork. It is not the home of this project.**

`xml-sec` is written and maintained by [@polaz](https://github.com/polaz) at
[Structured World](https://github.com/structured-world), and published under Apache-2.0.
The upstream repository is:

**https://github.com/structured-world/xml-sec**

## Send your contribution there, not here

Open issues and pull requests against upstream. A fix merged here reaches nobody:
this fork exists for one reason and is not released, not published to crates.io, and
not maintained as a separate project.

If you arrived here from a search result or a dependency graph, upstream is where the
code lives, where releases are cut, and where the maintainer will see you.

## Why this fork exists

It carries **one commit** on the branch `odal/raise-node-set-ceiling`:
`raise NODE_SET_ENTRY_CEILING so EU trusted lists verify`.

The published crate caps XMLDSig node-sets at 65536 entries. Several EU Member State
trusted lists have grown past that ceiling — by single digits — so verifying them
against the released crate fails on documents that are perfectly valid.

That is reported upstream as
[structured-world/xml-sec#158](https://github.com/structured-world/xml-sec/issues/158).
**When it ships, this fork should be deleted and the consumer repointed at the released
crate.** The branch is the whole purpose; `main` is an unmodified mirror of upstream.

## Before deleting this repository

It is load-bearing. A consumer pins the fork by commit SHA, so removing this repository
— or the `odal/raise-node-set-ceiling` branch — breaks that build. Repoint the consumer
first, confirm it builds, and only then delete.

## Conduct and security

Both belong upstream. Report a vulnerability in this code to the upstream maintainer,
following whatever policy the upstream repository publishes — not to us. We did not
write it and cannot patch it for anyone but ourselves.

If you believe our one patch is itself the problem, that is ours: say so on
[#158](https://github.com/structured-world/xml-sec/issues/158) and we will see it.
