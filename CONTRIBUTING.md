# Context
This file refers to the process of contributing to this documentation repository.

> 💡 For contributing to Cockpit itself please see [the source code repository](https://github.com/bluerobotics/Cockpit).

## Repository Structure
1. Each branch covers some form of release of the software
    - The `latest` branch covers the unstable features in development / early testing
    - The `stable` and `X.Y` versioned branches track major and minor stable releases
      - `stable` documents the current latest stable version
      - It only branches into the corresponding numbered branch at the time of the next version number increment
    - Patch release (`X.Y.Z`) changes are documented (as relevant) in the corresponding minor release branch (`X.Y`)
1. Documentation content is in the `content` directory
1. The theme is included in the `themes` directory, as a git submodule

## Release Synchronisation
1. Documentation contributions should be opened as [Draft pull requests](https://github.blog/2019-02-14-introducing-draft-pull-requests/) until the documented features have been merged into the software codebase, or released in the relevant version
1. Documentation completeness should not prevent software feature merging, but may hold up versioned software releases
    - Ideally every released feature and interface should have documentation available, but to avoid confusion documentation should never be merged for features that are not yet available
    - It is recommended that software pull requests that change an interface or part of the documented code structure be marked with a `docs-needed` [label](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels), and include a comment about which aspects need to be documented prior to the feature being merged (while the details are still front of mind for the developer)
    - If a software pull request is labelled as `docs-needed`, once a corresponding documentation pull request is merged the feature PR can be re-labelled with a completion status (e.g. `docs-minimal` or `docs-complete`)
    - Beta releases may require that no merged features are labelled with `docs-needed`, and stable releases may require that no included features are labelled with `docs-needed` or `docs-minimal`
1. When a new major or minor stable release of the software is made, the `stable` branch gets duplicated into a new branch tracking that version, which then gets reconfigured with a fixed release number, and the now-stable features in the `latest` branch get cherry-picked to the `stable` branch
    - This is handled by the documentation maintainers

# Making a Contribution
### Highlighting Documentation Holes/Weaknesses
> 💡 Suggesting areas for improvement is a valuable contribution!

While we strive to have comprehensive and clear documentation, it is not always obvious to developers which features need additional explanation. If there's a feature you're struggling to make sense of then others likely are too, so please let us know about it!

After searching for existing information, the recommended approaches are to:
1. Ask questions on [the community forum](https://discuss.bluerobotics.com/c/bluerobotics-software), for clarification of features you would like a better explanation of
1. [Create an Issue](https://github.com/bluerobotics/Cockpit-docs/issues) in this repository, with notes of your existing understanding, what you're unsure about, and/or any links and references that seem relevant

### Adding to the Documentation
> 💡 Contributions should typically be made from a unique branch in an external fork.

Specific processes are covered below, but the general process is:

0. [Create a GitHub account](https://github.com/signup)
1. [Fork this repository](https://github.com/bluerobotics/Cockpit-docs/fork)
1. [Make a new branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository#creating-a-branch-using-the-branch-dropdown) for your changes
1. Commit your changes to your branch
    - Small changes can just be made through GitHub's standard web interface
    - If making significant changes, press `.` to open the repository in an online editor, or clone your fork to your local machine and push your commits up to your GitHub repository once they're complete
1. Create a [Draft pull request](https://github.blog/2019-02-14-introducing-draft-pull-requests/) while work is underway, with a link in the description to any issues it resolves or software feature pull requests it documents
1. [Change the pull request to "ready for review"](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/changing-the-stage-of-a-pull-request#marking-a-pull-request-as-ready-for-review) once the underlying software change is merged, the documentation is building successfully, and the new content is ready
1. Fix any requested changes/improvements
1. Once your pull request is merged, update the status/labels of any relevant Issues and software pull requests, or comment on them if you don't have edit access

## Content Improvements
### Documenting a New/Upcoming Feature
> 💡 These can often be found by [searching the software repository](https://github.com/bluerobotics/Cockpit/issues?q=is%3Apull+label%3Adocs-needed) for pull requests with the `docs-needed` label.

0. Ensure your fork's `latest` branch is up to date with this repository
1. Branch out from your `latest` branch into a unique branch, ideally with a short name that reflects its purpose
1. Submit a Draft pull request with your changes, and include "Documents bluerobotics/Cockpit#{PULL-REQUEST}" in the description
    - `{PULL-REQUEST}` is the ID number of the software feature pull request covered by the proposed documentation
    - If your pull request covers multiple features, you can specify "Documents:" followed by a list of software feature pull request links
1. [Ensure your changes can be built](#testing), and (if relevant) clean up your commit history with an interactive rebase
1. Mark your pull request as "ready for review", and fix any requested changes
1. Once your pull request is merged, update the relevant software repository pull request(s) by changing the `docs-needed` label to `docs-complete` or `docs-minimal` as appropriate, or commenting the new documentation state if you don't have edit access to the repository

### Improving/Adding Documentation for Released Features
> 💡 Relevant features can typically be found by looking through the public documentation for features with minimal information, and/or [searching this repository](https://github.com/bluerobotics/Cockpit-docs/issues?q=is%3Aissue+is%3Aopen+label%3Acontent) for issues with the `content` label, or [searching the software repository](https://github.com/bluerobotics/Cockpit/issues?q=is%3Apull+is%3Aclosed+label%3Adocs-minimal) for pull requests with the `docs-minimal` label.

Documentation for existing features should generally first be [added to the `latest` branch](#documenting-a-newupcoming-feature), before optionally being backported to the `stable` and/or any relevant version branches, usually via [`git cherry-pick`](https://git-scm.com/docs/git-cherry-pick).

If your changes were requested in an Issue, make sure to include "Resolves #{ISSUE-NUMBER}" in the description of your pull request, to link to and automatically close the Issue when the pull request is merged.

## Infrastructure Improvements
### Modifying the Documentation Structure
> 💡 Requested features/fixes can be found by [searching this repository](https://github.com/bluerobotics/Cockpit-docs/issues?q=is%3Aissue+is%3Aopen+label%3Ainfrastructure) for issues with the `infrastructure` label.

> ⚠️ As the infrastructure can affect all aspects of the public documentation, it is necessary to ensure that infrastructure changes maintain compatibility with all the content branches, or (if absolutely necessary) update all the content branches with the relevant changes to work with the modified infrastructure.

0. Ensure all branches of your fork are up to date with this repository
1. Branch out from your `latest` branch, and make your desired changes
1. Submit your changes as a Draft pull request, and [ensure that the full documentation is able to build successfully](#testing)
    - If your changes were requested in an Issue, include "Fixes #{ISSUE-NUMBER}" in the description of your pull request to link to and automatically close the Issue when the pull request is merged
1. Submit pull requests to the versioned branches as relevant, to make use of the updated infrastructure
    - Include a link to the infrastructure pull request in the description of any content pull requests, to provide relevant context
1. Mark your pull request(s) as "ready for review", and fix any requested changes

### Modifying the Theme
The theme is maintained in an external repository, and included in this one as a submodule. Zola supports overriding theme components via the "templates" folder, which can be useful for initial testing and any specifics required for the software being documented, but if you want to update the upstream theme used:

1. Fork and branch out from [the theme repository](https://github.com/bluerobotics/bluetheme), and make your desired changes in a Draft pull request
1. Fork and branch out from the `latest` branch of this repository
1. Add your forked theme as a submodule to the "theme" folder of your branch, with a unique name
1. Change the `theme` variable of `config.toml` to match your theme name
1. Generate the docs, to confirm that the theme changes do not break the build process, and the results look as intended
1. Iterate the theme changes as necessary
1. Mark your theme pull request as ready for review
1. Once the theme changes are merged, ensure the theme submodule in the documentation `latest` branch gets updated, along with any relevant changes to the docs configuration, shortcodes, or template
    - The submodule update is generally automatic, via the daily "Update Submodules" Action, but you may need to create a [documentation pull request](#modifying-the-documentation-structure) if there are other changes required

## Testing
### Automatic Generation on Pull Requests
This repository includes continuous integration workflows that will build the documentation automatically in GitHub's servers, both for pull requests and updating the public documentation when new changes get accepted and merged in. This is particularly useful for contributors who don't want to install dependencies or download the repository source to their device, especially when only making small changes, or if you prefer to avoid using commandline tools.

...

### Local Setup
If you frequently contribute to the documentation, you may wish to set things up on your local machine, so you can build and test changes offline and more quickly, and more easily perform complex version history management with git, before pushing the working and clean source back up to your GitHub remote to update your pull request.

0. [Install Zola](https://www.getzola.org/documentation/getting-started/installation/)
1. Clone the content branch you're making changes in
    - e.g. `git clone -b BRANCH https://USER-NAME@github.com/USER-NAME/Cockpit-docs Cockpit-docs-modified`, where
        - `USER-NAME` is your GitHub username
        - `BRANCH` is the name of the content branch you're planning to change
1. Enter the cloned repository and initialise the submodules, to get the theme
   ```sh
   cd Cockpit-docs-modified
   git submodule update --init --recursive
   ```
1. `zola serve` from the base folder of the repository (not inside the "content" folder) to build, and preview your changes
1. Make your changes, and resolve errors/problems as relevant
    - While serving the docs, the preview responds live to changes in the underlying files
1. `git commit` your changes in logical groups
    - e.g. updating the usage overview and advanced sections to describe a single feature should be in a single commit
1. `git push` your changes up to your repository remote
1. Submit a pull request, as covered in the content/infrastructure sections above
