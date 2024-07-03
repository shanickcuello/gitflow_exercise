# gitflow_exercise

_**Based**_ on [atlassian gitflow document](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
The goal of the exercise is to learn the gitflow by practicing it.


Keywords for branch name prefixes are:
- `feature` for feature branches
- `task` for standalone tasks or parts of the feature
- `test` for experiments that are not intended to be merged into `develop`
- `version` for release branches and tags
- `hotfix` for branches that urgently (out of the usuall iteration flow) change the content (code/app) that has already been built\released  

example names:  
- `task/[TaskID-1337]-human-understandable-task-name`  
- `version/1.1`

## Exercises

### A. Prep  
1. Fork this repo, invite participants to collaborate. From now on work in your repos. Prefer working in pairs.  
1. Feel free to update this README.md at any point with any info you consider useful and updating the task's description to be more clear. You will need this at the latest stage.

### B. First feature 
1. "Develop" a feature 
    1. Create a branch for the feature development from the `develop`.
    1. Create a file feature2/contents.txt and write something there.
    1. PR it into the develop (mind the target repo. You want to target your repo, not the source of the fork).
1. "Release" the version
    1. Create a `version` branch.
    1. Update and commit the version number.
    1. Tag the commit.
1. Do the post-release house-keeping
    1. Merge the release branch into `develop`.
    1. Merge the latest release tag into `master` **using fast-forward**. So master would point to the exact commit that has a tag.

### C. Updpate and resolve the conflict
1. Improve feature2
    1. Create a branch from `develop`.
    1. Set feature's text to _"I love code"_. Don't merge it yet.
1. Improve feature2 yet again 
    1. Create a branch from `develop`.
    1. Set it's file text to _"I love git"_. Don't merge it yet
1. PR two feature2 improvements into `develop`. Solve the merge conflict. Two changes should be present in develop, the sentence should be correct.
1. "Release" the version.
1. Do the post-release house-keeping.

### D. Hotfix
1. Create a hotfix
    1. Create a `task` branch from `master`.
    1. Swap the _code_ and _git_ words in feature2
    1. Create a `hotfix` branch from `develop`.
    1. PR `task` into `hotfix`
1. "Release" the version (`version` branch is not needed here sice we have a `hotfix` one)
1. Do the post-release house-keeping

### Z. Improve
1. Create a PR to the original (not forked) repo with changed README.md that holds your updates and clarifications.
