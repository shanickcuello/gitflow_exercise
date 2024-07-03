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
    1. Create a PR targeting the `develop` (**mind the target repo.** You want to target your repo, not the source of the fork).
    1. Approve the PR and merge it via creating a merge commit.
    1. Make sure that the feature branch is deleted.
1. "Release" the version
    1. Create a `version` branch from `develop`.
    1. Update and commit the version number (`version.txt` file).
    1. Tag the commit.
1. Do the post-release house-keeping
    1. Merge the release branch into `develop`.
    1. Merge the latest release tag into `master` **using fast-forward**. So `master` branch would point to the exact commit that has a tag.

### C. Updpate and resolve the conflict
1. Improve feature2
    1. Create a branch from `develop`.
    1. Set feature's text to _"I love code"_. Don't merge it yet.
1. Improve feature2 yet again 
    1. Create a branch from `develop`.
    1. Set it's file text to _"I love git"_. Don't merge it yet
1. Create and merge a PR for each feature2 improvement into `develop`.  
Resolve the merge conflict. Two changes should be present in `develop` in one sentence. The sentence should be grammatically and punctuationally correct. (This will require manual conflict resolution)
1. "Release" the version. (See part B-2 for the details)
1. Do the post-release house-keeping. (See part B-3 for the details)

### D. Hotfix
1. Decide that you want a hotfix
    1. Create a `hotfix` branch from `master`. (Mind that you want that branch name to contain the upcoming hotfix version number)
1. Make changes
    1. Create a `task` branch from `hotfix`.
    1. Swap the _code_ and _git_ words in feature2 (ex: If it was "I love code and git" it should become "I love git and code")
    
    1. PR `task` into `hotfix`
1. "Release" the version 
    1. `version` branch creation is **not** needed here sice we have a `hotfix` one
    1. Update and commit the version number (version.txt file).
    1. Tag the commit.
1. Do the post-release house-keeping

### Z. Improve
1. Create a PR to the original (not forked) repo with changed README.md that holds your updates and clarifications.
