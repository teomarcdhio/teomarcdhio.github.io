---
layout: default
title: Git Commands
parent: Git
nav_order: 1
---
### Git commands

Squash the last two commits  
```git rebase -i HEAD~2```  
```git push -f```  
Rebase from main  
```git rebase main yourBranchName```   
Delete a local branch  
```git branch -D yourBranchName```   
Cherry pick commit 63162ea    
```git cherry-pick 63162ea```  
Tag a branch and publish it   
```git tag <tagname>```  
```git push origin --tags```     
