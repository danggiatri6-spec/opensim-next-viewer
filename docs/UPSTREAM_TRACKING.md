# Firestorm Upstream Tracking

## Canonical upstream

- Repository: https://github.com/FirestormViewer/phoenix-firestorm
- Candidate branch: `Firestorm_7.2.5`
- Candidate commit: `4ac201fdc56127de27de34567286885f4e75d194`

## Import policy

The production viewer should be a true derivative of the upstream Git repository, retaining its history and tags. Preferred approach:

1. Create a GitHub fork of `FirestormViewer/phoenix-firestorm` under the project owner.
2. Clone the fork locally and add the official repository as remote `upstream`.
3. Check out the pinned candidate commit in a dedicated integration branch.
4. Push the branch to this repository only if GitHub's fork/network rules and repository setup permit retaining the upstream ancestry; otherwise keep the fork as the canonical source repository and use this repository for project-specific orchestration/docs or migrate the project repository deliberately.
5. Never represent a documentation-only repository as if it already contains Firestorm source.

## Required provenance record for every baseline

- Upstream URL
- Upstream branch/tag
- Full commit SHA
- Date imported
- Local patch series or commit range
- Build configuration and dependency manifest
- License and third-party notice review status

## Update cadence

- Do not blindly follow upstream `master`.
- Review upstream stable releases on a planned cadence.
- Evaluate security fixes and OpenSim compatibility before updating the pin.
- Rebase/merge upstream in a dedicated maintenance branch.
- Run the full build and Grid smoke-test suite before promoting a new baseline.

## Licensing

Firestorm's repository-level license information is not a substitute for reviewing the exact license files and bundled third-party components in the selected revision. Before distributing binaries or modified source, preserve notices, identify modified files, and satisfy applicable source/relinking obligations. Obtain legal review for distribution decisions where needed.