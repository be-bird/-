# 課題2 レポート

課題2　階調数と疑似輪郭  
2階調，2階調，2階調の画像を生成せよ．  
課題作成にあたっては「Lenna」以外の画像を用いよ．

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，グレースケールにする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image; % 画像の表示

原画像をグレースケールにしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai2_1.png?raw=true)  
図2　グレースケール

次に，これを2階調画像にする．閾値は128の1つに設定する．

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;

2階調画像を図3に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai2_2.png?raw=true)  
図3　2階調

4階調画像は，閾値を3つ設定し，

IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar;  axis image;

とする．4階調画像を図4に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai2_3.png?raw=true)  
図4　4階調

同様に，8階調の場合は閾値が7つとなり，

IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0 + IMG1 + IMG2+ IMG3+ IMG4+ IMG5+ IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;

とすることができる．8階調画像を図5に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai2_4.png?raw=true)  
図5　8階調

