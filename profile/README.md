# OpenAbstractions

**Applications ask for work. People choose what does it.**

OpenAbstractions helps an application keep a download running, call a model,
read shared content, use a named credential, ask a person for a decision, or
find a supported application that is already open. The application gets one API
for each kind of work and clear outcomes when the work is unavailable or
refused.

A local runtime chooses an allowed service that meets the request. That service
keeps shared state, credentials and recovery data. The application does not need
the provider's private files, API key or vendor protocol.

```text
application -> resolve capability -> typed client -> OA service -> provider
```

Providers can wrap an existing engine, an operating-system facility, a resident
runtime or a remote service. The capability contract keeps the behavior and
typed outcomes stable across those implementations.

An operator can connect an existing downloader, model engine or remote service.
Future work can move to another provider while accepted work finishes with the
provider that took it.

An assistant can find and open a supported editor, propose a change to the
current document or workflow, and let that application show the preview and ask
the person to apply it. Instance, context and revision checks keep the proposal
attached to the item the person actually saw.

## Available now: 0.2.0

[Download 0.2.0](https://github.com/openabstractions/redist/releases/tag/v0.2.0) for Windows, Linux and macOS.
Use one runtime to keep accepted work running, call AI providers with named
credentials, manage application permissions, and find or activate registered
applications. Windows includes the Panel for inspecting and managing the runtime.
The SDK sources cover Go, C++17, Python, Rust and JavaScript; package versions
and registry availability are documented separately by each capability.

Windows x64 installation, upgrades, rollback and crash recovery passed.
Linux amd64 installation and runtime-backed downloading passed. The macOS
package is signed and notarised; protected service calls retain the documented
caller-identity limitation. Windows and Linux packages are unsigned.
[Release verification and limits](https://github.com/openabstractions/abstractions/blob/main/docs/results/release-0.2.0.md).

## Start as an application developer

Use the [facade](https://github.com/openabstractions/abstraction-facade) to
resolve only the capabilities your application needs. Go, C++17, Python, Rust
and JavaScript clients share generated contracts and native IPC. Package and
platform coverage varies by capability; each README names its tested path and
current limits.

Choose a capability:

| Need | Repository |
| --- | --- |
| Find and bind services | [Facade](https://github.com/openabstractions/abstraction-facade) |
| Durable work and recovery | [Job](https://github.com/openabstractions/abstraction-job) |
| Durable downloads | [Download](https://github.com/openabstractions/abstraction-download) |
| Chat, embeddings, audio, images, video and live voice | [Inference](https://github.com/openabstractions/abstraction-inference) |
| Named service-applied secrets | [Credentials](https://github.com/openabstractions/abstraction-credentials) |
| Authorized content by digest | [Storage](https://github.com/openabstractions/abstraction-storage) |
| Configuration and provenance | [Config](https://github.com/openabstractions/abstraction-config) |
| Exact action/resource policy | [Rights](https://github.com/openabstractions/abstraction-rights) |
| Questions requiring a person | [Asks](https://github.com/openabstractions/abstraction-asks) |
| Structured events | [Logging](https://github.com/openabstractions/abstraction-logging) |
| Model names and locations | [Model](https://github.com/openabstractions/abstraction-model) / [Router](https://github.com/openabstractions/abstraction-router) |
| Atomic named state and change observation | [Compare-and-set](https://github.com/openabstractions/abstraction-cas) / [Watch](https://github.com/openabstractions/abstraction-watch) |
| Native peer and server evidence | [Identity](https://github.com/openabstractions/abstraction-identity) |

The [main repository](https://github.com/openabstractions/abstractions) contains
the development runtime, integration tests, adopters and current implementation
status.

## Start as a provider author

Implement the generated service contract and its behavioral rules. The runtime
can host an in-process provider, launch or attach to a registered native
provider, or mediate a configured remote provider. A provider owns its resources
and persistence. The service boundary supplies identity, authorization,
credentials, bounds and typed outcomes.

Contracts distinguish resolution, acceptance, progress, completion, refusal and
unknown outcome. Durable work keeps an immutable request identity and original
binding for reconciliation after a lost reply.

The [conformance suite](https://github.com/openabstractions/abstractions/tree/main/conformance)
tests contract behavior independently of the repository implementation.

## Evidence and release status

The current integration tree has controlled and native adopter evidence across
the principal capabilities. [Release notes](https://github.com/openabstractions/redist/releases/latest)
list available packages, installation verification and signing state.

- [Adoption guide](https://openabstractions.org/adopt.html): dependency,
  runtime and setup expectations.
- [Capability catalogue](https://openabstractions.org/catalogue.html): contracts,
  languages, platforms and package routes.
- [Coverage](https://openabstractions.org/coverage.html): the implementation,
  revision, platform and verdict behind each claim.
- [Recorded results](https://github.com/openabstractions/abstractions/tree/main/docs/results):
  transcripts and their machine context.
- [Project overview](https://github.com/openabstractions/abstractions): current
  offering, service ownership, trust limits and source entrypoints.

Pin the exact package revision you test. Read the selected repository's release
page before adding an installation command. Historical evidence records one run
at one revision.

Apache-2.0. See the selected repository's license and dependency notices.

[Governance](https://github.com/openabstractions/.github/blob/main/GOVERNANCE.md)
and [security reporting](https://github.com/openabstractions/.github/blob/main/SECURITY.md).
