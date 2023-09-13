# action-docker-template

<!-- TODO: replace action-docker-template with your repo name -->
[![Test](https://github.com/gsoc2/action-docker-template/workflows/Test/badge.svg)](https://github.com/gsoc2/action-docker-template/actions?query=workflow%3ATest)
[![reviewdog](https://github.com/gsoc2/action-docker-template/workflows/reviewdog/badge.svg)](https://github.com/gsoc2/action-docker-template/actions?query=workflow%3Areviewdog)
[![release](https://github.com/gsoc2/action-docker-template/workflows/release/badge.svg)](https://github.com/gsoc2/action-docker-template/actions?query=workflow%3Arelease)
[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/gsoc2/action-docker-template?logo=github&sort=semver)](https://github.com/gsoc2/action-docker-template/releases)
[![action-bumpr supported](https://img.shields.io/badge/bumpr-supported-ff69b4?logo=github&link=https://github.com/gsoc2/action-bumpr)](https://github.com/gsoc2/action-bumpr)

This is a template repository for [creating a Docker container action](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-a-docker-container-action).
with release automation and [reviewdog](https://github.com/reviewdog/reviewdog) (linters) integrations.
Click `Use this template` button to create your action based on this template.

A sample action is to get GitHub star counts from a given repository.

## Input
<!-- TODO: update -->

```yaml
inputs:
  github_token:
    description: 'GITHUB_TOKEN'
    default: '${{ github.token }}'
  repo:
    description: 'target GitHub repository. e.g. reviewdog/reviewdog'
    default: '${{ github.repository }}'
    required: true
```

## Usage
<!-- TODO: update -->

```yaml
- name: Get Star Count
  uses: gsoc2/action-docker-template@v1
  id: sample
  with:
    repo: "reviewdog/reviewdog"

- name: Check Star Count
  run: |
    echo "${{ steps.sample.outputs.star }}"
```

## Development

### Release

#### [gsoc2/action-bumpr](https://github.com/gsoc2/action-bumpr)
You can bump version on merging Pull Requests with specific labels (bump:major,bump:minor,bump:patch).
Pushing tag manually by yourself also work.

#### [gsoc2/action-update-semver](https://github.com/gsoc2/action-update-semver)

This action updates major/minor release tags on a tag push. e.g. Update v1 and v1.2 tag when released v1.2.3.
ref: https://help.github.com/en/articles/about-actions#versioning-your-action

### Lint - reviewdog integration

![reviewdog integration](https://user-images.githubusercontent.com/3797062/72735107-7fbb9600-3bde-11ea-8087-12af76e7ee6f.png)

Supported linters:

- [reviewdog/action-shellcheck](https://github.com/reviewdog/action-shellcheck)
- [reviewdog/action-hadolint](https://github.com/reviewdog/action-hadolint)
- [reviewdog/action-misspell](https://github.com/reviewdog/action-misspell)

