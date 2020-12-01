##命令
---
id: git-commands
title: Git command Doc
sidebar_label: Git command Doc
---

| Name | Discription |
|------|-------------|
| git --version | 檢視⽬前所使⽤的 Git 版本	|
| cd /tmp | 切換到 /tmp ⽬錄（絕對路徑） |
| cd my_project | 切換到 my_project ⽬錄（相對路徑） |
| cd .. | 往上⼀層⽬錄移動 |
| cd ~/project/namecards/ | 這個 "~" 符號表⽰ home ⽬錄 |
| pwd | 顯⽰⽬前所在⽬錄 |
| ls -al | 列出在⽬前⽬錄所有的檔案及⽬錄，後⾯接的 -al 參數， a 是指連⼩數點開頭的檔案（例如.gitignore）也會顯⽰， l 則是完整檔案的權限、擁有者以及建立、修改時間 |
| touch index.html | 如果 index.html 這個檔案本來不存在， touch 指令會建立⼀個名為 index.html 的空⽩檔案；如果本來就已經存在，則只會改變這個檔案的最後修改時間，不會變更原本這個檔案的內容。 |
| mkdir demo | mkdir 指令會在⽬前所在⽬錄，建立⼀個名為 demo 的⽬錄 |
| cp index.html about.html | 把檔案 index.html 複製⼀份成 about.html |
| mv index.html info.html | 把檔案 index.html 更名成 info.html |
| rm index.html | 刪除檔案 index.html |
| rm *.html | 刪除在這個⽬錄裡所有的 html 檔 |
| git config --global < user name > | 設定作者名稱，如果將global 換成local 則會將特定特定的專案設定不同的使用者	|
| git config --global < user email > | 設定作者Email 信箱，如果將global 換成local 則會將特定特定的專案設定不同的使用者 |
| git config --list | 檢視Git 設定 |
| git config --global core.editor < editor command name > | 換預設編輯器 |
| git config --global < alias name > < git command > | Git 設定縮寫，方便輸入快速 |
| git init | 主要⽬的是要讓 Git 開始對這個⽬錄進⾏版本控制 |
| git status | ⽤來查詢現在這個⽬錄的「狀態」 |
| git add < file name > | 讓 Git 開始「追蹤」指定檔案，站存區的概念 |
| git add . | 讓 Git 開始「追蹤」目錄下的所有檔案，站存區的概念 |
| git add -all | 讓 Git 開始「追蹤」所有檔案，站存區的概念 |
| git add -p < file name > | 加上 -p 參數後， Git 會問說是不是要把這個區塊(hunk)加到暫存區，如果選 y 就是整個檔案加進去。如果只想送出部份內容，選擇 e 選項 |
| git add -f < file name > | 無視忽略規則，直接將此檔加入追蹤 |
| git commit -m < comment >| 將檔案加入永久區的概念	|
| git commit --allow-empty -m "空的" | 只要加上 --allow-empty 參數，沒 commnt 也是可以 Commit	|
| git commit -a -m < comment > | 這樣即使沒有先 add 也可以完成 Commit，但要注意的是這個 -a 參數只對已經存在 Repository 的檔案有效 |
| git log | 查詢 log |
| git log --oneline | 查詢精簡化 log |
| git log --author= < user name1 > \| < user name2 > | 尋找特定 User 的 log，同時可以再⽤ | (中⽂「或者」的意思) 來查詢多個 User |
| git log --grep= < search text > | 使⽤ --grep 參數，可以從 Commit 訊息裡⾯搜尋符合字樣的內容 |
| git log -S < search text > | 使⽤ -S 參數，可以搜尋在所有 Commit 的檔案中，哪些符合特定條件的 |
| git log --since="9am" --until="12am" --after="2017-01" | 查歷史資料的時候，可以搭配 --since 跟 --until 參數查詢，還可以再加⼀個 after 就可以找出 after 所指定日期之後的 commit |
| git log -p < file name > | 查詢指定檔案的詳細 log |
| git rm < file name > | 直接 commit 要刪除的檔案	|
| git rm < file nam > --cached | 將指定檔案從 git 移除控管 |
| git commit --amend -m < comment > | 要修改最後⼀次的 Commit 訊息，只要直接在 Commit 指令後⾯加上 --amend 參數即可 |
| git commit --amend --no-edit | 這樣就可以把檔案併入最後⼀次的 Commit 。⽽最後⾯那個 --no-edit 參數的意思是指「我不要編輯 Commit 訊息」，所以就不會跳出 Vim 編輯器的視窗 |
| git clean -fX	| 強制清除那些被忽略的檔案 |
| git blame -L < from number >,< to number > < file name > | 找出程式碼每行作者 -L 可以指定行數 |
| git checkout < file name > | 救回檔案 |
| git checkout . | 救回全部檔案 |
| git checkout HEAD~2 | 拿距離現在兩個版本以前的檔案來覆蓋現在⼯作⽬錄的檔案，同時也更新暫存區裡的狀態 |
| git checkout --ours < file name > | 如果是二進位檔案衝突時， --ours 為決定使用此分支的檔案 |
| git checkout --theirs < file name > |	如果是二進位檔案衝突時， --theirs 為決定使用其他分支的檔案 |
| git reset < id >^ | 在指定 Commit 的「前⼀次」，如果是 < id >^^ 則是往前兩次，以此類推。不過如果要倒退五次，通常不會寫 < id >^^^^^ ，⽽會寫成 < id >~5 。亦可使用 header or branch name |
| git reset < id >^ --mixed | 這個模式會把暫存區的檔案丟掉，但不會動到⼯作⽬錄的檔案 |
| git reset < id >^ --soft	| 這個模式下的 reset ，⼯作⽬錄跟暫存區的檔案都不會被丟掉，所以看起來就只有 HEAD 的移動⽽已。 |
| git reset < id >^ --hard	| 在這個模式下，不管是⼯作⽬錄以及暫存區的檔案都會丟掉 |
| git reset ORIG_HEAD | ORIG_HEAD 會記錄「危險操作」之前 HEAD 的位置。 |
| git branch | 檢視分支 |
| git branch < branch name > | 新增分支 |
| git checkout < branch name > | 切換到指定分支 |
| git checkout -b < branch name > | 切換到分支， -b 參數代表如果此分支不存在就會新建分支後再切換到此分支 |
| git hash-object |	計算 Blob 物件的 SHA-1 值	|
| git cat -file -t < HSA-1 > | -t 參數表⽰要查看這個 SHA-1 值所代表的物件的型態 |
| git cat -file -p < HSA-1 > | -p 參數表⽰查看這個 SHA-1 值指向的那顆物件的內容 |
| git branch -m < branch name > < new branch name >	| 分支改名 |
| git branch -d < branch name > | 刪除分支，大寫的 -D 為強制刪除。 |
| git ls-files -s | git ls-files 指令來查詢⽬前這些檔案在 Git 裡的樣⼦ |
| git tag -a < tag name > -m < comment > | 在⽬前這個 Commit 打上⼀個 Tag |
| git tag -d < tag name > | 刪除tag |
| git gc | git 資源回收機制，會將檔案已有效的方式進行打包並做好索引 |
| git veryfy -pack -v .git/objects/pack/< pack name > |	用來觀察git gc 打包的狀態 |
| git merge < branch name > --no-ff	| 合併分支，加入 --no-ff 參數是「不要使⽤快轉模式合併」的意思，這樣⼀來就會額外做出⼀個 Commit 物件 |
| git rebase | 重新定義分⽀的參考基準 |
| git rebase -i bb0c9c2	| -i 參數是指要進入 Rebase 指令的「互動模式」，⽽後⾯的 bb0c9c2 是指這次的 Rebase 指令的應⽤範圍會「從現在到 bb0c9c2 這個 Commit」 |
| git rebase --continue	| rebase 遇到衝突的時候可以使用 --continue 參數來繼續剛剛中斷的rebase |
| git reflog | 查詢RefLog |
| git tag < tag name > < id > -a -m < comment >	| -a 參數就是請 Git 幫你建立有附註的標籤，⽽後⾯的 -m 則是跟我們在做⼀般的 Commit ⼀樣輸入的訊息	|
| git tag -d < tag name > |	刪除標籤 |
| git revert HEAD --no-edit	| 取消最後這次的 Commit，加上後⾯的 --no-edit 參數，表⽰不編輯 Commit 訊息。 |
| git stash	| 暫存目前的進度 |
| git stash list | 查詢stash |
| git stash pop < stash item number > | 使⽤ pop 指令，可以把某個 Stash 拿出來並套⽤在⽬前的分⽀上。套⽤成功之後，那個套⽤過的 Stash 就會被刪除。如果不指定< stash item number > 就會先從最小的 item 開始取出 |
| git stash drop < stash item number > | 將 stash 從 stash list 中移除 |
| git filter-branch --tree-filter < command > |	根據所要執行的 command 可以一次大量的修改 commit |
| git cherry-pick < id > | 撿別的分⽀的 Commit 過來合併，如果加上 --no-commit 參數，撿過來的 Commit 不會直接合併，⽽是會先放在暫存區 |
| git reflog expire --all --expire=now | 這個指令是要求 Reflog 現在立刻過期	|
| git fsck --unreachable | 找出 unreachable 物件	|
| git remote add origin < git server name > | git remote 指令，顧名思義，主要是跟遠端有關的操作。 add 指令是指要加入⼀個遠端的節點。在這裡的 origin 是⼀個「代名詞」，指的是後⾯那串 GitHub 伺服器的位置。|
| git remote -v	| 可以看到遠端 server 詳細資訊 |
| git push -u origin master	| 把 master 這個分⽀的內容，推向 origin 這個位置。在 origin 那個遠端 Server 上，如果 master 不存在，就建立⼀個叫做 master 的同名分⽀。 但如果本來 Server 上就存在 master 分⽀，便會移動 Server 上 master 分⽀的位置，使它指到⽬前最新的進度上。 |
| git push -f | 硬推上程式 |
| git fetch	| 從 git remote server 上抓東西下來，通常會與 git merge 合併使用	|
| git pull	| git fetch + git merge	|
| git clone < git server > | 通常會使用在第一次 |
| git format-patch fd7cd38..6e6ed76	| 產生更新檔，後⾯的參數 fd7cd38..6e6ed76 表⽰會產⽣從 fd7cd38 這個 Commit 之後(不包括本⾝)，直到 6e6ed76 這個 Commit 為⽌的更新檔 |
| git format-patch -< number > -o < file path >	| 產生最新次數的更新檔加上 -o 參數可以指定產⽣的更新檔的位置 |
| git am < file >	|	使⽤ format-patch 指令產出的修正檔 |
