# Security

One maintainer, no company, no paid support. What follows is what one person
can promise, and nothing more.

## Report

Use GitHub's private reporting on the repository concerned:

    https://github.com/openabstractions/<repository>/security/advisories/new

That page exists only while private reporting is switched on, and nothing
checks that yet. If it is missing, open a public issue saying only that you
have a report and want a private channel. Do not put the details in the issue.

Say which repository and version, what an attacker gains, and how to reproduce
it. A download spec, a job record or a wire fixture that triggers the fault is
worth more than a description: the conformance corpus is built from exactly
those, and a fix is not done until yours is in it.

## What happens next

- A person replies when the report has been read. There is no response-time
  commitment, because nobody is on call. Two weeks of silence means it was not
  seen; open the public issue above.
- A confirmed fault is fixed in every language that has it, the fixture goes
  into the corpus, and the fix ships as a bugfix release of the affected
  repositories with a GitHub advisory that credits you, unless you ask not to be.
- Disclose when you like. Ninety days after the report is the usual courtesy;
  it is a request, not a term.

## Scope

Every repository under `github.com/openabstractions` named `abstraction-*`,
`service-*`, `addon-*` or `adopter-*` — today `abstraction-config`,
`abstraction-download`, `abstraction-facade`, `abstraction-identity`,
`abstraction-job`, `abstraction-logging`, `abstraction-model`, `abstraction-router`,
`abstraction-storage`, `service-jobd`, `addon-synology`, `adopter-comfyui` —
and `polite-monitor`. `abstraction-watch`, `abstraction-rights`, `abstraction-asks`,
`abstraction-cas` and `abstraction-download-over-curl` join them at the release
that creates them; `scripts/split.manifest` already publishes all five. The JSON
reader, the caller-identity binding and the authorisation service are the parts
that most deserve a look.

Not in scope: `abstractions`, `research` and `.github`, which hold nothing
that runs; `appcontainer-notes`, which is private; forks of other projects,
which are reported upstream; and the platform facilities the code delegates
to (BITS, the OS keychain, a NAS, GitHub). Code that is not published is not
in scope until it is.

No audit has been done. The JSON reader has had one day of one person's
adversarial testing; nothing else has had any.

## Who ships it

Under the EU Cyber Resilience Act the manufacturer of a product containing this
code is whoever ships that product. This project publishes source under
Apache-2.0, is not monetised, and is not a steward in the Act's sense. What it
owes you — an address, a fix, an advisory — is above. Who stands behind it, and
what happens if they stop, is in `GOVERNANCE.md`.
