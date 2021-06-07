## Instructions for developers

* Never commit to the master branch.
* Branch off the master-branch and name the branch as follows:
  * If the fix is a new feature, it should be named as 'feature/name-of-feature'.
  * If the fix is a bug, it should be named as 'bug/name-of-bug'.
* Once the fix is done, create a pull request(PR) to merge into master-branch.
* Add at least two reviewers to the PR: 1) Release Manager(RM) and 2) Person familiar with piece of code changed or added. Adding RM as reviewer is mandatory, second reviewer can be avoided in certain cases.
* It is the responsibility of the second reviewer and/or the developer to resolve merge conflicts (if any) before the code freeze happens.
* Please inform the reviewers via slack to review your PR.
* Please do not merge your PR to the master branch (it is RM's job).
* Link the concerned issue(s) with your PR and document the issue appropriately.
