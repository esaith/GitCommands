## Git Commands
### Update branch with master branch
<br>https://www.git-tower.com/learn/git/faq/git-pull-origin-master
<br>
<br>While on the feature branch
> git pull origin master --rebase

### Delete remote branch
https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-locally-and-remotely
> git push <remote_name> --delete <branch_name>
Example
> git push origin --delete MyBranch

### Local git repostory is out of sync with remote repository for listed --remote branches
When you delete a branch from Azure DevOps, it doesn’t automatically update your local Git repository. The deleted branches still appear when you run git branch --remote because your local Git repository doesn’t know that these branches have been deleted from the remote repository.

To synchronize your local repository with the remote repository, you can prune the deleted branches using the following command:

> git fetch --prune

This command fetches the branches from the remote repository and removes any remote tracking branches which no longer exist on the remote repository. After running this command, if you execute git branch --remote, you should no longer see the deleted branches.

**Remember to be careful** when using git fetch --prune as it will remove all tracking branches that do not exist on the remote repository. If you have any branches that you still need, make sure they exist on the remote repository before running this command.
