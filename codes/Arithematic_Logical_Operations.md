# Arithematic Ang Logical Operations
```
% % % Arithematic Ang Logical operations
clc;
clear all;
close all;

img1=imread("image1.jpeg");
img1=imresize(img1,[400,400]);
subplot(4,3,1);imshow(img1);title("Image1");

img2=imread("image2.jpeg");
img2=imresize(img2,[400,400]);
subplot(4,3,2);imshow(img2);title("Image2");

addn=imadd(img1,img2);
subplot(4,3,3);imshow(addn);title("Add");

subn=imsubtract(img1,img2);
subplot(4,3,4);imshow(subn);title("Sub");

multiplin=immultiply(img1,img2);
subplot(4,3,5);imshow(multiplin);title("Mul");

divn=imdivide(img1,img2);
subplot(4,3,6);imshow(divn);title("Div");

c_img1=bitcmp(img1);
subplot(4,3,7);imshow(c_img1);title("cmp1");

c_img2=bitcmp(img2);
subplot(4,3,8);imshow(c_img2);title("cmp2");

andn=bitand(img1,img2);
subplot(4,3,9);imshow(andn);title("And");

orn=bitor(img1,img2);
subplot(4,3,10);imshow(orn);title("Or");

xorn=bitxor(img1,img2);
subplot(4,3,11);imshow(xorn);title("Xor");

y=sgtitle("Shreyas Sarang")
```
