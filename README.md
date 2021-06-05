# git-style-guide

A sane, opinionated style guide for git.

## Repositories

> Great repository names are *short, descriptive* and *memorable*.

- Use **lowercase** for naming repositories.
- Use **kebab-case** (hyphen separated words) for multi-word names.

```bash
# good
prettier
parcel-transformer-ejs 

# bad
Parcel_Transformer_EJS
parcel_transformer_ejs

# ugly
Parcel Transformer EJS
ParcelTransformerEJS
```
## Branches

The primary branches could be any one or more of these:

- **main or master:** Production code. This branch contains code that is considered stable, possibly only code that has been or will be released. Code on this branch is deployable. Don't push directly to this branch. Merge only production ready code to this branch. This branch serves as an integration branch for production ready changes.
- **development or develop:** This is a optional branch. Development code. It could be the most active branch. This branch serves as an integration branch for features and fixes. When a feature is complete, it gets merged back into this branch.
- **staging:** This is an optional branch. It typical mirrors the master branch but usually for deploying to test servers. Code in this branch is usually ready and tested to be merged to the **main or master** branch.

Other branches are usually short-lived.

> Branch names should be *short* and *descriptive*.

- Use **kebab-case** when naming branches.
- Branch names should follow this format:

```bash
<story-type>-<description>-[ticket-id]
```

`story-type` can be one of these types:

- **ft:** A new feature
- **fix:** A bug fix
- **docs:** Changes to documentation
- **ref:** Refactoring production code
- **test:** Adding tests, refactoring test; no production code change
- **ch:** Updating build tasks, package manager configs, etc; no production code change

`description` is a summary of what the branch does. It should not be more than 50 characters. 

`ticket-id` is optional. However, if the branch is an implementation of a ticket in an agile project or a GitHub issue, the ticket id or issue tracking id should be referenced.

```bash
# good
ft-user-auth-12345
fix-scrollspy

# bad
fix

# ugly
login
```

> Branch names could also be version names or release tag names.

```bash
# good
v2.0.0
release-v2.1
version-10.0-oreo
v1.0.1-alpha

# bad
alpha
oreo

# ugly
next
```
