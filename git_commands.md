---
layout: default
title: Git Commands
parent: Git
nav_order: 1
---
### Git commands

Squash the last two commits  
```git logs```   
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
Show last commits    
```git logs```    
Show branch details   
```git show-branch``` 
Rename a branch   
```git branch -m oldbranchname newbranchname```   
Delete remote branch   
```git push origin --delete oldbranchname```    
Push renamed branch   
```git push origin -u newbranchname```   



