# 課題8 レポート

課題8 ラベリング  
二値化された画像の連結成分にラベルをつけよ．  
課題作成にあたっては「Lenna」以外の画像を用いよ．  

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai8_1.png?raw=true)  
図2　白黒濃淡画像

さらに，輝度値128を閾値として図2を二値化する．

IMG = ORG > 128; % 閾値128で二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

図3に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai8_2.png?raw=true)  
図3　二値画像

図3の連結成分に，

IMG = bwlabeln(IMG);  
imagesc(IMG); colormap(jet); colorbar; % 画像の表示

のようにしてラベルをつける．図4に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai8_3.png?raw=true)  
図4　ラベル

猫の模様が細かくラベリングされている．
