# Github Actions Workflows

## Outdated

Each workflow below have ID that refers to relevant branch contains predefined `.github/workflow/*.yaml` configuration

`main` branch doesn't contains any Github Actions configuration, but their description

#### Usage:

```
git clone -b [workflow_id] https://github.com/arxdeus/github_workflows .github
```

---

### Flutter

Setup action:

Workflow ID: `flutter/setup`

Features:
- Fetch and cache target `flutter` version
- Cache pub dependencies
- Cache `flutter` until version change

### Dart

Dart language contains 2 workflows:
#### 1. Single-package workflow

Workflow ID: `dart/single_package`

Features:
- `v[x].[x].[x]` semantic versioning via tags
- Automatic update of `pubspec.yaml` to tag
- Automatic publish to `pub.dev`

#### 2. Multi-package monorepo workflow

Workflow ID: `dart/monorepo_multi_package`

Features:
- `[package_name]-v[x].[x].[x]` semantic versioning via tags
- Automatic update of `pubspec.yaml` to version extracted from part of tag
- Automatic publish [package_name] to `pub.dev`

---
