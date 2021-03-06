# Preparing a pull request

Copied from the [p5.js repository](https://github.com/processing/p5.js).

Pull-requests are easier when your code is up to date! You can use git rebase to update your code to incorporate changes from other contributors. Here's how.

## Save and Update

### Save everything you have! 
    git status 
    git add -u
    git commit 


### Find out about changes
Make sure you're tracking upstream p5.js repository.

    git remote show upstream

If you see an error, you'll need to start tracking the main p5.js repo as an "upstream" remote repository. You'll only need to do this once! But, no harm is done if you run it a second time.

    git remote add upstream https://github.com/processing/p5.js

Then ask git about the latest changes.

    git fetch upstream 

### Just in case: make a copy of your changes in a new branch
    git branch your-branch-name-backup 

### Apply changes from master branch, adds your changes *after* 
    git rebase upstream/master 

## CONFLICTS
You will probably have some conflicts! 
If it’s just lib/p5.js and lib/p5.min.js, it’s easy to fix. just build the project again with grunt.

    grunt 
    git add -u
    git rebase --continue

If you have conflicts in other files & you're not sure how to resolve them... ask for help! Lauren, David, Kevin, and Kate are familiar with recent changes and can help you figure out what's new.

## And finally, for great glory
    git push origin

Here's a good reference on rebasing, in case you're intensely curious about the technical details. https://www.atlassian.com/git/tutorials/merging-vs-rebasing