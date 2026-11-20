# OpenSim-next Viewer

The dedicated PC Viewer repository for OpenSim-next.

## Project direction

OpenSim-next Viewer is a user-facing virtual-world client built on a mature Second Life / OpenSim viewer foundation. The initial integration strategy is **Firestorm-first**: preserve the upstream viewer's protocol, world synchronization, avatar, inventory, chat, building, and established client functionality, then evolve the product incrementally.

## Repository responsibilities

- [phoenix-firestorm](https://github.com/danggiatri6-spec/phoenix-firestorm): canonical Firestorm-derived Viewer source, OpenSim-next integration branches, build system, client UX, rendering evolution, performance, packaging, and release engineering.
- This repository: integration plan, architecture decisions, build notes, upstream tracking, and project coordination.
- [opensim-next](https://github.com/danggiatri6-spec/opensim-next): platform architecture, server-side work, Grid services, and cross-project planning.

## Upstream baseline

- Upstream: [Firestorm Viewer](https://github.com/FirestormViewer/phoenix-firestorm)
- Baseline branch: `Firestorm_7.2.5`
- Pinned commit: `4ac201fdc56127de27de34567286885f4e75d194`
- Fork mirror branch: `Firestorm_7.2.5`
- OpenSim-next working branch: `opensim-next/integration`
- Status: GitHub fork and branches verified; no successful Windows build or Grid connection is claimed.

## Platform priority

1. Windows 10/11 x64 — first-class initial platform.
2. macOS — second phase after the Windows experience stabilizes.
3. Linux — third phase; portability checks may run earlier.
4. Android — later, as a separate lightweight client.

Windows-first is a delivery priority, not a decision to make the architecture Windows-only.

## Engineering principles

- Keep the Firestorm upstream history and record the exact upstream commit for every integration baseline.
- Prefer small, reviewable changes and preserve upstream mergeability.
- Do not copy only `indra/newview`; the viewer depends on a large source tree, Autobuild configuration, generated files, and third-party dependencies.
- Do not replace mature protocol or world features until the replacement has feature parity and regression coverage.
- Keep the existing SDL3/OpenGL prototype as a separate technical experiment; it is not the production viewer foundation.
- Avoid cloud GPU rendering in the initial product.
- Support scalable quality settings so lower-end PCs can use core social and creation features.

## Current status

The true GitHub fork now exists at [danggiatri6-spec/phoenix-firestorm](https://github.com/danggiatri6-spec/phoenix-firestorm), with upstream parent [FirestormViewer/phoenix-firestorm](https://github.com/FirestormViewer/phoenix-firestorm). The pinned baseline and OpenSim-next integration branches have been created from the exact upstream commit listed above.

The Windows build dependency audit is documented in [docs/BUILD_AUDIT.md](docs/BUILD_AUDIT.md). It is based on the pinned source's official build guide and CMake configuration.

This is source-control and build preparation only. No successful Windows build, runtime launch, or OpenSim Grid login is claimed.

See [docs/FORK_SETUP.md](docs/FORK_SETUP.md), [docs/BASELINE.md](docs/BASELINE.md), and [docs/BUILD_AUDIT.md](docs/BUILD_AUDIT.md) for setup details.
See [docs/INTEGRATION_PLAN.md](docs/INTEGRATION_PLAN.md) for the integration plan.


## Windows End-User Distribution

See [Windows End-User Distribution Policy](docs/USER_DISTRIBUTION.md) for the zero-development-dependency installation requirements and release acceptance tests.
