# 課題10 レポート

課題10 画像のエッジ抽出  
次のプログラムを参考にして，エッジ抽出を体験せよ．  
各自，Lenna以外の画像を用いよ．

ORG = imread('Lenna.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); %カラーからグレイへの変換  
imagesc(ORG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai10_1.png?raw=true)  
図2　白黒濃淡画像

プレウィット法によるエッジ抽出を行う．

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

結果を図3に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai10_2.png?raw=true)  
図3　エッジ抽出（プレウィット法）

ソベル法によるエッジ抽出を行う．

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示 

結果を図4に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai10_3.png?raw=true)  
図4　エッジ抽出（ソベル法）

キャニー法によるエッジ抽出を行う．

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  

結果を図5に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai10_4.png?raw=true)  
図5　エッジ抽出（キャニー法）

プレウィット法とソベル法ではあまり結果が変わらないが，キャニー法は2つに比べ，抽出される線が多い．
