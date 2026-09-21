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

This policy covers original OpenAbstractions code published under
`github.com/openabstractions`: capability libraries, runtime services, providers,
adapters, tools and installers.

The capability repositories are `abstraction-asks`, `abstraction-cas`,
`abstraction-config`, `abstraction-credentials`, `abstraction-download`,
`abstraction-facade`, `abstraction-identity`, `abstraction-inference`,
`abstraction-job`, `abstraction-logging`, `abstraction-model`,
`abstraction-rights`, `abstraction-router`, `abstraction-storage` and
`abstraction-watch`. Delivery and integration code includes
`abstraction-download-over-curl`, `addon-synology`, `adopter-comfyui`,
`docker-jobd`, `polite-monitor`, `redist` and the legacy `service-jobd`.
Runtime, control-panel, gateway and example code in `abstractions` is covered too.

For a fault in an upstream project or a platform facility, use that project's
reporting channel. Report defects in OA's integration or authority boundaries
here. Research documents and organization metadata do not provide running
implementations.

The caller-identity binding, authorization, credential handling and generated
readers are useful areas to examine. Published coverage and release notes name
the checks performed and their limits. Passing tests do not establish a complete
security audit.

## Who ships it

Under the EU Cyber Resilience Act the manufacturer of a product containing this
code is whoever ships that product. This project publishes source under
Apache-2.0, is not monetised, and is not a steward in the Act's sense. What it
owes you — an address, a fix, an advisory — is above. Who stands behind it, and
what happens if they stop, is in `GOVERNANCE.md`.
