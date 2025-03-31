2025-03-31 09:17

Status:


Tags:
[[personal website]] 
[[cs]] 


___________________________________________________________________________
# Setting up Git for Obsidian

**Step 1 - Setup Authentication with HTTPS**
1. Github -> Settings -> Developer Settings -> Personal Access Tokens
2. Create a PAT with repo perms lasting forever
3. **Copy it** - you will not get another chance
4. Add your perms in the local terminal:
```
git config --global user.name "Your GitHub Username"
git config --global user.email "your-email@example.com"
```
5. In terminal, navigate to the vault's folder and paste the following text in (replacing where appropriate): 
`git remote set-url origin https://USERNAME:PAT@github.com/USERNAME/REPO.git`



# References
https://forum.obsidian.md/t/the-easiest-way-to-setup-obsidian-git-to-backup-notes/51429
https://publish.obsidian.md/git-doc/Start+here
https://publish.obsidian.md/git-doc/Getting+Started