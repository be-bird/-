# 課題9 レポート

課題9 メディアンフィルタと先鋭化  
メディアンフィルターを適用し，ノイズ除去を体験せよ．  
各自，Lenna以外の画像を用いよ．

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai9_1.png?raw=true)  
図2　白黒濃淡画像

まず，ノイズ除去をするにあたって，適当なノイズを図2に添付する．

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

図3にノイズが添付された画像を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai9_2.png?raw=true)  
図3　ノイズを添付した画像

図3のノイズを平滑化フィルタを用いて除去する．

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

図4に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai9_3.png?raw=true)  
図4　平滑化フィルタによるノイズ除去

図3のノイズをメディアンフィルタを用いて除去する．メディアンフィルタとは，変換後の濃度値を着目画素の近傍画素の濃度値の中央値とする方法である．エッジをぼかすことなく，ノイズの除去が行える．

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

図5に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai9_4.png?raw=true)  
図5　メディアンフィルタによるノイズ除去

図3のノイズを自分で設計したフィルタで除去する．

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計  
IMG = filter2(f,IMG,'same'); % フィルタの適用  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

図6に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai9_5.png?raw=true)  
図6　設計したフィルタによるノイズ除去

図5のように，メディアンフィルタを用いたときが，一番綺麗にノイズ除去されているように見える．
