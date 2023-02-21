# Drop Commit:

- For dropping the commit we use `git-reset` command. </br>

Types of reset:
- Hard reset.
- Soft reset.
- Mixed reset.


1. Hard reset: </br>
`git reset --hard commit_id` : uncommit + unstage + delete changes, nothing left. </br>
`git reset --hard HEAD^N`

2. Soft reset:</br>
`git reset --soft commit_id` : uncommit changes, changes are remain in staged (index). </br>

3. mixed reset:</br>
`git reset --mixed commit_id`: uncommit + unstage changes, changes are reamain in working tree. </br>

- Here in this practical i have used hard reset.

1. Commit one update: </br>

    ![p1](/screenshots/p1.PNG)

2. run the reset command: </br>

    ![p1](/screenshots/p2.PNG)

3. after dropping commit: </br>

    ![p1](/screenshots/p3.PNG)