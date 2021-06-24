# git-style-guide 
![LICENSE](https://img.shields.io/github/license/sarscode/git-style-guide)
![GitHub Stars](https://img.shields.io/github/stars/sarscode/git-style-guide?style=social)

A sane, opinionated style guide for git.

## Repositories

> Great repository names are *short, descriptive* and *memorable*.

- Use **lowercase** for naming repositories.
- Use **kebab-case** (hyphen separated words) for multi-word names.

```
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

```
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

```
# good
ft-user-auth-12345
fix-scrollspy

# bad
fix

# ugly
login
```

> Branch names could also be version names or release tag names.

```
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

## Commit Messages

Commit messages should consist of three distinct parts separated by a blank line. A title and an optional body and an optional footer.

```bash
<type>(scope): <subject>

<body>

<footer>
```

**Title:** The is a required and should follow the format `<type>(scope): <subject>` . When body and  footer are absent the title should contain a summary of the change in this format `<type>(scope): <summary>`.

`type` can be one of these types:

- **feat:** A new feature
- **fix:** A bug fix
- **docs:** Changes to documentation
- **refactor:** Refactoring production code
- **test:** Adding tests, refactoring test; no production code change
- **chore:** Updating build tasks, package manager configs, etc; no production code change

`scope` is optional. However, if present, it should be something specific to the commit change. For example: **auth**.

`subject`  should be at most 50 characters, should begin with a capital letter and should not end with a period. Use present tense to describe what a commit does, rather than what it did. For example, use **Add**, instead of **Added** or **Adding**. 

```
# good
feat(accounts): Add user signup validations
chore(deps): Upgrade to parcel v2.0.1

# bad
fix

# ugly
login
```

**Body:** is optional and only used when a commit requires a bit of explanation and context. It should be written in present tense.

**Footer:** is optional and is used to reference issue tracking IDs.

*Below is template guide for a commit message with title, body and footer.*

```
feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
```

**Example:**

```
feat(accounts): Add user signup validations

Add validation constraints for user signup. Require password length to be 
minimum of 6 and contain Alphanumeric characters.

[Done #512345]
```
