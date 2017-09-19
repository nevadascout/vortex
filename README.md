# Vortex - The Vision
An open source scriptable framework for your CI/CD solution.

All build steps are fully scriptable and are placed within your project repository.

## 1. Management Area

 - PHP app that handles queuing of builds triggered by webhooks, an API or manually
 - Web interface for viewing builds
 - Sign in with BitBucket or GitHub
 - Documentation for builds API and how to write build steps


## 2. Build Runner Manager

 - A simple app that sits on a host machine
 - Listens to a message queue
 - Creates a docker container for each build


## 3. Build Runner

 - Lives within a docker image
 - Clones the repository
 - Reads the build config and triggers the build scripts



## Configuration options

### On Vortex server
 - bitbucket/github/gitlab account (for making comments, approving, etc)
 - app root path
 - build steps repo
 - project repo credentials (account or ssh key)

### In vortex.json
 - build steps (which order, which parellel, etc)
 - pre/post build scripts
 - enable/disable inline comments (for test failures, style violations, etc)
