# Readme

## Case one - build image for master

When there is `${{ github.sha }}` present, but not `${{ github.event.pull_request.head.sha }}` - this means it is triggered from the master branch.

The symptoms:

    * GIT_COMMIT == ${{ github.sha }}

This happens when:

    * Trigered by schedule
    * Manually triggered from **master** branch

## Case when committing to branch different than master

## Make PR from non-master branch to master branch

In that case tehre is a value for `${{ github.event.pull_request.head.sha }}` and the this will trigger non-master tasks

The symptoms:

    * GIT_COMMIT == ${{ github.event.pull_request.head.sha }}

## Merge PR to master branch

There is not `${{ github.event.pull_request.head.sha: }}` and the symptoms are

The symptoms:

    * GIT_COMMIT == ${{ github.sha }}
