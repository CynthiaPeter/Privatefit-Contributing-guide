<img width=250px src="https://atsign.dev/assets/img/@platform_logo_grey.svg?sanitize=true">

# Contributing to Priv@tfit

Hi there!
Thanks for your interest in contributing to Priv@tefit.

We 💙 and accept [Pull Requests](https://help.github.com/articles/about-pull-requests/)
for fixing issues or adding features.

Please read our [code of conduct](code_of_conduct.md), which is based on
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.0-4baaaa.svg)](code_of_conduct.md)

### Housekeeping

→ For small changes, especially documentation, you can simply use the "Edit" button
to update the Markdown file, and start the
[pull request](https://help.github.com/articles/about-pull-requests/) process.

→ Use the preview tab in GitHub to make sure that it is properly
formatted before committing.

→ A pull request will cause integration tests to run automatically, so please review
the results of the pipeline and correct any mistakes that are reported.

﹗ **Important:** If you plan to contribute often or have a larger change to make, it is best to
setup an environment for contribution, which is what the rest of these guidelines
describe.

## Development Environment Setup


### Prerequisites

  * Install Dart: https://dart.dev/get-dart
  * Install Flutter: https://docs.flutter.dev/get-started/install


### GitHub Repository Clone

To prepare your dedicated GitHub repository:

1. Fork in GitHub https://github.com/atsign-foundation/REPO
2. Clone *your forked repository* (e.g., `git clone git@github.com:yourname/REPO`)
3. Set your remotes as follows:

   ```sh
   cd REPO
   git remote add upstream git@github.com:atsign-foundation/REPO.git
   git remote set-url upstream --push DISABLED
   ```

   Running `git remote -v` should give something similar to:

   ```text
   origin  git@github.com:yourname/REPO.git (fetch)
   origin  git@github.com:yourname/REPO.git (push)
   upstream        git@github.com:atsign-foundation/REPO.git (fetch)
   upstream        DISABLED (push)
   ```

   The use of `upstream --push DISABLED` is to prevent those
   with `write` access to the main repository from accidentally pushing changes
   directly.
   
### Development Process

1. Fetch latest changes from main repository:

   ```sh
   git fetch upstream
   ```

1. Reset your fork's `trunk` branch to exactly match upstream `trunk`:

   ```sh
   git checkout trunk
   git reset --hard upstream/trunk
   git push --force
   ```

   **IMPORTANT**: Do this only once, when you start working on new feature as
   the commands above will completely overwrite any local changes in `trunk` content.
1. Edit, edit, edit, and commit your changes to Git:

   ```sh
   # edit, edit, edit
   git add *
   git commit -m 'A useful commit message'
   git push
   ```

1. Open a new Pull Request to the main repository using your `trunk` branch
