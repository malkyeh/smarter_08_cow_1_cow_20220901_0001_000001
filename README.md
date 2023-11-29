# 側拍牛隻影像辨識模型
模型雲端連結 : https://drive.google.com/file/d/1RziIRBrkB58OluCUd_o6dNk7B0rOaj6H/view?usp=sharing

此模型以 Yolov5 為基礎，並對得分演算法進行改進，最後再以卡爾曼濾波器及匈牙利演算法增加追蹤效果，旨在從側拍鏡頭追蹤及辨識牛隻身份。[註] : 牛隻身份固定，若拿其他牛舍的牛當資料則無法進行辨識。


以下為輸入原圖之範例 : 
![](https://hackmd.io/_uploads/Hy7ee_pba.png)

以下為輸出之結果範例 : 
![](https://hackmd.io/_uploads/SyX8bupZp.png)


### 使用方式

此檔案提供程式壓縮檔，並請使用 anaconda 建立 python 3.8 環境，執行步驟如下 : 

1. 建立 anaconda python 3.8 的環境
```
conda create -n strongsort python=3.8
```

2. 解壓縮後進入 `yolov5s_plus_update`
```
cd yolov5s_plus_update
```

3. 下載 Python 相依套件
```
pip install -r requirements.txt
```

4. 開始偵測

因修改之演算法是以時間序列為特徵，建議偵測影片效果較佳。

```
python track.py --source {video_name} --yolo-weights best.pt --save-vid 
```

5. 查看檢測結果

可以在 `Yolov5_StrongSORT_OSNet/run/exp{number}` 查看檢測結果

