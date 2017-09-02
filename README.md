# vortex
An open-source scriptable pull request build bot

Build steps are custom scripts which can either be placed into a separate repo, or within the repo being tested

## Overview
**Architecture**
1. User sets up webhook call on new PR being created within BitBucket/GitHub/GitLab
2. Vortex queues a new build for the PR at the appropriate commit
3. Vortex runs the build, checking out the required commit
    - Checkout the repository (limited history)
    - Load the vortex build config file
    - Run the pre-build script
    - Run the build steps
    - Run the post-build script
    - Finish
4. Vortex reports back the build status on the PR in comments



## Configuration options

### On Vortex server
 - bitbucket/github/gitlab account (for making comments, approving, etc)
 - app root path
 - build steps repo
 - build steps repo credentials (account or ssh key)

### In vortex.json
 - build steps (which order, which parellel, etc)
 - pre/post build scripts
 - enable/disable inline comments (for test failures, style violations, etc)
