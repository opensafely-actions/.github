# Rulesets for opensafely-actions repositories

This directory houses two JSON files that can be used to import rulesets into
a repository in the `opensafely-actions` organization.
It is recommended to apply these rulesets to repositories housing reusable actions
within the organization.

### Importing a ruleset into a repository
A ruleset can be imported into a repository by following these steps:
 - Download the appropriate JSON file from this directory
 - In the repo, head to ⚙️Settings > Rules > Rulesets
 - Select New Ruleset > Import a ruleset
 - Browse to the downloaded JSON file and select it
 - Review the imported ruleset, adding further configuration (e.g. status checks) if needed
 - Save your changes!

Here is a video example,courtesy of
[github's ruleset-recipes repository README](https://github.com/github/ruleset-recipes/blob/main/README.md).

![Gif walking through the steps outline above to import a ruleset from a JSON file.](https://github.com/github/release-assets/assets/7575792/8806fa8c-b874-4a4e-97ef-4f8c238f4d29)


### Rulesets

#### Protect default branch (`protect-default-branch.json`)
This ruleset applies to the default branch of a repository, and offers the following protections:
- Prevent deletion by users
- Require a PR before merging
- Require status checks to pass before merging
- Prevent force-pushing

The above protections are in place to facilitate effective collaboration and minimise the risk of
broken code being merged into the default branch.
By ensuring that users work on separate branches prior to merging, users can work in parallel on
features or bug fixes without affecting the default branch, and any conflicting code can be
resolved in a PR before merging.

When the ruleset is imported, the required status checks will have to be added manually in the web UI.
Please ensure that this is done. If no status checks are added, an error will be raised by GitHub when
attempting to save the ruleset.

#### Protect semantically versioned tags (`protect-semantically-versioned-tags.json`)
This ruleset applies to tags that follow the semantic versioning format (e.g. `v1.0.0`),
and offers the following protections:
- Prevent deletion by users
- Prevent force-pushing

Since semantically versioned tags are used to represent releases, the above protections are in place to
ensure that the release history is preserved and that tags are not accidentally deleted or modified.