# Guidelines for versioning

Contents:

- Versioning schema for third party products
- Versioning schema for CNO products
- Creating a new version

## Versioning schema for third party products

CNO uses Ansible roles to deploy third party products as platform components.

These roles are versioned as `<product version>-<role version>`.

### Product version

The `<product-version>` represents the version of the main product in a Role.

In case of Helm, the application version is used, not the chart version.

### Role version

The `<role-version>` represents the version of the CNO Ansible Role itself:

- Starting at `1.0` for each new main product version
- Small fixes on the `1.0` result in a `1.1`
- Changes to the `1.0` version that may need configuration changes or need other attention will result in a `2.0`

Example for Gitlab:

- `13.4.1-1.0`: first tag on Gitlab role for deploying Gitlab application version `13.4.1`, deployed via Helm Chart version 4.4.1 (whose version is not shown up in this schema)
- `13.4.1-1.1`: tag for the same role that had a small fix.

## Versioning schema for CNO products

CNO has various roles for internal, supportive products.

These roles are versioned via [SemVer](https://semver.org/).

Example for Gitlab-cli:

- `0.1.0`: first tag on Gitlab-cli

## Creating a new version

Steps to create a new version for a role:

1. Go to the project of the CNO component in Gitlab

2. Go to _Deployments_ > Releases

3. Click _New release_

4. Fill out:

   - _Tag name_: use the version from guidelines above
   - _Release title_: choose a short descriptive name
   - _Release notes_: provide a brief list of most significant changes in this release
   - _Links_: if applicable add links to release and changelogs of the third party product


5. Click _Create release_

6. Inform the team on the new version
