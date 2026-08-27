# LANGA

**16 digital services across 5 networks, in production, on our own infrastructure.**

Day-to-day operations are handled by AI agents working under a written method. Not as an
experiment: it is the thing that keeps the services open.

Origins in 2009. First company in 2015. LANGA Corporation S.r.l. since 2019.
Milan and Alba, Italy.

---

## What we run

Five networks, each one a catalogue that packages a capability and sells it to a different
buyer. Underneath them, a single set of engines: identity, commerce, governance, monitoring,
transactional email. An engine is written once and configured per vertical, never
reimplemented.

Internal services authenticate with a shared secret and pay nothing. External clients use an
API key with a tier. Same route, different door.

---

## How it is run

A written rulebook, a shared event log, and roles with explicit permissions. Every decision,
every doubt, and every defect is recorded as it happens, by whoever finds it.

The interesting part is not that agents write code. It is what happens when there are enough
of them that no single person can hold the state in their head.

---

## What we learned the expensive way

**Most of what breaks is not missing. It is present, plausible, and wrong.**
Absence is easy: something is empty, and you see it. The costly failures pass every
completeness check because nothing is empty. They are simply not what the field claims.

**A guard that was never exercised in the direction where it must fail is not a guard.**
Run it twice. It must fire on the live defect, and it must stay silent on a correct case.
Tested once, a guard that always passes is indistinguishable from one that works.

**An empty field is visible. A full and false one is not.**
A column filled on 89 rows out of 89, where 86 hold the wrong thing, passes validation,
passes review, and passes the eye. Nothing flags it.

**Every measurement declares its coverage.**
Not how many rows you checked, but out of how many possible, and the date of the most
recent. A check that examined 2 items out of 49 and found nothing is not green. It is a
check that does not know.

**An owner without a door is not an owner.**
Assigning work to a role nobody can reach is not assigning it. The record looks complete,
the address does not deliver, and no query will ever tell you.

**Whoever produces does not verify.**
Installing is a technical act. Verifying is a judgement, and only the second one needs to be
independent.

---

## Areas of work

**Multi-agent operations.** Roles, permissions, shared memory, decision records, and the
failure log that comes with running agents at scale.

**Service infrastructure.** Single sign-on, monitoring, payment gateway, transactional email,
all centralised and consumed through catalogues.

**Commerce and marketplaces.** Multi-brand storefronts running on shared engines, configured
per sector rather than rebuilt.

**Tools for small businesses.** The part that would not exist if we did not build it.

---

## What we publish

We publish method before machinery. The rules that govern how our agents work are useful to
anyone running more than a handful of them. Our infrastructure is not, and it stays closed.

Repositories here are documentation and small, self-contained tools. They are maintained or
they are archived. We would rather have one repository that is current than ten that are not.

---

## Tools you can use today

Three small tools, each one born from a defect we measured on our own estate and could not
find an existing answer for. No dependencies beyond the standard library. MIT.

**[realroute](https://github.com/langacorp/realroute)** — checks that a route really exists,
by content and not by status code. Born from a site that answered `200` to every URL,
including one that could not exist, so a status-code check reported it green without having
looked at anything.

**[leakform](https://github.com/langacorp/leakform)** — finds secrets in a git repository by
shape rather than by field name, across every ref rather than the working tree. Born from a
repository searched for the first time five years after its last commit: the values had been
readable the whole time, and nothing said nobody had looked.

**[samecheck](https://github.com/langacorp/samecheck)** — measures whether the copies that
should be identical still are, and never says which one is right. Born from one file living
in 29 copies, in 4 distinct versions, under 3 different naming conventions.

Each one declares its coverage on every run — how much it examined out of how much exists,
and what it skipped and why — and each ships a self-test that must fire in one direction and
stay silent in the other. A run that examined nothing never exits as a pass.

---

[langa.tv](https://langa.tv) · support@langa.tv
