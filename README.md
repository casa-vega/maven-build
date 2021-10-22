
# Example Maven build and release for Cadence

Using workflow-dispatch and github-app we can chain specific workflows together

- https://github.com/marketplace/actions/workflow-dispatch
- https://github.com/marketplace/actions/github-app-token
- https://github.com/marketplace/actions/merge-branch

## build-snapshot
- Performs a snapshot build on any branch that is not master.

## build-release
- Performs a release build on the specified branch using the specified build version
- Artifact created

## create release
- Performs a tag, release, and changelog
- Artifact shipped externally

## deploy development
- deploys resulting snapshot artifacts to development environment

## deploy snapshot
- environment protected for seperation of duty
- deploys cached artifact to staging environment

## deploy production
- environment protected for seperation of duty
- deploys cached artifact to production environment

