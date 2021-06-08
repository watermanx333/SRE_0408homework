# Hadoop

Modules
The project includes these modules:

Hadoop Common: The common utilities that support the other Hadoop modules.(管理命令)
Hadoop Distributed File System (HDFS™): A distributed file system that provides high-throughput access to application data.(檔案系統)(存檔讀取)
Hadoop YARN: A framework for job scheduling and cluster resource management.(專門執行程式運算,運算系統)
Hadoop MapReduce: A YARN-based system for parallel processing of large data sets.(資料處理引擎,很認識資料庫系統因此可拿來做分析)
Hadoop Ozone: An object store for Hadoop(適合用來儲存影音資訊)
來源:http://hadoop.apache.org/

---
:pushpin: Hadoop系統當初被設計用來分析原始資料  
:question: 何謂原始資料?  
根據國際科學與技術資料委員會的定義：資料(Data)是經由一定程序所得到的事實(fact)內容。就本規範而言，原始資料是指依計畫建議書所述之研究方法與所須器械於野外進行調查、觀測或實驗後取得並紀錄，且未經任何統計分析、內容格式轉換、摘要處理等過程的初級資料。原始資料亦為驗證科研結果與衍生更多研究價值的基礎。  
raw data本身沒有任何意義和價值，只是一個客觀的存在，不可修改。

---
大數據的4V:  
1.velocity:串流型態，sensor每分每秒有資料進來(不會對它做修改raw data)
2.variety:企業系統紀錄檔(Log),也是raw data或是政府opendata或
3.volume:資料量，隨時間增加資料多。
4.veracity:資料真實性，也就是過濾資料，得到真正有效可提供信息的資料。

---
hadoop可根據需求配置應用系統
![](https://i.imgur.com/FLdStY3.png)
圖片來源:https://www.geeksforgeeks.org/hadoop-ecosystem/

---
hadoop architecture
![](https://i.imgur.com/h1P2ZQB.png)

圖片來源:https://bigdataanalyticsnews.com/hadoop-2-0-yarn-architecture/

HDFS:多台電腦構成的檔案系統(叢集版)，容量沒有限制
YERN:專門用來跑程式(指定在不同機器跑)(叢集版)
MAPREDUCE:資料處理引擎(data processing)

---



