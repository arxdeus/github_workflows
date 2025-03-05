# Github Actions Workflows


## Reusable workflows

Refer to any workflow configuration under `.github/workflows` directory inside your own Github Actions configuration
```
jobs:
    code_check:
        uses: arxdeus/github_workflows/.github/workflows/dart_monorepo_code_check.yaml@main
```

Don't forget to give relevant permissions and workflow conditions inside your configuration

Each required by workflow permissions listed in each workflows section below

Example of usage:
https://github.com/arxdeus/modulisto/blob/main/.github/workflows/code_check.yaml

## Composite actions

Composite actions located in `actions` directory and acts as a steps of the jobs inside your workflows

You may refer to them from your workflows steps under `jobs.*.steps.*.uses` section

```
steps:
    - name: Setup
      uses: arxdeus/github_workflows/actions/flutter_setup@main
```

Example of usage: https://github.com/arxdeus/github_workflows/blob/main/.github/workflows/dart_monorepo_code_check.yaml#L60

## Flutter

### Setup action:

type: ___Composite action___

Features:
- Fetches and caches target `flutter` version
- Caches pub dependencies
- Caches `flutter` until version change

#### Action path: `arxdeus/github_workflows/actions/flutter_setup@main`

## Dart

###  Code check

type: ___Reusable workflow___

Features:
- Pre-checks that code or pubspec actually was modified
- Checks both of the lowest (from `pubspec.yaml`) and highest/actual (from `.fvmrc`) versions
- Creates human-readable Test reports for both versions

#### Workflow path: `arxdeus/github_workflows/.github/workflows/dart_monorepo_publish.yaml@main`

### Multi-package monorepo publish workflow

type: ___Reusable workflow___

Features:
- `[package_name]-v[x].[x].[x]` semantic versioning via tags
- Automatic update of `pubspec.yaml` to version extracted from part of tag
- Automatic publish [package_name] to `pub.dev`

#### Workflow path: `arxdeus/github_workflows/.github/workflows/dart_monorepo_publish.yaml@main`

### Single-package publish workflow

type: ___Reusable workflow___

Features:
- `v[x].[x].[x]` semantic versioning via tags
- Automatic update of `pubspec.yaml` to tag
- Automatic publish to `pub.dev`

#### Workflow path: `TBD`


