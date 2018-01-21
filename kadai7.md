# 課題7 レポート

課題7　ダイナミックレンジの拡大  
画素のダイナミックレンジを0から255にせよ．  
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

図2の画素のダイナミックレンジを以下のようにして拡大する．

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

図4に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai7_3.png?raw=true)  
図4　ダイナミックレンジ拡大

図4のヒストグラムを，

ORG = uint8(ORG);  
imhist(ORG); % 濃度ヒストグラムを生成、表示

のようにして表示する．unit8を用いてORGの値を8ビット符号なし整数へ変換することができる．計算のため一度double型にしたORGの値を，ここで整数にしている．図5がそのヒストグラムである．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai7_4.png?raw=true)  
図5　ヒストグラム（ダイナミックレンジ拡大時）

ダイナミックレンジを拡大することによって，使われていなかった0付近の輝度値も使われるようになる．
