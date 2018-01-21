# 課題5 レポート

課題5　判別分析法
判別分析法を用いて画像二値化せよ．
課題作成にあたっては「Lenna」以外の画像を用いよ．

「ponta.png」を原画像とする(図1)．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/ponta.png?raw=true)  
図1　原画像

まず，原画像を読み込み，白黒濃淡画像にする．

ORG=imread('ponta.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

原画像を白黒濃淡画像にしたものを図2に示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai5_1.png?raw=true)  
図2　白黒濃淡画像

図2を判別分析法を用いて二値画像に変換する．判別分析法とは，対象物の濃度と，背景の濃度とがそれぞれ最もよくまとまり，かつ対象物と背景との違いが際立つように閾値を定める方法である．以下のようにして，二値化する．

H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
myu_T = mean(H);
max_val = 0;
max_thres = 1;
for i=1:255
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける
C2 = H(i+1:256);
n1 = sum(C1); %画素数の算出
n2 = sum(C2);
myu1 = mean(C1); %平均値の算出
myu2 = mean(C2);
sigma1 = var(C1); %分散の算出
sigma2 = var(C2);
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出
if max_val<sigma_B/sigma_w
max_val = sigma_B/sigma_w;
max_thres =i;
end;
end;

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;

図3に結果を示す．

![原画像](https://github.com/be-bird/image_processing/blob/master/images/kadai5_2.png?raw=true)  
図3　判別分析法による二値化

用意した原画像の場合，猫が寝ている座椅子が背景，その他が対象物であるかのようになる．
