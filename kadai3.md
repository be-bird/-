# 課題3 レポート

課題3　閾値処理  
閾値を4パターン設定し,閾値処理した画像を示せ．  
課題作成にあたっては「Lenna」以外の画像を用いよ．

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai3_1.png?raw=true)  
図2　白黒濃淡画像

次に，輝度値64を閾値として，2階調画像にする．

IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換  
imagesc(IMG); colormap(gray); colorbar;

閾値64の2階調画像を図3に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai3_2.png?raw=true)  
図3　閾値64

閾値を96としたときの2階調画像は，

IMG = ORG > 96; % 輝度値が96以上の画素を1，その他を0に変換  
imagesc(IMG); colormap(gray); colorbar;

とすることができる．閾値96の2階調画像を図4に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai3_3.png?raw=true)  
図4　閾値96

以下，同様に閾値128と，192の2階調画像を図5～6に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai3_4.png?raw=true)  
図5　閾値128

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai3_5.png?raw=true)  
図6　閾値192
