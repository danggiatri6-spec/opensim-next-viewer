# Windows Build Checklist

This checklist is for the candidate Firestorm 7.2.5 baseline. Always confirm exact requirements against the pinned branch's official build guide before running commands.

## Target

- Windows 10/11 x64
- Visual Studio 2022
- Desktop development with C++
- CMake (the upstream guide for the selected branch specifies the supported version)
- Git for Windows
- Python 3 and pip
- Autobuild and the upstream build-variables repository
- Sufficient free disk space for source, downloaded dependencies, and build products

## Source preparation

- [ ] Fork the official Firestorm repository, preserving Git history.
- [ ] Add the official repository as remote `upstream`.
- [ ] Check out the candidate baseline commit `4ac201fdc56127de27de34567286885f4e75d194`.
- [ ] Record the exact source commit and tool versions.
- [ ] Read the branch-specific `doc/building_windows.md`.

## Build configuration

The candidate OpenSim-enabled configuration is `ReleaseOS`. Do not use `ReleaseFS_open` for the OpenSim client because that configuration does not include OpenSim support.

The upstream guide has documented a command pattern similar to:

```powershell
autobuild configure -A 64 -c ReleaseOS -- --chan OpenSimNext -DLL_TESTS:BOOL=FALSE
autobuild build -A 64 -c ReleaseOS --no-configure
```

Treat these as a starting reference, not a guarantee: validate the exact options and dependency setup against the pinned branch and installed Autobuild version before execution.

## Optional components

For the first baseline, avoid optional components that require separate licenses or proprietary packages (for example KDU/Kakadu, FMOD, or Havok) unless the project has obtained the required rights and setup.

## Evidence to retain

- Full configure and build logs
- Compiler and SDK versions
- Autobuild version and dependency manifest
- Exact upstream commit
- Build artifact hashes
- Known warnings and disabled components

## Acceptance

A successful compile is only the first gate. The next gate is a runtime smoke test, followed by connection to a test OpenSim Grid and functional checks listed in [INTEGRATION_PLAN.md](INTEGRATION_PLAN.md).