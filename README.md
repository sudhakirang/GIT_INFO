# GIT_INFO
Frequently used GIT commands in my workflow with short descriptions and syntaxes



    1. Git clone: One time setup
used for initial clone from the remote repository to a local repository. From the local repository to work location folder use git checkout (which is already created, if you want to create the branch and switch to that at this moment in the working location use git checkout -b).
    Used when: You're starting to work with a repository for the first time.
    What it does:
        • Downloads all files, commit history, and branches from the remote repository.
        • Initializes a new Git project on your machine.
        • Automatically sets the remote (usually named origin).
    Syntax: git clone <remote-repo-URL>
    
    2. Git pull: Regular synching
    Which bring in the new changes from remote to already cloned code in the working folder. It can happen in 2 steps, they are: git fetch (from remote to local) and git merge (from local to working folder).
    Used when: You've already cloned the repo earlier and want to bring in new changes.
    What it does:
        • Fetches the latest commits from the remote branch.
        • Merges them into your current local branch.
    Syntax: git pull origin <branch-name>
    
    3. Git commit: save changes locally
    It records changes taken from the working directory through git add to a local repository. Due to this the changes are not yet visible to others.
    Syntax: git add <file_name> 
           git commit -m "message"

    4. Git push: upload changes to remote
    To upload your committed changes to a remote repository. Such that anyone who are using the same repo can view the changes. 
    Syntax: git push origin <branch_name>
    
    5. Git branch: pointer to a specific commit
    Used to work on features, bug fixes or experiments without affecting the main branch
        a. Git checkout -b <branch_name>: create and switch to a new branch.
        b. Git branch <branch_name>: create and be stay in the current branch only
        c. Git checkout <branch_name>: switch to the branch name (created in b.)
        d. Git switch -c <branch_name>: create and switch to the new branch used in the newer version of git (>2.23+)
        e. To view branches:
            i. Git branch: shows local branches
            ii. Git branch -r: shows all remote branches
            iii. Git branch -a: shows all branches (remote and local).

    6. Git cherry-pick: copy a specific commit to another branch
    Allows you apply a specific commit from one branch into another, without merging the whole branch.
    Syntax: git cherry-pick <commit-hash>
    Example: git cherry-pick e5a1c4d this creates a new commit in main with the same changes as the selected commit.
    We can also commit a range of commits git cherry-pick <start_commit>^…..<end_commit> 
    Note: i.  '^' represents inclusion of the first commit. 
        ii. If conflict arises while using the cherry-pick, git pause the operation and ask for resolve after resolving the conflict then use the following commands to continue the cherry-pick operation
                1) Git add <file>
                2) Git cherry-pick --continue
        iii. Careful while using the cherry-pick in the long-lived branches, since it can create duplicate commits if we not managed well. 
        iv. After the commit, to check its status weather committed or not use git log (to view commit history)/git status/graph status in VS code/git push origin main (to see the new commit)

    7. Git rebase: Rewriting history to make a cleaner, linear commit history.
    Used to move, reorder, or replay commits from one branch onto another. It's a powerful alternative to git merge, especially when you want to keep your history linear and clean.
    
    8. Git merge: Combine changes from one branch into another
    Takes the changes from one branch (source) and integrates them into the current branch (target). It preserves all history and adds a merge commit if needed.

    9. Git Stash: Allows you to temporarily save changes in your working directory without commiting them. Useful when you need to switch branches/work on something else but do not want to loose/commit your unfinished changes.
