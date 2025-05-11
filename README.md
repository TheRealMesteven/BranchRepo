# Mod Branch Repository Storage
Some scripts to store mods in branches of a repository whilst being editable through the same .sln file via worktrees.

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
4. Run `Create-New-Mod-Branch.ps1` and fill in the name, description and author.
