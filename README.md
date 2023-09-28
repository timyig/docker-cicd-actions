# docker-cicd-actions

Test repository to building a docker image release workflow

## Workflow description

### Branches

The `main` branch is protected by allowing only pull requests from the `dev` branch.
PR are merged automatically after checks have passed.
Pull requsts from the `dev` branch are triggered when a commit is tagged in the `dev branch`.

Commits into the `dev` branch are only possible via PRs and checks.

### Workflows

* main
  * When PR is opened pull images and run sanity checks
  * Tag the images with the `Tag` and push
* dev
  * When PR is opend build, test and push image
    * Tag with dev and datetime (YYYY-MM-DD-HH-MM)
  * When commit is tagged open PR into main

### ToDos

* [ ] Build, Test, Push on PR to `dev`
  * [ ] Get tag the image
* [ ] Trigger PR into main when commit is tagged in `dev`
* [ ] On PR opened in main, pull, tag and push image
