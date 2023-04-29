# Laplacian
```
% Laplacian

img=imread("image1.jpeg");
img_gray=rgb2gray(img);
subplot(1,3,1);imshow(img_gray);title("Og Img");

% m=[0,-1,0;-1,4,-1;0,-1,0];
m=[-1,-1,-1;-1,8,-1;-1,-1,-1];
mask=conv2(double(img_gray),double(m),"same");
subplot(1,3,2);imshow(mask);title("Mask");

sharpen=img_gray+uint8(mask);
subplot(1,3,3);imshow(sharpen);title("Sharpen");
y=sgtitle("Laplacian Filtering")
```
