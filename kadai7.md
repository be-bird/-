# 課題7 レポート

課題7　ダイナミックレンジの拡大  
画素のダイナミックレンジを０から２５５にせよ．  
課題作成にあたっては「Lenna」以外の画像を用いよ．

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai7_1.png?raw=true)  
図2　白黒濃淡画像

次に，図2のヒストグラムを，

imhist(ORG); % 濃度ヒストグラムを生成、表示

のようにして表示する．図3がそのヒストグラムである．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai7_2.png?raw=true)  
図3　ヒストグラム

図2の画素のダイナミックレンジを拡大する．

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示



