## 1.Take a sequence of moving-forward images in NTHU campus

**a.腳踏車廢器區**

<img src='moving forward GIF/5435.gif'>

**b.走去吃胖老爹**

<img src='moving forward GIF/5437.gif'>

**c.欣賞竹湖**

<img src='moving forward GIF/5442.gif'>

**d.清大花園**

<img src='moving forward GIF/5455.gif'>

## 2.Show feature extraction and matching results between two images
[實作過程請參閱此link](https://colab.research.google.com/drive/1sn6nira08AclU3xzaY3CkKlx9yZMHLAt#scrollTo=R8teSbWVkDZ5),

如下圖，首先我們使用SIFT來找出feature sift

<img src='SIFT Match/IMG_5435 04_matches_sift.jpg'>

<img src='SIFT Match/IMG_5437 04_matches_sift.jpg'>

<img src='SIFT Match/IMG_5442 03_matches_brisk.jpg'>

<img src='SIFT Match/IMG_5455 03_matches_sift.jpg'>

## 3.Perform image alignment and generate infinite zooming effect

使用BRISK演算法結果找出frature match result

**a.走去吃胖老爹**

<img src='allign_zooming/5437.gif'>

**b.欣賞竹湖**

<img src='allign_zooming/5442.gif'>

**c.清大花園**

<img src='allign_zooming/5455.gif'>


## 4.Implement different feature extrators, e.g. SIFT, SURF, and compare the results
### 原圖

<img src='algorithm compare/5437/IMG_5437 03.jpg' width = "640" height="480">
<img src='algorithm compare/5442/IMG_5442 03.jpg' width = "640" height="480">
<img src='algorithm compare/5455/IMG_5455 03.jpg' width = "640" height="480">

### SIFT演算法

<img src='algorithm compare/5437/IMG_5437 03_key_sift.jpg' width = "500" height="400">
<img src='algorithm compare/5442/IMG_5442 03_key_sift.jpg' width = "500" height="400">
<img src='algorithm compare/5455/IMG_5455 03_key_sift.jpg' width = "500" height="400">

### BRISK演算法

<img src='algorithm compare/5437/IMG_5437 03_key_brisk.jpg' width = "500" height="400">
<img src='algorithm compare/5442/IMG_5442 03_key_brisk.jpg' width = "500" height="400">
<img src='algorithm compare/5455/IMG_5455 03_key_brisk.jpg' width = "500" height="400">

### BRISK與SIFT Match比較結果
SIFT Match
<img src='algorithm compare/5437/IMG_5437 03_matches_sift.jpg'>
<img src='algorithm compare/5442/IMG_5442 03_matches_sift.jpg'>
<img src='algorithm compare/5455/IMG_5455 03_matches_sift.jpg'>
BRISK Match
<img src='algorithm compare/5437/IMG_5437 03_matches_brisk.jpg'>
<img src='algorithm compare/5442/IMG_5442 03_matches_sift.jpg'>
<img src='algorithm compare/5455/IMG_5455 03_matches_sift.jpg'>

## 5.Enhance effect by using photoshop. 

### 原圖

<img src='algorithm compare - enhanced/5437/IMG_5437_enhanced 03.jpg' width = "640" height="480">
<img src='algorithm compare - enhanced/5442/IMG_5442_enhanced 03.jpg' width = "640" height="480">
<img src='algorithm compare - enhanced/5455/IMG_5455_enhanced 03.jpg' width = "640" height="480">

### SIFT演算法

<img src='algorithm compare - enhanced/5437/IMG_5437 03_enhanced_key_sift.jpg' width = "500" height="400">
<img src='algorithm compare - enhanced/5442/IMG_5442 03_enhanced_key_sift.jpg' width = "500" height="400">
<img src='algorithm compare - enhanced/5455/IMG_5455 03_enhanced_key_sift.jpg' width = "500" height="400">

### BRISK演算法

<img src='algorithm compare - enhanced/5437/IMG_5437 03_enhanced_key_brisk.jpg' width = "500" height="400">
<img src='algorithm compare - enhanced/5442/IMG_5442 03_enhanced_key_brisk.jpg' width = "500" height="400">
<img src='algorithm compare - enhanced/5455/IMG_5455 03_enhanced_key_brisk.jpg' width = "500" height="400">


### BRISK與SIFT Match比較結果
SIFT Match
<img src='algorithm compare - enhanced/5437/IMG_5437 03_enhanced_matches_sift.jpg' >
<img src='algorithm compare - enhanced/5442/IMG_5442 03_enhanced_matches_sift.jpg' >
<img src='algorithm compare - enhanced/5455/IMG_5455 03_enhanced_matches_sift.jpg' >
BRISK Match
<img src='algorithm compare - enhanced/5437/IMG_5437 03_enhanced_matches_brisk.jpg' >
<img src='algorithm compare - enhanced/5442/IMG_5442 03_enhanced_matches_brisk.jpg' >
<img src='algorithm compare - enhanced/5455/IMG_5455 03_enhanced_matches_brisk.jpg' >


## 6.比較所有演算法

### SIFT演算法說明: 

SIFT定位演算法關鍵步驟的說明：,利用原始影象與高斯核的摺積來建立尺度空間，並在高斯差分空間金字塔上提取出尺度不變性的特徵點。該演算法具有一定的仿射不變性，視角不變性，旋轉不變性和光照不變性，所以在影象特徵提高方面得到了最廣泛的應用。

該演算法大概可以歸納為三步：1）高斯差分金字塔的構建；2）特徵點的搜尋；3）特徵描述。

在第一步中，它用組與層的結構構建了一個具有線性關係的金字塔結構，讓我們可以在連續的高斯核尺度上查詢特徵點。它比LoG高明的地方在於，它用一階高斯差分來近似高斯的拉普拉斯核，大大減少了運算量。 

在第二步的特徵點搜尋中，主要的關鍵步驟是極值點的插值，因為在離散的空間中，區域性極值點可能並不是真正意義上的極值點，真正的極植點可以落在了離散點的縫隙中。所以要對這些縫隙位置進行插值，然後再求極值點的座標位置。第二步中另一關鍵環節是刪除邊緣效應的點，因為只忽略那些DoG響應不夠的點是不夠的，DoG的值會受到邊緣的影響，那些邊緣上的點，雖然不是斑點，但是它的DoG響應也很強。所以我們要把這部分點刪除。我們利用橫跨邊緣的地方，在沿邊緣方向與垂直邊緣方向表現出極大與極小的主曲率這一特性。所以通過計算特徵點處主曲率的比值即可以區分其是否在邊緣上。這一點在理解上可以參見Harris角點的求法。

最後一步，即為特徵點的特徵描述。特徵點的方向的求法是需要對特徵點鄰域內的點的梯度方向進行直方圖統計，選取直方圖中比重最大的方向為特徵點的主方向，還可以選擇一個輔方向。在計算特徵向量時，需要對區域性影象進行沿主方向旋轉，然後再進鄰域內的梯度直方圖統計。 
### BRISK演算法說明:

BRISK演算法在特徵點檢測部分沒有選用FAST特徵點檢測，而是選用了穩定性更強的AGAST演算法。在特徵描述子的構建中，BRISK演算法通過利用簡單的畫素灰度值比較，進而得到一個級聯的二進制位元串來描述每個特徵點，這一點上原理與BRIEF是一致的。BRISK演算法裡採用了鄰域取樣模式，即以特徵點為圓心，構建多個不同半徑的離散化Bresenham同心圓，然後再每一個同心圓上獲得具有相同間距的N個取樣點。



### ORB演算法 

ORB演算法使用FAST進行特徵點檢測，然後用BREIF進行特徵點的特徵描述，但是我們知道BRIEF並沒有特徵點方向的概念，所以ORB在BRIEF基礎上引入了方向的計算方法，並在點對的挑選上使用貪婪搜尋演算法，挑出了一些區分性強的點對用來描述二進制串。

|     |  Sample Pattern   | 	Orientation calculation | Sampling pairs 
| ---   |--- | --- | --- 
|SIFT   |	None.| 	None. | Random.  
|ORB  |None. | Moments. | Learned pairs.
|BRISK  |	Concentric circles with more points on outer rings. | Comparing gradients of long pairs. |  Using only short pairs.

## 7. References
1. [A tutorial on binary descriptors – part 4 – The BRISK descriptor](https://gilscvblog.com/2013/11/08/a-tutorial-on-binary-descriptors-part-4-the-brisk-descriptor/?fbclid=IwAR1lFCLMVlV0_TDza5L6Gi6jvcvkRmYxZ8-9rBCFkpn_bnqvkrHVaTwZ4Cw)
2. [SIFT - A Short introduction to descriptors](https://gilscvblog.com/2013/08/18/a-short-introduction-to-descriptors/?fbclid=IwAR1kNmaZUe0V8GaFnBtBqGUNX-169ZLBWkHz_n4xCniBfDMBIFX10I8XQ70)
3. [Performance Evaluation of Binary Descriptors – Introducing the LATCH descriptor](https://gilscvblog.com/2015/11/07/performance-evaluation-of-binary-descriptor-introducing-the-latch-descriptor/?fbclid=IwAR2aceDNJg2DMZoW66pZ21FUZQCs_CYNO2R1oYoHn_Zj0buQThbwhO6eAHk)
