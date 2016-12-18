# git-issues

### [在Git中新增一個標籤到某筆Commit紀錄](http://chshman310222.pixnet.net/blog/post/172006035-%5B%E7%89%88%E6%8E%A7%5D-%E5%A6%82%E4%BD%95%E5%9C%A8git%E4%B8%AD%E6%96%B0%E5%A2%9E%E4%B8%80%E5%80%8B%E6%A8%99%E7%B1%A4%E5%88%B0%E6%9F%90%E7%AD%86commit%E7%B4%80)
###新增標籤的指令為：   
git tag -a <標籤名稱> <該筆提交紀錄的檢查碼前6~8碼(不用全部)>   
git push origin --tags   

###刪除標籤的指令為：   
Local端  =>　git tag -d 標籤名稱   
Remote端 =>  git push origin :refs/tags/標籤名稱   
    
   
### [Git Can't push because I locally committed a file that is too large](http://stackoverflow.com/questions/35947835/cant-push-because-i-locally-committed-a-file-that-is-too-large) 
  
  $ git rebase -i origin/master master   
  
If your bad commits are only an add of big files, just delete them deleting the concerned lines in the rebase todo file.  
  
If your big files belong to a more complex commit, use "edit" option in the rebase todo file on each concerned line. When the rebase operation stops just after the commit to amend:  
 
  $ git rm bigFile1 bigFile2  
  $ git commit --amend  
  $ git rebase --continue  
 
Terminate the rebase, resolving all conflicts if necessary.  

Finally, push again.  

  $ git push 
