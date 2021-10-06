In order to pull a new repo, first do `git clone <url>`

Then, in order to pull all branches, you must first create local branches which track the remote branches. 
`git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done`

In order to verify this, we can run the following:
`git remote show origin`

This should show us all the local branches are tracking, pulling, AND pushing to the corresponding remotes.

After this, you can then run `fetch` and `pull` to bring down all the different branches and their code.
`git fetch --all`
`git pull --all`

All branches are now up to date!
