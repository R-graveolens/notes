# How to Dev on WSL 2

## Git

### Initialization

First, initialize Git in the folder where we want to keep a record.

```zsh
> cd <folder>
> git init
```

### Version Control

#### Tracking Modifications

Distinct three "spaces" : Working directory and Stage and Repository of version.

Write or edit a file in the folder ( modifications in working directory ), then

* use `git add` to tell Git to add the modifitions (into Stage).
  
    ```zsh
    > git add <file>
    ```

* use `git commit` to instruct Git to commit the files to the Repo of version of git.

    ```zsh
    > git commit -m <comment>
    ```

    The text provided after the '-m' flag is used to input a description for this particular commit, describing the purpose or content of the changes made in this commit.

**Rk: Not necessarily one `git add` followed by one `git commit`.**
Tracking changes, first modification -> `git add`-> second modification -> `git add` -> `git commit` (committing both modifications merged together).

If we've done some edits or modifications but haven't staged or committed them:

* `git status` can display the status in both working directory and Stage space.

* If `git status` informs you that files have been modified, you can use `git diff <file>` to view the changes made. Knowing what changes have been made to file, it's much more reassuring to commit it to the repository. Committing changes and adding new files are the same two steps.
* `git checkout -- <file>` : discard changes in Working directory.
* `git reset HEAD <file>` : Unstage and return the modifications back to Working directory. (Then can `git checkout -- <file>` to discard it).

#### Version Time Travel

* The version pointed to by `HEAD` is the current version, so Git allows us to travel between versions in history using the `git reset --hard commit_id` command.

* Before traveling, you can use `git log` to view the commit history to determine which version you want to roll back to.
  
* To return to the future, use `git reflog` to view the command history to determine which version in the future you want to return to
![Alt text](image/WSLGuide/image.png)

#### File Delete

After deleting files in the working directory, `git status` can inform you about the deleted files.

1. To permanently delete these files: Use git rm followed by git commit.
2. To recover: `git checkout -- <file>`.
   