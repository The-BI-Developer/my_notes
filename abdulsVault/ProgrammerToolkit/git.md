WHEN GIT REMOTE FAILS

ROOT cause: 
	git remote add origin git@github.com:The-BI-Developer/taimour.git
	git push -origin master #this will fail due to authentication failure
	ERROR: git@github.com: Permission denied (publickey).	
	
Checking CONNECTION:
	ssh -T git@github.com
Starting SSH-AGENT
	eval "$(ssh-agent -s)"


1. Generate a new SSH key:
	ssh-keygen -t ed25519 -C "abdul.w1337@gmail.com"
	
	eval "$(ssh-agent -s)" #start ssh agent
	ssh-add ~/.ssh/id_ed25519 #add ssh private key to ssh-agent

2. Adding key to GITHUB account
	cat ~/.ssh/id_ed25519.pub #copy contents
	
	Add SSH key in settings of github account

ADDING REMOTE REPO
$ git remote add origin https://github.com/OWNER/REPOSITORY.git
# Set a new remote

$ git remote -v
# Verify new remote
> origin  https://github.com/OWNER/REPOSITORY.git (fetch)
> origin  https://github.com/OWNER/REPOSITORY.git (push)

#MODIFY REMOTE URL
git remote set-url [remote name e.g. origin/upstream] [new SSH/HTTPS url]

#UNDO A MERGE
git reset --hard HEAD~1

#DELETE A BRANCH
git branch --delete <banch_name>

#MODIFYING A COMMIT
What you want is to either do a "git commit --amend" to modify your old commit if you've not already created a fresh commit with your changes.

If you've already created a fresh commit, you'll want to use "git rebase -i" to squash your commit on top of the old one.

#NAMING CONVENTIONS
	EVery team has their own convention!
	(1) Convention 1
	regular branches
		dev branch: new feature or bugfixes, not related to production branch!
		master branch (default): stable version
		qa: automation and testing
		staging: demo or proposal (decide to bring to production)
	temp branches
		bug fix - rejected from feature branch for fixing
		hotfix - temp patch
		feature branch: new use case or module
		experimental branch - playground
		wip branch - work in progress
	(2) Convention 2
		git branch <category (select below)/reference/kebabcase_descp>
			feature - adding, refactor, remove (arr)
			bugfix - duh
			hotfix - temporal solution
			test - experimenting outside the project (playground)

		git commit -m <category (select below): statement1;statement2> #verb conjugated in imperative way e.g. add, rewrite,refactor
			refactor - modify for convenience, performance, readibility
		        feat - new feature
			fix - fix a bug
			chore - for everything else

#CLONED ACCINDENTLY USING HTTPS INSTEAD OF SSH LEADING TO AUTH ERRORS	
git remote set-url origin git@github.com:The-BI-Developer/<MY-REPO>.git



#GIT TAGGING
git tag #view tags
git show <my_tag> #show info on tag
git tag -a <my_tag> -m "" #annotated
git tag <my_tag> #lightweight
git tag -a <my_tag> commit_checksum

git checkout <tag> #results in detached head state

git tag --delete <my_tag>

#tags can only reference checksums = equal to release in github (diff terminology)




