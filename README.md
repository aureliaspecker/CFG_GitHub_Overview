# Using Git & Version Control with your command line

Use the below commands to use Git and GitHub in your command line.

## Instructions

### Creating a repository

Open Terminal.

Navigate to the directory that contains the local project you want to intialize with Git. To navigate in terminal, use the commands `cd` (change directory) and `ls` (list): [click here](https://openclassrooms.com/en/courses/4614926-learn-the-command-line-in-terminal/4634356-navigate-your-system) for more explanations on this.

Intialize the local directory as a Git repository and adding your project to GitHub.

```
$ git init
```

[Add the files](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/) in your new local Git repository. This stages (i.e. prepares) these files for the first commit.

```
$ git add .
```

Commit the files that you've staged in your local repository. The following command commits the tracked changes and prepares them to be pushed to a remote repository.

```
$ git commit -m "Make first commit"
```

Open GitHub in your browser and create a repository. **Do not select Create with Readme**. At the top right hand of your GitHub repository's Quick Setup page, copy the remote repository URL.

In Terminal, [add the URL for the remote repository](https://help.github.com/articles/adding-a-remote/) where your local repository will be pushed.

```
$ git remote add origin URL-of-remote-repository
```

Origin stands for the repository that sits online in GitHub.

[Push the changes](https://help.github.com/articles/pushing-to-a-remote/) in your local repository to GitHub.

```
$ git push -u origin master
```

### Creating a branch

It's considered good practice to avoid working in the master (i.e. main) branch of the repository and to create a branch to work on. A branch is basically a copy of your master branch. Different people can work on different branches in parallel before merging everything into the master branch.

Brefore creating a new branch, make sure your master branch is up to date by pulling the changes from upstream.

```
$ git pull
```

Create the branch on your local machine and switch in this branch.

```
$ git checkout -b give-your-new-branch-a-name
```

You can check what branch you're currently in, by running the following command.

```
$ git branch
```

This will show you something like this. The * indicates which branch you're in.

```
* aurelias_branch
  master
  master_clean
```

To change branches.

```
$ git checkout name_of_branch_you_want_to_go_to
```

### Adding files and commiting changes

When you've made some changes to your branch and you want to commit them, start staging your work for commit.

```
$ git add .
```

To see what files have been staged, use the following command.

```
$ git status
```

Commit the files that you've staged locally and add a commit message.

```
$ git commit -m "Add a meaningful commit message"
```

### Pushing your repository to your GitHub account online

Pushes the changes in your local repository up to the remote repository you specified as the origin on GitHub.

```
$ git push origin name-of-branch-you-want-to-push-to-GitHub
```

### Cloning a repository

On GitHub online, go to the main page of the repository. Under the repository name, click Clone or download. In the Clone with HTTPs section, copy the clone URL for the repository.

Open Terminal.

Change the current working directory to the location where you want the cloned directory to be made.

Type `git clone`, and then paste the URL you copied above.

```
$ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

Press Enter. Your local clone will be created.

```
$ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
Cloning into `Example-File`...
remote: Counting objects: 10, done.
remote: Compressing objects: 100% (8/8), done.
remove: Total 10 (delta 1), reused 10 (delta 1)
Unpacking objects: 100% (10/10), done.
```
[More information](https://help.github.com/articles/cloning-a-repository/)


### Merging a branch back into your master branch

Open Terminal.

Make sure you have navigated to your project.

Check out the branch you wish to merge to. Usually, you will merge into `master`.

```
$ git checkout master
```

Pull the branch you wish to merge into the master branch from the upstream repository.

```
$ git pull https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git BRANCH_NAME
```

If there are conflicts, resolve them. For more information, see [Addressing merge conflicts](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/).

Commit the new version of the master branch after the merge.

Review the changes and ensure they are satisfactory.

Push the merge to your GitHub repository.

```
$ git push origin master
```
