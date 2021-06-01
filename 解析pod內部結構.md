# 解析pod的內部結構
![](https://i.imgur.com/FaU4ggy.png)
:pushpin: 名字為pause這個container，執行sleepinfinity命令,這個命令讓這個container一直睡下去(睡夢羅漢)，如此一來此這個Pod就會一直存在下去。
Pause很安全,沒開任何port號,很難被攻陷,pause還在,這個POD就會一直存在。
pod的網路卡,運算資源都放這個裡面。

---


![](https://i.imgur.com/0qvQUbD.png)
:pushpin: 許多公司的淨銷存系統、會計系統...等，都放在這裡面。
紫色為volume，青色正方體為container。

---
```
$ echo 'apiVersion: v1
kind: Pod
metadata:
  name: sharepid
spec:
  shareProcessNamespace: true
  hostname: xyz 
  containers:
  - name: derby
    image: dafu/alpine.derby
    imagePullPolicy: Never
  - name: shell
    image: busybox
    stdin: true
    tty: true  ' > sharepid.yml


```
kind: 宣告這個yaml要產生pod。 :arrow_left: 記錄在master主機
metadata存在etcd資料庫系統
    name: sharepid :arrow_left: pod名稱
spec :arrow_left: 內部規格
shareProcessNamespace:透過檔案系統互通有無(記憶體)，不需要透過網路，共用同一個processs系統。
共用同一個主機名稱。
containers: (一個pod可以有多個container)
container名字
下載image來源
imagePullPolicy: Always，代表每次重啟pod都會上網載光碟片。
stdin: true :arrow_heading_down: 
tty: true :arrow_right: 虛擬終端機(-i-t參數)