# podman

![](https://i.imgur.com/df7NGwG.png)


紅帽三劍客: Podman、Buildah、Skopeo
![](https://i.imgur.com/0wsTEps.png)

:pushpin: Podman  
Podman是一個program，enter按下去才會執行，變成程序，它不是Daemon，因此不會背景執行。  
:pushpin: Buildah  
Buildah執行Dockerfile，產生image  
:pushpin: Skopeo
Skopeo下載imgaes，每家公司有自己的光片中心(IBM、微軟...)，Docker只能下載自己Docker的光片中心。

Skopeo抓images(2派都能處理)
Images有2個派別，1.docker公司  2.OCI

---
Docker使用Runc產生container，Runc使用GO語言寫出來的。
Podman使用Crun產生container，Crun使用C語言寫出。
Crun比RunC快一倍

---
Podman有兩種模式:1.rootful(root權限執行) 2.rootless(一般帳號執行)


---
Podman與Docker不同的地方:
Docker Daemon的DNS server只會服務同一網段的所有電腦名稱解析(ping電腦名稱可通)，而Podman則沒有辦法(需ping ip位址)
