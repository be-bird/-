# 課題1レポート

課題1　標本化間隔と空間解像度
画像をダウンサンプリングして（標本化間隔を大きくして）表示せよ．
課題作成にあたっては「Lenna」以外の画像を用いよ．


「ponta.png」を原画像とする．

ORG=imread('ponta.png'); % 原画像の入力
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図1に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/image/ponta.png?raw=true)  
図1　原画像

原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/image/kadai1_1.png?raw=true)  
図2　1/2サンプリング

同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．すなわち，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

とする．1/4サンプリングの結果を図3に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/image/kadai1_2.png?raw=true)  
図3　1/4サンプリング

1/8から1/32サンプリングは，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

を繰り返す．サンプリングの結果を図4～6に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/image/kadai1_3.png?raw=true)  
図4　1/8サンプリング

![原画像](https://github.com/be-bird/image_processing/blob/master/image/kadai1_4.png?raw=true)  
図5　1/16サンプリング

![原画像](https://github.com/be-bird/image_processing/blob/master/image/kadai1_5.png?raw=true)  
図6　1/32サンプリング

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
