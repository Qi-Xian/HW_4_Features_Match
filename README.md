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

|     |  Sample Pattern   | 	Orientation calculation | Sampling pairs 
| ---   |--- | --- | --- 
|SIFT   |	None.| 	None. | Random.  
|ORB  |None. | Moments. | Learned pairs.
|BRISK  |	Concentric circles with more points on outer rings. | Comparing gradients of long pairs. |  Using only short pairs.

