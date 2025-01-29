# Git

These are practices that apply to shared commits[1] (maybe after cleaning commits locally).

## tl;dr

-   Shared commits should not be changed.
-   Changes in each shared commit should be closely related.

## Don’t push your work until you’re happy with it

“One of the cardinal rules of Git is that, since so much work is local within your clone, you have a great deal of freedom to rewrite your history locally. However, once you push your work, it is a different story entirely, and you should consider pushed work as final unless you have good reason to change it. In short, you should avoid pushing your work until you’re happy with it and ready to share it with the rest of the world.”

– [Git tools - rewriting history](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)

See also:

-   [Which git commands rewrite history?](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
-   [Cleaning *unshared* history: Squashing all commits in a branch](https://youtu.be/08dhy3Zoob4).
-   [Cleaning *unshared* history with `git rebase --interactive`](https://youtu.be/cMI8p1XhMzA).
-   [Cleaning *unshared* history with `git commit --amend`](https://youtu.be/539pfVfr7OI).
-   [Cleaning shared history with `git revert`](https://youtu.be/A8Ld6iDqc3w).
-   [Git playlist](https://www.youtube.com/playlist?list=PLvgdJdJDL-AOHkwiaMvYhPKVjiD9vzZIo).

## Keep commits focused

A commit should focus on related changes only. For example, fixing two different bugs should produce two separate commits. Small commits make it easier for other developers to understand the changes and roll them back if something went wrong. You can avoid sharing unwanted changes via [.gitignore](https://git-scm.com/docs/gitignore). If you can’t succinctly describe what the commit is doing in a few words, then it is likely too big. Small commits are easier to review, and easier to merge because they offer fewer opportunities for conflicts.

See also:

-   [The right size of a PR](https://github.com/2DegreesInvesting/practices/discussions/3).
-   [Google engineering guide](https://google.github.io/eng-practices/review/developer/small-cls.html)
-   [.gitignore templates](https://github.com/github/gitignore).
-   Undoing things with Git ([video](https://youtu.be/dZOfEF19yDk), [lesson](https://coderefinery.github.io/git-intro/05-undoing)).

## The work you share should be complete

Each commit and feature should do what it promises, completely; and reverting it should undo what that commit or feature was meant to do, also completely. Before you commit changes, consider if other changes you’ve made are part of the same conceptual change and combine them into one commit rather than committing them separately.

## Explain how to test the effect of the changes you made

Testing your code is important, particularly when sharing it with others. Automated tests are the best but not the only way to test the effects of the changes you made. When automated tests are excluded, the  PR’s first comment should explain how you ensured that the code behaves as you expect, and how someone else may reproduce your results.

## Structure each commit message like an email

Like an email, commit messages have a subject and an optional body. The subject should start with a line summarizing your changes (aim for 50 characters or less). Use the imperative, present tense – for example, “Fix typo”, not “Fixed typo” or “Fixes typo”. The message body, if present, should follow a blank line; wrap around 70 characters; and explain the motivation for the change (“why”, not “what” or “how”).

See also:

-   [Example of a commit message](https://github.com/RMI/resources/issues/74)
-   [Commit best practices](https://r-pkgs.org/git.html#commit-best-practices)

## Agree on a workflow

Choose a workflow based on your team’s needs and preferences. However you choose to work, just make sure to agree on a common workflow that everyone follows:

GitHub workflow:

This workflow is RMI’s default. If a project uses a different workflow, document prominently (e.g. in README) what that workflow is ([example](https://github.com/github/gitignore#contributing-workflow)).

-   Uses a central repository.
-   Uses a single long-lived branch: “main”; it never contains broken code.
-   Developers work on “feature” branches (never on the “main” branch), share them via pull requests, and peers review the changes before they become a part of the central repository.
-   A new release is created by tagging a particular commit on the main branch.

Gitflow workflow:

-   Like the GitHub workflow but uses two long-lived branches: “main” and “develop”. The main branch stores the official release history, and the develop branch serves as an integration branch for features.

A team may agree on custom conventions beyond the “vanilla” workflows listed above. For example, you may agree to prefix a commit subject with “FIXME”, “AMEND”, or something else, to communicate with your team succinctly via a vocabulary you all share.

See also:

-   [Comparing workflows](https://www.atlassian.com/git/tutorials/comparing-workflows).

## Use tools to be more productive

Rather than relying on memory or will power, rely on good systems. Good systems such as git [aliases](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases), [hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks), and [graphical user interfaces](https://happygitwithr.com/git-client.html) can help you work more productively, correctly, and comfortably.

See also:

-   [oh-my-zsh: Unleash your terminal like never before](https://ohmyz.sh/).
-   [gh: Take GitHub to the command line](https://cli.github.com/).
-   [Git from RStudio](https://rstudio.com/resources/webinars/managing-part-2-github-and-rstudio/).

## References

[Version control best practices](https://www.git-tower.com/blog/version-control-best-practices/)

## How

-   [GitHub’s Git guides](https://github.com/git-guides/).
-   [Coderefinery’s Git intro](https://coderefinery.github.io/git-intro/).
-   [Git best practices](https://bit.ly/book-git-in-practice).
-   [Visualization of useful Git
    commands](https://dev.to/lydiahallie/cs-visualized-useful-git-commands-37p1).

------------------------------------------------------------------------

[1] A *shared* commit is a commit that someone other than you might access, for example, because you pushed it to a remote repository that someone else has permission privileges to access.
