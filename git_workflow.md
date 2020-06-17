# Git workflow used in this repo

### General workflow

- Create a new code branch with your name or if you want you can create new branches for each different "feature" that you work on. (In this case a "feature" would be a small group of code examples)
- Add and commit your changes
- Push the changes
- Create a pull request
- If the pull request is approved, then you are done! :tada:
- If the pull request reviewer makes some suggestions, asks you to make some changes, then you can continue working on the same branch and commit your changes. They will appear in the same pull request. When you are done, you can let the reviewer know that they can check again.  



### Step by step workflow

1. Update your local version of the repository:

```bash
cd learning-hub
git fetch
```

2. Run the following command to create a new branch: 

```bash
git checkout -b append-examples
```

3. Add your files:

```bash
git add append_example.py
```

4. Commit your changes.

```bash
git commit -m "3 examples for the append function"
```

5. Optional: You can add more files (same as Step 3).
6. Optional: You can make multiple commits (same as Step 4).



7. Push these changes to the repository by running:

```bash
git push origin append-examples
```

Go to the shared repo on GitHub and click on the green 'compare & pull request' button.

Click on 'create pull request'.



### Other commands

Switch to the main branch (this has all the approved changes)

```bash
git checkout master
```

Update your local version

```bash
git pull 
```



### Review and merge a PR

#### You can do this on the GitHub website

or

#### Using the terminal 

**Step 1:** From your project repository, bring in the changes and test.

```bash
git fetch origin
git checkout -b your-branch-name origin/your-branch-name
git merge master
```

**Step 2:** Merge the changes and update on GitHub.

```bash
git checkout master
git merge --no-ff your-branch-name
git push origin master
```



#### Deleting the branch

After (the PR is approved and) the branch is merged into `master`, it's possible to delete the branch:

```bash
git branch -d branch1
```

There are some reasons to keep a branch around though. For example, if it's a feature branch, you may want to be able to do bugfixes on that feature still inside that branch. (See below how to `rebase` the branch.)

#### Rebasing the branch

Often, you might want to make sure that your commits apply cleanly on the remote branch. In this case, you’d do your work in the remote branch and then rebase your work onto `origin/master` when you were ready to submit your patches to the main project. Check out the `your-branch-name` branch, and then rebase it onto the `master` branch as follows:

```bash
git checkout your-branch-name
git rebase master
```

At this point, you can go back to the master branch and do a fast-forward merge.

```bash
git checkout master
git merge your-branch-name
git push origin master
```

This way, we don't have to do any integration work — just a fast-forward or a clean apply.