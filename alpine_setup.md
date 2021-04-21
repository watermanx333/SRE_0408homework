# Linux 程序管理

:arrow_forward: program(程式)，檔案，他一定要具有執行權限。
:arrow_forward: process(程序)，run程式，如:啟動Word、Excel、作業系統跑得軟體和程式。

---

程序：載入記憶體，紀錄執行者的權限屬性參數，會知道使用者的UID。
![](https://i.imgur.com/FiawnRu.png)

---
PowerShell

指令→ ps aux (查看有多少process)

ps命令是linux busybox在run的

$ls -al /bin | grep ps

$which busybox ← busybox放在哪個目錄
![](https://i.imgur.com/n4ek67X.png)

$ls -alh /bin/busybox
![](https://i.imgur.com/xWB75rt.png)
(h換成人一看就懂的)

$busybox
![](https://i.imgur.com/VF37ioG.png)

:pushpin: busybox
1.檔案很小，只有806k，沒有全功能模擬linux命令，由於檔案小，IP分享器、wifi、物聯網、IOT裝置都是用linux的busybox(cpu都很低階，不需要高效能)
2.有很多命令，這些命令是C語言或GOLAN寫出來的。
3.為linux的一個程式。
$sudo apk add procps
$ls -al /bin 
ps→  捷徑檔不見了，完整命令被覆蓋掉。

$sudo nano /etc/profile
:page_facing_up: 所有人，只要有人登入這台機器，這個program就會被執行。  
:+1: 在profile裡可用alias更改指令


---
:pushpin:top 
可以監看目前所有程式的執行狀況，點1看全部cpu,點q離開

---
:pushpin: pstree  
程式具有父子關係  

pstree -h 顯示PID號碼  
![](https://i.imgur.com/9ih5mDv.png)
(全都是程式)  

:bomb:   
init號碼為1，為系統的一個執行的程式。  
現在在bash環境下，爸爸為sshd(5646)←也是程式，上圖都是程式。
PPID→parents process id

~$ echo $PPID
5646

看自己的PID→ $$PID


---
:star: 原本的ps放在/bin/ps→$which ps  
自己做得ps在 /etc/profile


---
:pushpin: 找程式參數意思  
ps --help
man ps←完整手冊