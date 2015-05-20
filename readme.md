# GitHub Setup

A quick setup guide to get your project files up on GitHub as quickly as possible using the command line.

## Create a new repository

Before you start, setup a new repository on GitHub.

##  Create your directory structure and files

1. Create a new folder for your project- this will be the location of your local depository.

	```
	$ mkdir ~/development/MoominsRule
	```

2. Navigate to the newly created directory.

	```
	$ cd ~/MoominsRule
	```

3. Make your first commit.
	
	```
	$ git init
	```
	
	```
	Initialised empty Git repository in /Users/Adam/AwesomeWebsite/.git/
	```

4. Create your initial files and directories.
	
	```
	$ mdkir img
	$ touch humans.txt Readme.txt
	$ mkdir css; cd css; touch styles.css; cd ../
	```

## What do your Git eyes see?

Before we commit it's best to see exactly which directories and files Git can see.
	
1. Check what files Git can see.
	
	```
	$ git status
	```

	```
	On branch master

	Initial commit

	Untracked files:
		(use “git add <file>..” to include in what will be committed)

			css/styles.css
			humans.txt
			img/
			readme.txt
	```

2. Make Git take notice of untracked files by either adding multiple files or one-by-one.
	
	```
	$ git add .
	```

	or

	```
	$ git add readme.txt
	```

3. So you can upload an empty directory to GitHub, create a .gitkeep file in each empty directory.

	```
	$ gitkeep
	```

	```
	gitkeep is creating files…
	created ./img/.gitkeep
	finished. 1 files(s) created!
	```

4. Now we have our basic file structure, check what files Git can see before we commit.

	```
	$ git status
	```
	
	You should receive a message that looks something like this:
	
	```
	On branch master

	Initial commit

	Changes to be committed:
		(use “git rm —cached <file>…” to unstage)

			new file: css/styles.css
			new file: humans.txt
			new file: img/.gitkeep
			new file: js/.gitkeep
			new file: readme.txt
	```

5. Now let’s actually make a change by committing our files and directories. 
	
	```
	$ git commit -m “Setup basic file structure”
	```

	Note: anything after “-m” will be read as a message and should be written in the present tense. It’s important to always write clear commit messages to make it easier for other people to follow along and provide feedback.

	```
	[master (root-commit) 53fe028] Setup basic file structure
 	8 files changed, 522 insertions(+)
 	create mode 100644 css/styles.css
 	create mode 100644 humans.txt
 	create mode 100644 img/.gitkeep
 	create mode 100644 js/.gitkeep
 	create mode 100644 readme.txt
	```

6. It’s finally time to push our first commit up to GitHub.