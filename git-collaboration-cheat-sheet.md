Step 1: Initializing a Git repositorycsharp

```csharp
git init
```

This command initializes a new Git repository in the current directory. If the project is already created in IntelliJ or any other IDE with Git integration, you don't need to run this command.

Step 2: Adding a remote repositorycsharp

```csharp
git remote add origin &lt;Github URL&gt;
```

This command adds a remote repository with the given GitHub URL. The "origin" is a commonly used name for the remote repository, but you can choose a different name if desired.

Step 3: Staging changescsharp

```csharp
git add .
```

This command stages all the changes in the current directory for the next commit. The dot (.) represents all files in the current directory.

Step 4: Committing changessql

```sql
git commit -m "Test"
```

This command creates a new commit with the staged changes. The "-m" flag allows you to provide a commit message, which should briefly describe the changes made in this commit.

Step 5: Pushing changes to the remote repositoryperl

```perl
git push origin master
```

This command pushes the committed changes to the remote repository's "master" branch. It uploads your local commits to the GitHub repository.

Step 6: Creating a new branchcss

```css
git checkout -b feature1
```

This command creates a new branch named "feature1" and switches to that branch. You can replace "feature1" with any desired branch name.

Step 7: Making changes on the new branch
Here, you can work on the changes specific to the "feature1" branch. Modify files, add new files, etc.

Step 8: Updating the branch with changes from the master branch```git pull origin master

````

This command fetches and merges the latest changes from the remote repository's "master" branch into the current branch ("feature1" in this case). It ensures that your branch is up to date with the latest changes.

Step 9: Staging and committing changes on the branchsql
```sql
git add .
git commit -m "Test"
````

These commands stage the changes made on the branch and create a new commit with the provided commit message.

Step 10: Pushing changes to the branch on the remote repositoryperl

```perl
git push origin feature1
```

This command pushes the committed changes on the local branch to the remote repository's "feature1" branch.

Step 11: Initiating a pull request
At this point, you would typically go to the GitHub repository's web interface, create a pull request, and compare the changes in the "feature1" branch with the "master" branch. Reviewers can provide feedback and ultimately merge the changes into the main codebase.

Step 12: Deleting the branch from GitHub
Once the pull request is merged, you can delete the "feature1" branch from the GitHub repository using the web interface.

Step 13: Switching back to the master branch```git checkout master

````

This command switches back to the "master" branch.

Step 14: Deleting the local branchmathematica
```mathematica
git branch -D feature1
````

This command deletes the local branch named "feature1." Be cautious when deleting branches, as it permanently removes the branch and its commits.

Step 15: Updating the local master branch with the latest changes from the remote repository```git pull origin master

```

This command fetches and merges the latest changes from the remote repository's "master" branch into the local "master" branch. It ensures that your local branch is up to date with the latest changes made by others.

Please note that these instructions assume you have Git properly installed and configured on your system.
```
