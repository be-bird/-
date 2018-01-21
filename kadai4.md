# 課題4 レポート

課題4　画像のヒストグラム  
画素の濃度ヒストグラムを生成せよ．  
課題作成にあたっては「Lenna」以外の画像を用いよ．

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai4_1.png?raw=true)  
図2　白黒濃淡画像

ヒストグラムは，

imhist(ORG);

で表示することができる．図2のヒストグラムを図3に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai4_2.png?raw=true)  
図3　ヒストグラム

図3を見ると，輝度値250以上の出現頻度が高いことが分かる．
