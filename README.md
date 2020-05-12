# Autobadge

| Summary           | Badge                                              |
| ----------------- | -------------------------------------------------- |
| Release Stability | ![Autobadge Release Stability][release-stability]  |
| Latest Release    | ![Autobadge Latest Release][latest-release]        |
| Code Quality      | [![Maintainability][quality-image]][quality-link]  |
| Code Coverage     | [![Test Coverage][coverage-image]][coverage-link]  |

[release-stability]: https://img.shields.io/static/v1?label=latest&message=0.1.0&color=purple
[latest-release]: https://img.shields.io/static/v1?label=stability&message=prerelease&color=yellow
[quality-image]: https://api.codeclimate.com/v1/badges/74ffb9e627a105dd7a43/maintainability
[quality-link]: https://codeclimate.com/github/autosuite/autobadge/maintainability
[coverage-image]: https://api.codeclimate.com/v1/badges/74ffb9e627a105dd7a43/test_coverage
[coverage-link]: https://codeclimate.com/github/autosuite/autobadge/test_coverage

## Introduction

This is a GitHub Action that automatically manages a few types of badges in a predetermined area in your `README.md`
file. Currently, this consists of two badges:

- Current version.
- Stability.

## Usage

Note that you will need to have an Action that performs a pre-commit (stage, commit) and push, as seen below:

```yaml
name: my-workflow

on: [push]

jobs:
  autocommit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - uses: autosuite/autobadge@master
      - uses: autosuite/autocommit@master
      - uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
```

Next, add the following lines to anywhere in your `README.md` file (see the source of this file as an example):

```md
[release-stability]: foo
[latest-release]: foo
```

As well as these lines:

```md
| Summary           | Badge                                              |
| ----------------- | -------------------------------------------------- |
| Release Stability | ![Autobadger Release Stability][release-stability] |
| Latest Release    | ![Autobadger Latest Release][latest-release]       |
```

## Configuration

> You can see all configuration in the [action.yml](action.yml) file.

There is no special configuration for this Action. This may be subject to change as the need arises.

## Documentation

If you would like to contribute to this project, please read our [contributors documentation](CONTRIBUTING.md) and
our [code of conduct](CODE_OF_CONDUCT.md). The license we use for this project is defined in
[the license file](LICENSE).
