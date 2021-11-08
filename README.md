
# Example Maven build and release for Cadence

[![build-release](https://github.com/casa-vega/maven-build/actions/workflows/build-release.yml/badge.svg)](https://github.com/casa-vega/maven-build/actions/workflows/build-release.yml)

Using workflow-dispatch and github-app we can chain specific workflows together

- https://github.com/marketplace/actions/workflow-dispatch
- https://github.com/marketplace/actions/github-app-token
- https://github.com/marketplace/actions/merge-branch


## Default Build and Deployments (typically main or master branch)

Order of operations:

### 1. build default (build-default.yml)
- Performs a snapshot build on the default branch.

## Snapshot Build and Deployments (development branch)

### 1. build snapshot (build-snapshot.yml)
- Performs a snapshot build on any branch that is not master.

### 2. deploy development (deploy-development.yml)
- deploys resulting snapshot artifacts to development environment

---

## Release Build and Deployments 

Order of operations:

### 1. build release (build-release.yml)
- Performs a release build on the specified branch using the specified build version
- Artifact created

### 2. tag release (tag-release.yml)
- Performs a git tag, github release, and changelog
- Artifact shipped externally

### 3. update release (update-release.yml)
- Performs a POM file version update

### 3. deploy snapshot (deploy-staging.yml)
- environment protected for seperation of duty
- deploys cached artifact to staging environment

### 4. deploy production (deploy-production.yml)
- environment protected for seperation of duty
- deploys cached artifact to production environment

