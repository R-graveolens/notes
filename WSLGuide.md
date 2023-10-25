# How to Dev on WSL 2

## Git
### Initialization 
First, initialize Git in the folder where we want to keep a record.
```
> cd <folder>
> git init
```
Write or edit a file ( ex. readme.md ) in the folder, then

* use `git add` to tell Git to add the modifitions (= staged) into repo.
    ```
    > git add <file>
    ```
* use `git commit` to instruct Git to commit the files to the repo.
    ```
    > git commit -m <comment>
    ```
    The text provided after the '-m' flag is used to input a description for this particular commit, describing the purpose or content of the changes made in this commit.

###