# Best Practices for Pull Requests

Pull requests (PRs) are a core mechanism for maintaining high-quality code and ensuring collaborative software development. A well-structured PR process improves the readability, maintainability, and stability of code while fostering a culture of peer review and knowledge sharing.

The following guidelines outline best practices for submitting, reviewing, and merging pull requests in RMI repositories.

## General Requirements
- Any repository that is expected to be seen or used by others **should have its main branch protected**, ensuring that all changes go through a pull request process.
- A pull request **should receive at least one review** from someone other than the submitter before merging.
- Automated checks (e.g., CI/CD pipelines, linters, test suites) **should pass before a PR is approved**.

## Submitting a Pull Request
When submitting a PR, follow these principles to make the review process smooth and effective:
- **Keep PRs Focused and Small**:
  - PRs should be scoped to a specific change (e.g., a feature, bug fix, or refactor) to make review easier (see [git](git.md) for more information).
- **Write a Clear PR Description**:
  - Clearly state the purpose of the PR.
  - Mention relevant issues (e.g., "Fixes #42").
- **Ensure Code is Ready for Review**:
  - Run all tests and linters locally before submitting.
  - Merge from the latest `main` to avoid merge conflicts.
  - Include relevant documentation updates if the change affects API.

## Reviewing a Pull Request
Reviewers play a crucial role in maintaining code quality while keeping the development process efficient. The following principles apply:

### Review Timing & Frequency
- Developers should allocate one dedicated time block per day for code review.
- At the same time, developers are not expected to be reviewing PRs continuously throughout the day (ie. Submitters should plan for a 24hr turn-around from PR to merge).

### Approval Criteria
- PRs should be approved when they definitely improve the overall health of the repository, even if they are not perfect.
- If a PR is generally good but requires minor improvements, it is encouraged to approve with comments rather than blocking progress unnecessarily.
- If a PR introduces significant issues, reviewers should request changes with specific, and constructive feedback.

### Providing Clear Feedback
- Reviews must specify an explicit status:
  - ✅ **Approval** – The PR is good to merge.
  - 🔄 **Requested Changes** – Specific identified improvements are required before merging.
  - ❌ **Close Recommendation** – The PR should not be merged (e.g., if it's redundant, out of scope, or fundamentally flawed).
- "NIT" (nit-picky) or "NB" (non-blocking) comments do not constitute a full review. If a reviewer provides only nits, they should still approve the PR.

### Effective Review Comments
- Be Specific: Instead of “this needs improvement,” say “Consider using a named constant instead of a magic number here.”
- Be Constructive: Focus on helping the author improve their code rather than just pointing out mistakes.
- Balance Perfection vs. Progress: Not every PR needs to be flawless, but it should meet quality standards and not introduce technical debt.

## Merging a Pull Request
- PRs should only be merged when they have:
  - ✅ At least one approval from a non-submitter.
  - ✅ All required automated checks passing.
  - ✅ Any requested changes addressed.
- "Squash and merge" is recommended to keep the commit history clean, unless there’s a good reason to preserve multiple commits.
- The PR author is responsible for merging their own PR once it meets all requirements.

## Additional Considerations
- **Emergency Fixes**: In rare cases, urgent fixes (hot-fixes) may be merged with an expedited review process. This should be an exception, not the norm.
- **Refactoring PRs**: If a PR is purely a refactor (e.g., renaming, restructuring), it should be reviewed with an emphasis on maintainability and avoiding regressions.

By following these best practices, we can maintain a high-quality, well-reviewed codebase while keeping the development workflow smooth and efficient.
