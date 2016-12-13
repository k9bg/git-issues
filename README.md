# git-issues


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
