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
Rename / change a commit   
```git commit --amend```   
```git push --force-with-lease origin yourBranchName```    
Clone repository using token ( token need Full control of private repositories ).   
```export GITHUB_USER=matteo-marcolini```.  
```export GITHUB_TOKEN=<yourclassictoken>```.  
```export GITHUB_REPOSITORY=teomarcdhio/radio```.  
```git clone https://${GITHUB_USER}:${GITHUB_TOKEN}@github.com/${GITHUB_REPOSITORY}```.  




