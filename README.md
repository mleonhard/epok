# Epoks

A proposal for universal version numbers, incremented quarterly, to help reduce technical debt.

2020-05-14 v0.1 Michael Leonhard ([mleonhard](https://github.com/mleonhard))


# Devkwik and Kotar
People change software to make it more useful.  The people who change a particular piece of software are called its owners.

Owners make various kinds of changes:
- Adding features
- Fixing bugs
- Adding support for platforms
- Improving performance
- Removing features
- Removing support for platforms
- *Devkwik*, improving the structure of the software so owners can make future changes more quickly

We need this new word '*devkwik*' because existing words are cumbersome or inexact:
- remove technical debt
- cleanup
- refactor
- simplify

The term 'technical debt' is particularly cumbersome to say and write.  It evokes financial ideas which are not applicable to software.  Technical debt slows down development.  This is its most important property.  We will call it '*kotar*' from 'code' and 'tar'.

Tar is a thick sticky substance.  A machine covered in tar will not work well.  A person who wants to fix or modify the machine must first remove some of the tar.  Tar smells bad.  Tar is very stable and does not go away by itself.

Unused software components are kotar.  Unnecessarily complicated structures are kotar.  Useless bureaucracy is kotar.  Manual processes that slow down changing the software are kotar.

Example uses of 'kotar' and 'devkwik':
- "To speed up our release velocity, let's change our time allocation to 80% features and 20% devkwik."
- "I will accept this project only if you let me first spend three months removing the kotar and adding tests."
- "Our team uses Kwikjile, with a three-to-one feature-devkwik ratio.  Our median *devocity* is 9 changes per week."
- "My company is driven by the sales team.  None of the leaders understand kotar.  Are you hiring?"
- "Code review comment: How about devkwiking this module a bit before adding the new functions?"
- "Change description: Devkwik the RPC method classes (1 of 4): Remove inheritance by changing RpcMethod from an abstract class to an interface.  Move helper functions to Helpers class."
- "// TODO(mleonhard) Find out if this is really kotar."


# Motivation

Every software project uses modules from different owners.  Module owners can add features easily.  Before removing features, they must get all owners to change their software to stop using the features.  Getting other people to do work is difficult and often impossible.  This is why modules kotar quickly.

Module kotar has devastating effects on security, privacy, and velocity.

Examples of module kotar:
- text encodings besides UTF-8
- [java Collections API](https://docs.oracle.com/en/java/javase/14/docs/api/java.base/java/util/Collections.html)
- `null`
- [posix file api](https://danluu.com/deconstruct-files/)
- Perl for non-one-liners
- Internet Explorer
- Old Android APIs
- Win32 API
- SSL and old TLS versions
- MD5
- DES

This document addresses the problem of module kotar by helping module owners remove features quickly.


# Epok Number

An epok is a quarter, three months of time.

Epoks are numbered.  Epok one (e1) starts at 2020-07-01T00:00:00Z; e2 starts on 2020-07-10; and so on.  Epok zero (e0) is all the time before e1.

'*enow*' is the current epok.

'*enext*' is the epok after the current one.

'*eold*' is the epok before the current one.

Epoked software must:
- include an epok number in every source file, compiled binary, API, file, and network message.
- support the current epok and the previous one

Epoked modules must support deprecated functions for at least one epok.  This gives software owners time to update their software to stop using the function.


# Make Devkwik Easier

When a module owner releases a new version of a module with a function removed, they must tell others which function to use instead, and how to switch to it.  They can publish a migration script that automatically changes code to use the new function.

Software owners can use tools to automatically:
1. download migration scripts
1. prepare branches with the migrations applied and ready for review
1. create a work item for each migration
1. assign the work items to appropriate team members based on change history


# Migration Script Format


# Publishing Migration Scripts


# Migration Tools


# Rosy Future

Eventually, all aspects of software will be epoked:
- Languages - We can finally remove `null`.
- Core libraries - We can make collections immutable by default.
- Internet protocols - We can remove insecure features.
- Wifi protocols - This could bring a seachange in IoT security.
- Commercial APIs - Reduced cost of innovation
