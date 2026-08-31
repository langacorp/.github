# LANGA

**Humans decide. AEGIS is the shield they wield.**

Anyone can call a model. What is hard is running a hundred of them against a
real estate of services and still knowing, a month later, who decided what, on
what evidence, and what it cost.

**AEGIS** is that shield: shared memory, explicit permissions per role, every
decision and every doubt written down at the moment it happens.
Three creatures are its **minds** — **Talos** builds, **Daedalus** reorders,
**Argus** watches. The **hands** hold it, and there are as many as needed.
The **eyes** never sleep.
The hands and the eyes are at work today; the minds are being built, Talos first.

On top of that: an ecosystem of **digital services and marketplaces**, in
production, on our own infrastructure. The current count is on
[langa.tv](https://langa.tv) — it is not written here, because it changes.

Origins in 2009. First company in 2015. LANGA Corporation S.r.l. since 2019.
Offices in Milan, Alba, Brescia and Cuneo, Italy.

The company is people: a team, and developers who have built with us over the
years. Some of them are credited by name in the repositories below.

---

## How we work

A written rulebook, a shared event log, and roles with explicit permissions. Every decision,
every doubt and every defect is recorded by whoever finds it, at the moment they find it —
not summarised afterwards by whoever is left.

Humans decide; the hands carry a large share of the day-to-day work under that rulebook.
The rulebook exists because they need it, and so do we — it is what keeps the two kinds of
work legible to each other.

That is the part worth describing, and it is less impressive than it sounds. It exists
because we kept losing things: a decision nobody could reconstruct, a doubt that never
reached anyone, a defect found twice by two different people who each thought they were
first. Writing it down as it happens is cheaper than any of those.

The rules are not aspirational. Each one has an outcome — it passes or it does not — and a
consequence when it does not. A rule without a consequence gets read once and then quietly
stops being followed.

### What runs it

**AEGIS** also carries the engines the services share: identity, payments,
governance, intelligence, sync. It is not a product and is not sold directly —
capabilities reach customers through the networks.

**Talos** will execute the part that needs no person in front of it. Most of the
work is not autonomous, and the split is counted rather than claimed: we would
rather publish a smaller number that is measured.

The hands themselves are visible while they work, with the numbers read live
and the gaps named where a number cannot be read yet:
**[aegis.langa.tv/status](https://aegis.langa.tv/status)**

---

## What we publish, and why

**We open how we work, never what we sell.** The method is useful to anyone running more
than a handful of hands. Our service infrastructure is not, and it stays closed.

The tools here were not written to be published. Each one came out of a defect we hit on our
own estate, and each one is still in use here every day. That is the only reason they stay
current: a tool that its authors do not run stops matching reality within a few months, and
nothing announces the moment it does.

We would rather have one repository that is current than ten that are not.

---

## Tools you can use today

Small tools, each one born from a defect we measured on our own estate and could not
find an existing answer for. Each ships a self-test that runs on every push. MIT.

**[realroute](https://github.com/langacorp/realroute)** — checks that a route really exists,
by content and not by status code. Born from a site that answered `200` to every URL,
including one that could not exist, so a status-code check reported it green without having
looked at anything.

**[leakform](https://github.com/langacorp/leakform)** — finds secrets in a git repository by
shape rather than by field name, across every ref rather than the working tree. Born from a
repository searched for the first time five years after its last commit: the values had been
readable the whole time, and nothing said nobody had looked. Ships a pre-commit hook that
catches a secret one second before it is committed, which is the only second that matters.

**[samecheck](https://github.com/langacorp/samecheck)** — measures whether the copies that
should be identical still are, and never says which one is right. Born from one file living
in many copies, in several distinct versions, under three different naming conventions.

**[provenreal](https://github.com/langacorp/provenreal)** — compares what a system claims
with what can be measured, from independent sources. It answers two questions rather than
one: how many, and of what. Born from five public pages giving five different answers about
the same thing, none of them wrong in isolation.

**[countdrift](https://github.com/langacorp/countdrift)** — finds numbers written by hand
that no longer match their source. Born from a line in our own rulebook reading *"AI agents
in production (32 total)"* while the registry returned a different number, and from there it
had spread into published articles and into a panel's markup.

**[kemproof](https://github.com/langacorp/kemproof)** — attests that an ML-KEM-768 key
exchange really happened, and records it with an expiry. It does not encrypt anything, and
its README says so before it says anything else. Born from our own pages promising
*encryption* where the code performed a *key exchange* — two different promises.

## What they have in common

**Every run declares its coverage** — how much was examined out of how much exists, and what
was skipped and why. Not how many things you checked, but out of how many possible. A check
that examined two items out of forty-nine and found nothing is not green; it is a check that
does not know.

**A run that examined nothing never exits as a pass.** The absence of a finding and the
absence of a search look identical from the outside. Each tool exits non-zero when it looked
at nothing, and says so in words.

**Each one ships a self-test that must fire in one direction and stay silent in the other.**
A guard exercised only where it passes is indistinguishable from one that always passes.

---

[langa.tv](https://langa.tv) · support@langa.tv

Maintained by [Luca PRATA](https://github.com/LucaPRATA), founder, and the LANGA Technician team — LANGA Corporation S.r.l., Milan, Italy.
