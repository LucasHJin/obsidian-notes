2025-03-31 09:17

Status:


Tags:
[[personal website]] 
[[cs]] 


___________________________________________________________________________
# Setting up Git for Obsidian

1. Download the *Git* plugin from community plugins and enable it
2. Navigate on Github:
	1. Github -> Settings -> Developer Settings -> Personal Access Tokens
3. Create a PAT with repo perms lasting forever
4. **Copy it** - you will not get another chance
5. Add your perms in the local terminal:
```
git config --global user.name "Your GitHub Username"
git config --global user.email "your-email@example.com"
```
6. In terminal, navigate to the vault's folder and paste the following text in (replacing where appropriate): 
`git remote set-url origin https://USERNAME:PAT@github.com/USERNAME/REPO.git`
7. In the same terminal, enter the following commands
```
git add .
git commit -m "COMMIT MESSAGE - FOR YOU TO ENTER"
git push -u origin main
```
8. From here, any time you want to commit, in the command panel for Obsidian you can choose:
```
Git: Push
Git: Commit all changes with specific message
```
9. *Optional:* You can also choose to set continuous commits and pushes/pulls in the Git community plugin section in settings

**Remember to make an existent repo folder** 


# References
https://forum.obsidian.md/t/the-easiest-way-to-setup-obsidian-git-to-backup-notes/51429
https://publish.obsidian.md/git-doc/Start+here
https://publish.obsidian.md/git-doc/Getting+Started