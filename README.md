# git
* man git
* man git-add
* man git-tag

#installation , initialization and configuration
* git init - adds .git folder in the directory, which have all objects etc..
* git config --global user.name
* git config --global user.email
* git config --list
* git config user.name
* git config user.email
* git config -e , git config --local -e , git config --edit -> .git/config
* git config --global -e , git config --global --edit -> ~/.gitconfig
* git config --system -e -> /etc/gitconfig
* git config --global core.editor "code --wait"
* git config --get <key>
* git config --unset <key>
* git config --unset-all <key> - for multiple entries
* git config --remove-section <section>
* git config --global pull.rebase true/false


#porcelain (high level) and plumbing (low level) commands
* plumbing : useful for understanding gits internals
* git cat-file -p <hash>
* git apply
* git commit-tree
* git hash-object

porcelain :
* git status - current status of changes
* git status -s
* git add  
* git add -p
* git commit -am
* git commit -m
* git commit --amend (to edit commit msg but chnages the commit hash)
* git log --oneline --graph
* git log --oneline -p (patch - gives diff also)
* git log --oneline --stat
* git --no-pager log -n 10 --oneline --parents
* git log --decorate=short (default) | git log --decorate=full | git log --decorate=no
* git log branchname
* git log origin/branch
* git log --oneline --graph --decorate --parents 
* git push 
* git pull
* git merge branchname
* git rebase branchname
* git reset --soft commithash
* git reset --soft HEAD~1
* git reset --hard HEAD~1
* git diff --staged
* git diff
* git remote add name uri
* git fetch 
* git merge remote/branch
* git ls-remote
* git reflog (it tracks the HEAD)

#branching - branch is a pointer to a commit
* git branch
* git branch -m oldname newname
* git branch my_new_branch
* git branch -d branchname
* git branch -D branchname
* git switch -c my_new_branch -> -c tells git to create branch it it doesnt exists
* git switch branchname
* gitignore - can add list of files names to ignore by git
* git/info/exclude
* git/HEAD

#content :
* index - the tracked part of changes at a point of time
* commit - a snapshot of whole repo at point of time , commit is not diff of previous commits
* commit sha (min 7)- unique hash, which depends on author,commit message, date and time, parent (previous commit)

* cat-file - gives u , tree hash , authour , commit message , committer -> tree hash will have a blob object with hash(of a file) -> blob object hash will have content
* tree - a git way of storing a directory
* blob - a git way of storing a file

* can not unset a section using config --unset
* /etc/gitconfig -> system, ~/.gitconfig -> global, .git/config -> local, .git/config.worktree -> worktree

* git branch allows u to keep track of diffrent changes seperately
* branch is a pointer to a commit which is cheap
* a ref is a pointer to a commit , all branches are refs but not all refs are branches

* All the data in git is just the files stored in a hidden directory called .git - which includes commits , hashes , tags and other objects etc...
 - .git, .git/config , .git/objects , .git/objects/78
* .git/logs/refs/heads/branchname -> will have a commit of the head of that branch
* git log is not only for local and also can see the remote log

* merge will take all the commits from both branches from merge base commit and after clearing conflicts it will create another commit called merge commit.
* fast forward merge - the branch we are merging onto if the tip of the branch is merge base. 
* rebase - gives linear history , wherever the merge base - rebase makes the top commit of that branch as merge base and then adds the new commits of new branch on top of it. (first it moves the merge base and then it will fast forward merge)

* soft reset will uncommit chnages and keep it in staged while uncommited chnages remains as staged/unstaged as before.
* hard reset will uncommit and undo from staging also and staged chnages will be deleted. untracked will be as is

* remote repo is just an another repo , can be a local repo
* adding a remote to our git repo doesn't mean that we automatically have all the contents , but we need to fetch
* fetch - copies all the contents og .git/objects dir and other infor from repo into current one (but we wont get in local , need to merge)
* we can also merge branches between local and remote 
* github/gitlab is a central place to share ur code and collab with others - is for hosting remotes.
* fork is for copying the repo from owners to our account, not a git operation.



