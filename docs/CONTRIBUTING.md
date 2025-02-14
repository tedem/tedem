# Contributing

We warmly invite you to contribute to this repository and help enhance its value, making it even better than it is today! As a contributor, we kindly ask you to follow these guidelines to ensure a smooth and productive collaboration.

 - [Code of Conduct](#code-of-conduct)
 - [Question or Problem?](#question-or-problem)
 - [Issues and Bugs](#issues-and-bugs)
 - [Feature Requests](#feature-requests)
 - [Submission Guidelines](#submission-guidelines)
 - [Coding Rules](#coding-rules)
 - [Commit Message Guidelines](#commit-message-guidelines)

## Code of Conduct

This repository is committed to fostering a safe, respectful, and inclusive environment for all contributors. To ensure a positive experience, we expect all contributors to adhere to the following principles:

- Treat everyone with respect and kindness.
- Avoid using language that is discriminatory, offensive, or exclusionary.
- Provide constructive feedback and engage in good faith discussions.
- Refrain from any form of harassment, threats, or inappropriate behavior.

If you observe or experience a violation of these principles, we encourage you to report it promptly via [contact method/reporting mechanism]. Your concerns will be addressed with confidentiality and care.

## Question or Problem?

Please refrain from opening issues for general support questions, as we aim to reserve GitHub issues for bug reports and feature requests. For support inquiries, feel free to reach out via [contact method/reporting mechanism].

## Issues and Bugs

If you encounter a bug in the source code, you can help us by [submitting an issue](#submitting-an-issue) on our GitHub Repository.
Even better, you can [submit a pull request](#submitting-a-pull-request-pr) with a fix.

## Feature Requests

You can *request* a new feature by [submitting an issue](#submitting-an-issue) to our GitHub Repository.
If you would like to *implement* a new feature, please consider the size of the change to determine the right steps to proceed:

- For a **Major Feature**, first open an issue and outline your proposal so that it can be discussed.
  This process allows us to better coordinate our efforts, prevent duplication of work, and help you craft the change so that it is successfully accepted into the project.

  **Note**: Adding a new topic to the documentation, or significantly rewriting a topic, counts as a major feature.

- **Small Features** can be crafted and directly [submitted as a pull request](#submitting-a-pull-request-pr).

## Submission Guidelines

### Submitting an Issue

Before you submit an issue, please search the issue tracker. An issue for your problem might already exist, and the discussion could provide you with readily available workarounds.

You can [submit an issue](#submitting-an-issue) to our GitHub Repository.

### Submitting a Pull Request (PR)

Before you submit your pull request (PR), please consider the following guidelines:

1. Search our GitHub Repository for any open or closed PRs related to your submission.
   You don't want to duplicate existing efforts.

2. Ensure that an issue describes the problem you're fixing or documents the design for the feature you'd like to add.
   Discussing the design upfront helps ensure that we're ready to accept your work.

3. [Fork](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo) the repo.

4. In your forked repository, make your changes in a new git branch:

     ```shell
     git checkout -b fix/my-branch main
     ```

5. Create your patch.

6. Follow our [Coding Rules](#coding-rules).

7. Commit your changes using a descriptive commit message that follows our [commit message guidelines](#commit-message-guidelines).
   Adherence to these conventions is necessary because release notes are automatically generated from these messages.

     ```shell
     git commit --all
     ```
    Note: the optional commit `--all` command line option will automatically "add" and "rm" edited files.

8. Push your branch to GitHub:

    ```shell
    git push origin fix/my-branch
    ```

9. In GitHub, send a pull request to the repository.

### Reviewing a Pull Request

The repository team reserves the right not to accept pull requests from community members who haven't been good citizens of the community.

#### Addressing Review Feedback

If we ask for changes via code reviews then:

1. Make the required updates to the code.

2. Create a fixup commit and push to your GitHub repository (this will update your Pull Request):

    ```shell
    git commit --all --fixup HEAD
    git push
    ```

That's it! Thank you for your contribution!

##### Updating the Commit Message

A reviewer might often suggest changes to a commit message (for example, to add more context for a change or adhere to our [commit message guidelines](#commit-message-guidelines)).
In order to update the commit message of the last commit on your branch:

1. Check out your branch:

    ```shell
    git checkout fix/my-branch
    ```

2. Amend the last commit and modify the commit message:

    ```shell
    git commit --amend
    ```

3. Push to your GitHub repository:

    ```shell
    git push --force-with-lease
    ```

> NOTE:
> If you need to update the commit message of an earlier commit, you can use `git rebase` in interactive mode.
> See the [git docs](https://git-scm.com/docs/git-rebase#_interactive_mode) for more details.

#### Pull Request is Merged

After your pull request is merged, you can safely delete your branch and pull the changes from the main (upstream) repository:

* Delete the remote branch on GitHub either through the GitHub web UI or your local shell as follows:

    ```shell
    git push origin --delete fix/my-branch
    ```

* Check out the main branch:

    ```shell
    git checkout main -f
    ```

* Delete the local branch:

    ```shell
    git branch -D fix/my-branch
    ```

* Update your local `main` with the latest upstream version:

    ```shell
    git pull --ff upstream main
    ```

## Coding Rules

To ensure consistency throughout the source code, keep these rules in mind as you are working:

## Commit Message Guidelines

Commit messages must follow the [Conventional Commits](#[commit-header](https://www.conventionalcommits.org/en/v1.0.0/) format.

We have very precise rules over how our Git commit messages must be formatted.
This format leads to **easier to read commit history**.

Each commit message consists of a **header**, a **body**, and a **footer**.

```
<header>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The `header` is mandatory and must conform to the [Commit Message Header](#commit-message-header) format.

The `body` is mandatory for all commits except for those of type "docs".
When the body is present it must be at least 20 characters long and must conform to the [Commit Message Body](#commit-message-body) format.

The `footer` is optional. The [Commit Message Footer](#commit-message-footer) format describes what the footer is used for and the structure it must have.

#### Commit Message Header

```
<type>(<scope>): <short summary>
  │       │             │
  │       │             └─⫸ Summary in present tense. Not capitalized. No period at the end.
  │       │
  │       └─⫸ Commit Scope: [You can check the repository commit history.]
  │
  └─⫸ Commit Type: build|chore|ci|docs|feat|fix|perf|refactor|revert|style|test
```

The `<type>` and `<summary>` fields are mandatory, the `(<scope>)` field is optional.


##### Type

Must be one of the following:

* **build**: Changes that affect the build system, tools, or external dependencies. These changes often involve updating configurations, adding/removing dependencies, or modifying build scripts. Example scopes: `gulp`, `broccoli`, `npm`.

* **chore**: Routine tasks or maintenance updates that do not modify application logic or features. These could include updating dependencies, renaming files, or restructuring the project folder.

* **ci**: Modifications to Continuous Integration (CI) configuration files and scripts to improve or fix automated testing and deployment processes. Examples include updates to workflows, pipelines, or tools like `GitHub Actions`, `Jenkins`, or `TravisCI`.

* **docs**: Changes limited to documentation, such as updates to `README.md`, API documentation, or inline comments. These changes do not affect the code or functionality.

* **feat**: Introduction of a new feature or functionality to the codebase. This usually involves adding new modules, APIs, or user-facing features.

* **fix**: Corrections of bugs or issues that affect the functionality or expected behavior of the application. This includes addressing errors, glitches, or regressions.

* **perf**: Code modifications aimed at enhancing performance, such as optimizing algorithms, reducing resource usage, or improving load times. These changes should not alter functionality.

* **refactor**: Restructuring existing code without changing its behavior or functionality. This can include improving readability, reusing code, or simplifying complex logic.

* **revert**: Undoing a previous commit or set of changes. This is typically used to roll back changes that introduced bugs or unintended side effects.

* **style**: Code changes that do not affect the functionality but improve the formatting, structure, or style, such as fixing indentation, renaming variables for clarity, or adhering to a style guide.

* **test**: Addition of new tests, updates to existing tests, or fixing issues in the test suite. These changes ensure better test coverage and reliability of the codebase.

##### Scope

You can check the repository commit history.

##### Summary

Use the summary field to provide a succinct description of the change:

* Use the imperative, present tense: "change" not "changed" nor "changes".
* Don't capitalize the first letter.
* Do not use a dot (.) at the end.

#### Commit Message Body

Just as in the summary, use the imperative, present tense: "fix" not "fixed" nor "fixes".

Explain the motivation for the change in the commit message body. This section should explain _why_ you are making the change.
You can include a comparison of the previous behavior with the new behavior to illustrate the impact of the change.

#### Commit Message Footer

The footer can contain information about breaking changes and deprecations. It is also the place to reference GitHub issues, Jira tickets, and other PRs that this commit closes or is related to.

For example:

```
BREAKING CHANGE: <breaking change summary>
<BLANK LINE>
<breaking change description + migration instructions>
<BLANK LINE>
Closes #<issue number>
<BLANK LINE>
Co-authored-by: Jane Doe <jane.doe@example.com>
Signed-off-by: John Smith <john.smith@example.com>
```

or

```
DEPRECATED: <what is deprecated>
<BLANK LINE>
<deprecation description + recommended update path>
<BLANK LINE>
Closes #<pr number> (PR)
<BLANK LINE>
Co-authored-by: Jane Doe <jane.doe@example.com>
Signed-off-by: John Smith <john.smith@example.com>
```

The Breaking Change section should start with the phrase `BREAKING CHANGE:` followed by a summary of the breaking change, a blank line, and a detailed description of the breaking change that also includes migration instructions.

Similarly, the Deprecation section should start with `DEPRECATED:` followed by a short description of what is deprecated, a blank line, and a detailed description of the deprecation that also mentions the recommended update path.

### Revert Commits

If the commit reverts a previous commit, it should begin with `revert:`, followed by the header of the reverted commit.

The content of the commit message body should contain:

- Information about the SHA of the commit being reverted in the following format: `This reverts commit <SHA>`.
- A clear description of the reason for reverting the commit.

## Thanks

Tank you for your contribution!

**Note**: [Angular/CONTRIBUTING.md](https://github.com/angular/angular/blob/main/CONTRIBUTING.md) was used as a base for this document.
