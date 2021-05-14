# Docker 運作架構

### 介紹Docker  
docker前身為系統整合商，主要是建設系統(會計系統、人事系統、Mail系統....等等)，為了降低human errors，使用了以下Linux的技術相互搭配:  
:one: Namespace，用以隔離process。  
:two: chroot，獨立file system。  
:three: overlay2，檔案系統格式。  
:four: cgroup，限制每個process的運算資源。  
:five: slirp4netns，創造網路空間。  
:six: bridge/tun，上網。  

這些技術有了Application Container        :heavy_exclamation_mark: 目標降低human errors :heavy_exclamation_mark:  

使用Application Container同時啟動Server:  1.Database 2. Web Application(透過瀏覽器run貿易系統、淨銷存系統..) 3. DHCP/DNS/E-mail  

多台Server組成Cluster(Kubernetes,k8s)，可以幫我們管理多台電腦(container)和自動化管理，人參與下降=human errors降低，再加了一堆功能後形成雲多作業系統。  

![](https://i.imgur.com/MzHH7lw.png)
:pushpin:執行runC須具備兩樣東西: 1. container設定檔(config.json)，2. rootfs，檔案根系統目錄，runC只產生Container,產生完變結束。
:pushpin: shim，log監控container的所有行為，向containerd做報告。