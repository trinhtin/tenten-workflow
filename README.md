# tenten-workflow

# Quản lý mã nguồn với Git: Sử dụng 2 nhánh release và 1 nhánh chính (main)

This document describes a popular workflow for managing source code with Git using two release branches and one main branch.

## Branches

* **main branch:**
    * The central branch that stores stable and well-tested source code.
    * Should be protected to avoid direct changes.
    * Used to create official releases for the project.
* **release branches:**
    * Created from the main branch for each new release.
    * Used to implement changes and bug fixes for the upcoming release.
    * Once completed, the release branch is merged into the main branch and a tag is created to mark the release.

## Workflow

1. **Start from the main branch:**
    * Clone the latest source code from the main branch to your local machine.
    * Begin working on changes and bug fixes for the next release.
2. **Create a release branch:**
    * When you're ready for a new release, create a new release branch from the main branch.
    * Example: `git branch release/v1.0.0`
3. **Work on the release branch:**
    * Switch to the created release branch: `git checkout release/v1.0.0`
    * Make the necessary changes and bug fixes for the release.
    * Frequently commit and push your changes to the release branch.
4. **Review and merge the release branch:**
    * After completing the release development, switch to the release branch and run `git checkout main`.
    * Merge the latest code from the release branch into the main branch: `git merge release/v1.0.0`.
    * Resolve any conflicts (if any) that arise during the merge process.
    * Push the changes to the main branch.
5. **Create a tag for the release:**
    * Switch to the main branch: `git checkout main`
    * Create a tag for the release: `git tag v1.0.0`
    * Push the tag to the main branch: `git push --tags`
6. **Release the software:**
    * After creating the tag, you can proceed with publishing the release to users.

##  Additional Notes

* Consider using Git Flow or GitLab Flow for a clearer and more efficient workflow.
* Utilize code review to ensure code quality before merging into the main branch.
* Employing release branches helps safeguard the main branch from unwanted changes and guarantees stability for official releases. 

## References

* [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows)
* [GitHub workflow](https://docs.github.com/en/get-started/using-github/github-flow)
* [GitLab Flow](https://about.gitlab.com/topics/version-control/what-is-gitlab-flow/)

For further information, explore additional resources and online courses on Git to enhance your knowledge and proficiency in source code management.

I hope this helps!
