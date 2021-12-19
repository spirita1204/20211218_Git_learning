# Git_learning  
設定快捷縮寫  
```
$ git config --global alias.co checkout  
$ git config --global alias.l "log --oneline --graph"  
```  
查詢目錄下狀態
```
$ git status
```
建立內容為hello之welcome.html檔  
```
$ echo "hello" >welcome.html  
```
讓git開始追蹤(加入到index暫存區)  
```
$ git add welcome.html  
$ git add *.html  
$ git add --all  
```  
將暫存內容提交儲存("做了什麼"),只會處理暫存區的內容  
```
$ git commit -m "init"  
```
檢視紀錄(使用GUI介面檢視相對快)   
```
$ git log #檢視全部資訊
$ git log [file.name] #檢視單一檔案紀錄 (Log Selected)
$ git log -p [file.name] #檢視單一檔案紀錄(詳細)
$ git log --oneline --graph #輸出更為精簡
$ git log --oneline --graph --author="Ding_Hong_Chen" #查詢特定作者編輯  
$ git log --oneline --graph --grep="add" #查詢含特定之標籤
$ git log --oneline --since="9am" --until="12am" --after="2017-01" #查詢特定時間-----2021/12/18
```
砍資料->並更新狀態到暫存區    
```
$ rm welcome.html $ git add welcome.html  
=> $git rm welcome.html
```
取消git控管  
```
$ git rm welcome.html --cached (Stop Tracking)
```
改名  
```
$ git mv a.html b.html 
```
修改commit紀錄(後續還有完整教學)  
```
$ git commit --amend -m "change commit" #修改最後次commit
```
有東西漏track,合併到最後一次commit   
```
$ git add [file.name]
$ git commit --amend --no-edit 
```
新增目錄(git計算,產生物件是根據檔案內容作計算)
```
$ mkdir images 
$ touch images/.keep
# then , add and commit ...
```
有些檔案不想放git內
```
$ touch .gitignore #再編輯要忽略之內容(只忽略建立.gitignore後的資料 不然要先git rm [file.name] --cached)
```
清除.gitignore的檔案
```
$ git clean -fx #f:強制
```
抓兇手
```
$ git blame index.html (Blame Selected)
$ git blame -L 5,10 index.html
```

