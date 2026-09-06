# Governance

## Who decides

One maintainer: Reinis Lusis ([@ReinisLusis](https://github.com/ReinisLusis)),
who has shipped iOS and Android SDKs in Kotlin, Java and C++ that other
companies integrate against. Two owners of the `openabstractions` GitHub
organisation as of 2026-09-07. There is no company, no foundation, no board,
and nothing is sold under the project's name.

## How a contract changes

A contract is a layer's normative page and the conformance corpus beside it
(`testdata/` in each layer). Every implementation of the layer must produce
the same bytes on that corpus, and `scripts/check.sh` runs the comparison.

- A new obligation lands as a scenario in the corpus before any
  implementation. If the scenario cannot be written, the obligation is not
  imposed (`METHOD.md` §8).
- A rule no scenario can fail is deleted, not weakened.
- A change that turns an existing scenario red is a contract change, not a
  fix, and is announced as one.
- Decisions are written down, dated, and reopened only by an external event of
  landscape-changing size: a platform vendor shipping the thing, a law, an
  adopter demanding it. Rejected decisions stay visible, struck out, so nobody
  rebuilds them. That record is private today; the corpus that enforces it is
  public.

Proposals are pull requests carrying the scenario. The maintainer merges.

## If the maintainer stops

None of this needs permission:

- The licence is Apache-2.0, perpetual and irrevocable (its §2). Nothing can
  be withdrawn from you.
- The name is not a registered trademark. Nobody holds one, and nothing here
  forbids a fork keeping it.
- The corpus is public. A fork that stays green against it is a conforming
  implementation whoever maintains it; a fork that changes the corpus is a new
  contract and should say so.
- No signing key, service, domain or account stands between you and building
  what is published. There is no domain.

If a report sent the way `SECURITY.md` describes draws no reply from a person
for ninety days, treat the organisation as unmaintained, fork, and say publicly
that you have. Until a second owner exists that is the whole succession plan,
and it is written here so nobody has to guess.
