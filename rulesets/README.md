# Rulesets for opensafely-actions repositories


This directory contains several [rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets)
for repositories in the opensafely-actions organisation.

## Importing a ruleset into a repository
Follow [the instructions in the GitHub docs for importing a ruleset](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/managing-rulesets-for-a-repository#importing-a-ruleset).

Note that the Protect default branch ruleset requires status
checks to pass before a topic branch can be merged into the default branch.
**You will need to specify the applicable status checks manually in the web UI when you import the ruleset.**

## Rulesets

Refer to the [GitHub documentation](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets) if you need help interpreting specific rules.

### Protect default branch
This ruleset protects the default branch of a repository.
The protections are in place to facilitate effective collaboration and minimise the risk of broken code being merged into the default branch.
Via the ruleset, we encourage that users work on separate branches prior to merging,
which allows users to work in parallel on features or bug fixes without affecting the default branch,
and to resolve any conflicting code in a pull request before merging.

### Protect semantically versioned tags
This ruleset protects tags that follow the semantic versioning format (e.g. `v1.0.0`).
Since semantically versioned tags are used to represent releases,
the protections are in place to ensure that the release history is preserved and that tags are not accidentally deleted or modified.