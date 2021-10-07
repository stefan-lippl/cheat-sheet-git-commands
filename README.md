# Cheat-Sheet git commands

## Table of content

<br>

1. Git Configuration
2. Git Init
3. Git Add
4. Git Commit
5. Amend Commit
6. SSH Key Setup
7. Git Push
8. Branches

<br>

# Git Configuration

Define your username / email via

> <code>git config --global user.name "m.mu"</code>
>
> <code>git config --global user.email test@test.com</code>

Enable comand line coloring output via

> <code>git config --global color.ui auto</code>

Check configs via

> <code>git config -l</code>

<br>
<br>

# Git Init

Navigate to the working directory via

> <code>cd <folder_path></code>

Initialize the wd as git repository via

> <code>git init .</code>

<br>
<br>

# Git Add

First check the status of the changes which have been made: Git status shows the the current state of the git wd and staging area. Check via:

> <code>git status</code>

1.  Add a single file to the staging area via

    > <code> git add sarcasm.json </code>

2.  Add all files to the staging area
    > <code>git add . </code>

But, only the files in the current directory and downwards gets added to the staging area. If you are e. g. inside wd/test_folder, only the files in test_folder gets added, not the files in the wd.

If added single file:
If running git status again, the added file should now be in green font-color and ready to be committed. All other files are still red cut they aren't added to the staging area.

If added all files:
All files of the current folder should now be green and ready to commit.

Add all files of the whole working directory, even you are in a subfolder via:

> <code>git add -A</code>

If there is one file which should get removed from the staging area, this can be done via:

> <code>git rm --cached sarcasm.json</code>

If all files should be removed out of the staging area:

> <code>git rm -r -cached .</code>

Again, the new status can be checked with the ~ git status command and the file should be removed out of the staging area.

<br/>
<br>

# Git Commit

Start a commit with all files in the staging area via

> <code>git commit -m "<commit description, e.g., new feature>"</code>

If now use ~ git status again, where should be "nothing to commit, working tree clean" because the changes are already committed.

1. Inspect the commit via

   > <code>git log </code>

2. or in one line via
   > <code> git log --oneline</code>

To show a specific commit, copy the right commit-hash out of the git log and show via

> <code> git show 2c0101f02f8c299969c5bf12df9e81801a61a2ca</code>

Check different content in one file, if changed something in a file after committed it via

> <code> git diff</code>

Now the changes can be committed via ~ git commit. After this you can see the commit in the ~ git log.

For large files (> 100MB) use git Large File System:

https://git-lfs.github.com/

https://www.youtube.com/watch?v=uLR1RNqJ1Mw

Track the large files or even whole directories via

> <code>git lfs track "model_checkpoints/"</code>

See which types of files get tracked via

> <code> git lfs track</code>

Confirm which specific files get tracked via

> <code> git lfs ls-files</code>
