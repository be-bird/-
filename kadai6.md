# 課題6 レポート

課題6　画像の二値化
下記のプログラムを参考にして画像を二値化せよ．
課題作成にあたっては「Lenna」以外の画像を用いよ．

clear; % 変数のオールクリア  
ORG=imread('Lenna.png'); % 原画像の入力  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  
pause; % 一時停止

IMG = ORG>128; % 128による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  
pause;

IMG = dither(ORG); % ディザ法による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，白黒濃淡画像にする．

ORG=imread('Lenna.png'); % 原画像の入力  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai6_1.png?raw=true)  
図2　白黒濃淡画像

輝度値128を閾値として二値化する．

IMG = ORG>128; % 128による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

図3に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai6_2.png?raw=true)  
図3　閾値128での二値化

ディザ法を用いて二値化する．ディザ法とは疑似濃淡表示を行う際の手法の一つである．原画像の各画素の輝度値を，あらかじめ定められたディザマトリクスの値と比較し，その大小関係で出力画素の輝度値を決定する方法．以下のように

IMG = dither(ORG); % ディザ法による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示 

とすることでディザ法を用いた二値化ができる．図4に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai6_3.png?raw=true)  
図4　ディザ法での二値化

図2～4を比較すると，図4は図3よりも図2のような白黒濃淡画像のように見える．
