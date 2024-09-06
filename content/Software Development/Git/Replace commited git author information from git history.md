If you working for multiple projects or companies, you may use different Github logins. If you accidentally commit something as wrong git user, it will be a pain to change the history. If you push it and add more commits on that it will be more painful to revert those changes.

If you search on google, you will see a lot of solutions. Most solutions are not straight forward, you have to spend few minutes to hours to realize the solution because of many CLI commands and copy pastings. But did you know that you can replace author name and email in the entire git history with a script?

You don’t need to use git CLI commands to change the author's name and email in the commit history. You can just run a script to replace all the commits assigned to the wrong git author.

The following illustration shows the high-level solution. Using a script, you can replace the author. This script will

- not change committed dates
- not change committed messages

#### *Warning* - This will change the git hashes of the commits

### Step (1/4): Create a fresh, bare clone of your repository

Bar clone means it does not have a git working directory. It has only .git data.  

```
git clone --bare https://github.com/user/repo.git
cd repo.git
```

### Step (2/4): Create script.sh file, update and execute

Open this script and change following OLD_EMAIL, CORRECT_NAME & CORRECT_EMAIL  

```
#!/bin/sh

git filter-branch --env-filter '

OLD_EMAIL="your-old-email@example.com"
CORRECT_NAME="Your Correct Name"
CORRECT_EMAIL="your-correct-email@example.com"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
export GIT_COMMITTER_NAME="$CORRECT_NAME"
export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
export GIT_AUTHOR_NAME="$CORRECT_NAME"
export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```

Give executable permissions: You need permission to execute the shell script. You need to give executable permission  
`sudo chmod 755 script.sh`

Let's run:Time to run the shell script. This script will not push those changes to your origin. So, you can review after executing.  
`./script.sh`

### Step (3/4): Review your git log

Check author name, email, and commits messages.  

```
git log
git log --decoreate --oneline      # one line log
```

### Step (4/4): Push to Github

Check twice before you run the following command.  
`git push --force --tags origin 'refs/heads/*'`

## 👿Warning👿 - Once you run this script, your commit hashes will be changed

[![Alt Text](https://res.cloudinary.com/practicaldev/image/fetch/s--tePWec5t--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/0rftwae2m2r5z7u098ja.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--tePWec5t--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/0rftwae2m2r5z7u098ja.png)p

because of hash changes - When you get a git pull, you will see something like this  
[![Alt Text](https://res.cloudinary.com/practicaldev/image/fetch/s--FLFmX2HT--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/26xfpd27sdzpsgd8k5f2.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--FLFmX2HT--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/26xfpd27sdzpsgd8k5f2.png)

Your git users will have to run following command to avoid that issue  

```
git pull --allow-unrelated-histories
```

> Also see [[Change Git user for a specific repo]] if it makes useful for u 

> Very useful and works properly.
> Got it from https://dev.to/deshanm/replace-accidentally-committed-git-author-information-from-git-history-15dk 

