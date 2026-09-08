# Open Abstractions

**Common software capabilities. Language-native interfaces. More control over
how the work gets done.**

Open Abstractions builds interfaces, libraries and services for downloads,
background work, storage, logging and other capabilities applications repeatedly
implement for themselves. Applications can use these capabilities without being
tied to one implementation. The people running them gain more choice over where
work happens, what it may do, and how they observe it.

The same concepts have APIs that fit each language. Shared records, protocols
and behavioral contracts define what crosses the boundary: what a request means,
what a provider promises, and how it reports progress, completion or refusal.
The goal is common behavior, not identical-looking code in every language.

## Keep the engine. Adopt the interface.

A **provider** implements an interface. It can wrap a library an application
already uses, call an operating-system facility, or communicate with a service.
The interface is the agreement; the provider is how the work gets done.

That makes adoption incremental. Start with one capability, keep an existing
engine behind an adapter, or use one of our implementations. Applications do
not need to adopt the whole project or install a service to use a local binding.

Different providers can offer different guarantees. An in-process downloader
cannot continue after its process exits; a suitable service-backed provider
can. Those differences belong in declared capabilities, not surprises at the
call site.

## Services add capabilities, not prerequisites

Libraries make capabilities available inside an application. Services can
coordinate them beyond the application's lifetime: finishing background work,
sharing resources, applying policy and recording decisions for audit.

We build services and tools on the same contracts, rather than making the
contracts depend on our products. The broader aim is a machine whose work can
be inspected and controlled across applications, not a separate settings page
and private implementation in every program.

**Downloads are one working example.** The download layer supports resumable,
digest-verified transfers. With the appropriate provider configured, a
[supervisor](https://github.com/openabstractions/service-jobd) can finish the
work after the caller exits, or a
[Synology NAS](https://github.com/openabstractions/addon-synology) can perform
the transfer. The application asks for a download; the provider determines how
it is executed. [Delegation example and platform limits](https://github.com/openabstractions/abstractions/blob/main/docs/results/NAS1.txt).

## Choose a building block

| Capability | Start here |
|---|---|
| Download files, resume interrupted transfers and verify their contents | [Download](https://github.com/openabstractions/abstraction-download) |
| Track work, ownership, checkpoints and cancellation | [Job](https://github.com/openabstractions/abstraction-job) |
| Store bytes by content, or coordinate changes to a file | [Storage](https://github.com/openabstractions/abstraction-storage) / [Compare-and-set](https://github.com/openabstractions/abstraction-cas) |
| Record events and observe changes | [Logging](https://github.com/openabstractions/abstraction-logging) / [Watch](https://github.com/openabstractions/abstraction-watch) |
| Identify local callers, manage keep-awake permissions and ask users questions | [Identity](https://github.com/openabstractions/abstraction-identity) / [Rights](https://github.com/openabstractions/abstraction-rights) / [Asks](https://github.com/openabstractions/abstraction-asks) |
| Discover available bindings for jobs, downloads, storage and logging from Go | [Facade](https://github.com/openabstractions/abstraction-facade) |

Model naming and resolution live in
[Model](https://github.com/openabstractions/abstraction-model). The underlying
job, download and storage contracts are not specific to AI.

## What makes the interfaces interoperable

Contracts define the behavior. Implementations are exercised against shared
conformance cases, including failure and recovery, rather than being considered
compatible because their method names match. Public
[contracts](https://github.com/openabstractions/abstraction-job/blob/main/CONTRACT.md)
and [results](https://github.com/openabstractions/abstractions/tree/main/docs/results)
describe the agreements and the evidence behind them.

We are also developing a code generator for shared record definitions,
encoders, decoders and message envelopes. It does not generate execution engines
or connection management. The generator is not yet available as a standalone
public release.

**Apache-2.0. Experimental releases, starting with Go, Python and C++.**
Language coverage, provider capabilities and platform support vary by layer;
each repository documents its current status and installation route.

Start with a layer above to use or implement a capability. Read the
[project overview](https://github.com/openabstractions/abstractions) for the
architecture and [research](https://github.com/openabstractions/research) for
the prior art.

[Governance](https://github.com/openabstractions/.github/blob/main/GOVERNANCE.md)
and [security reporting](https://github.com/openabstractions/.github/blob/main/SECURITY.md).
