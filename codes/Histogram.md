# Histogram
```
 % Histogram
clc;
clear all;
close all;

img= imread("image2.jpeg");
img_gray= rgb2gray(img);

og_hist=zeros(1,256);
[rows,col]=size(img_gray);
for i = 1:rows
    for j= 1:col
        m=double(img_gray(i,j));
        og_hist(m+1)=og_hist(m+1)+1;
    end
end
subplot(1,2,1);imshow(img_gray);
area = rows*col;
cumulative=zeros(1,256);
sum=0;
for i =1:256
    sum=sum+og_hist(i);
    cumulative(i)=sum;
end
D=255;

for i = 1:rows
    for j = 1:col
        n=double(img_gray(i,j));
        img_gray(i,j)= ((cumulative(n+1)*D)/area);
    end
end
img_gray=uint8(img_gray);
imshow(img_gray);

myhist= zeros(1,256);
for i = 1:rows
    for j= 1:col
        m=double(img_gray(i,j));
        myhist(m+1)=myhist(m+1)+1;
    end
end
subplot(1,2,2);imshow(img_gray);
```
