# Mod Branch Repository Storage
Some scripts to store mods in branches of a repository whilst being editable through the same .sln file via worktrees.

This was made because when modding, each mod had its own repository which lead me to having 88 repositories at the time of writing. The mods vary in sizes but having a whole repository for one branch for one small feature seemed overkill and disorganized. Developing with the normal branch system was tempting but dealing with stashes was annoying as I would loose track of my changes as I work on different areas at a time. Lastly, combining them all into one repository was considered but then filtering through changes to stage was also annoying. **This system emulates having one solution with different repositories with their own github repositories but, stores the github repositories on branches instead.**

Currently is a work in progress (scripts are a bit of a pain). Theres no guaranteed error checks and you will probably be deleting branches and repositories if something breaks.
And currently with the scripts setup it will only automatically place c# project links into the `.sln` file.

## How to
1. Place template project files into `/Template`

![image](https://github.com/user-attachments/assets/6a2e1f74-0522-482b-8ddc-8020d99e69cb)

The following:
```
[MOD_NAME]
[MOD_AUTHOR]
[MOD_DESCRIPTION]
[MOD_GUID]
```
will be replaced by the scripts.

2. Create a github repository and copy the URL.
3. Run `Create-Repo.ps1` and paste in the URL.
**Make sure to have a template in your templates section. Otherwise an empty branch will be created and the `.sln` file wont be updated with the new project reference.**
Also dont put a space in the mod name. I dont have error handling for it.
5. Run `Create-New-Mod-Branch.ps1` and fill in the name, description and author.

## Public example
Currently using it for my PulsarLostColony public and private mods.
Public : https://github.com/TheRealMesteven/PulsarLostColony-PublicMods/tree/Home
