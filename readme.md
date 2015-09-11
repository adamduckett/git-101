# Git 101

A no bullshit guide to getting a project on GitHub.


## #1 Creating or cloning a repository

We need to either create a new repository or clone an existing one.


### Create a new repository

Create a new directory, add some files and execute:

```
	$ git init
```

to create a new git repository.


### Or, clone an existing repository

To create a local copy of an existing GitHub repository:

```
	$ git clone [https://github.com/username/project.git]
```

This will create a working copy of the repository on your machine.


## #2 Checking Git's status

It's now a good idea to see what Git files Git can see:

```
	$ git status
```

Any 'untracked' files need to be added, we'll do that next.


## #3 Adding changes

Your files are currently untracked by Git; we'll make Git take notice of them with:

```
	$ git add <filename>
```
```
	$ git add .
```

This will add your proposed changes to the **Index**.


## #4 Committing changes

To actually commit your changes, use:

```
	$ git commit -m "Commit message"
```

Your files are now committed to the **HEAD**, but are not in your remote repository yet.


## #5 Pushing changes

Finally, ypi need to push your changes from the **HEAD** of your local working copy and send them to your remote repository on GitHub.


### I din't clone no repo, honest!

If you didn't clone an existing repository earlier you first need to add the remote server you wish to push to before you can push your changes to the server:

```
	$ git remote add origin [https://github.com/username/project.git]
```


### I cloned the heck outta that repo!

If you did clone an existing remote repository simply execute:

```
	$ git push origin master
```

Make sure _master_ is whatever branch you want to push your changes to. If you're riding solo on a project this will likely always be _master_.


## #6 Branching off

Branches are handy for working on a project independently without affecting other developers' shit. You can then merge your changes back to the master branch when you're done.


### Create (and switch to) a new branch

To create a new branch called "awesome_feature" and swith to it, use:

```
	$ git checkout -b awesome_feature
```

### Switch back to master

You can switch back to the master branch with:

```
	$ git checkout master
```

### Deleting a branch

To delete the "awesome_feature" branch:

```
	$ git branch -d awesome_feature
```

### Make your branch available to other developers

Your branch is only of use to you unless you push it to your remote repository. Push your "awesome_feature" branch with:

```
	$ git push origin awesome_feature
```


## #7 Updating & merging

To update your local repository to the most recent commit you can use:

```
	$ git pull
```

This will fetch and merge remote changes to your working directory. Handy, huh?


### Merging branches

You can also merge your "awesome_feature" branch into your active branch (e.g. master) with:

```
	$ git merge awesome_feature
```

### Dealing with conflicts

Sometimes Git isn't able to automatically merge your changes. If this happens you are responsible for merging any _conflicts_ yourself manually by editing the files Git flags up.

After making your changes, you need to mark them as merged with:

```
	$ git add <filename>
```

### Previewing changes before merging

If you would like to preview your changes before merging use:

```
	$ git diff <source_branch> <target_branch>
```

## #8 Renaming a repository

When you rename a repository, all existing information is automatically redirected to the new name (e.g. _Issues_, _Wikis_, _Stars_ and _Followers_).

All web traffic will be redirected and all `git clone`, `git fetch`, or `git push` operations targeting the previous location will continue to funtion.

However, it's recommended to update any existing local clones to point to the new repository URL with:

```
  $ git remote set-url origin <new_url>
```