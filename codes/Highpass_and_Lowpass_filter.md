
```
% % Highpass and Lowpass filter
clc;
clear all;
close all;

img=imread("image2.jpeg");

img_gray=rgb2gray(img);
img_double=double(img_gray);

[h,w]=size(img_gray)
D=zeros(h,w);
H=zeros(h,w);
 Do=20;
for u=1:h
    for v=1:w
        D(u,v)=sqrt(((u-(h/2))^2)+((v-(w/2))^2));
        if D(u,v) <= Do
            H(u,v)=1;
        else 
            H(u,v)=0;
        end
    end
end

f_ft=fft2(img_double);
f_shift=fftshift(f_ft);
f_img=H.*f_shift;
if_ft=ifft2(f_img);
filtered_img=uint8(abs(if_ft));
figure(1);
subplot(2,2,1);imshow(img_gray);title("Original Image");
subplot(2,2,2);imshow(H);title("Low Pass Filter Mask");
subplot(2,2,3);mesh(H);title("Filter Response");
subplot(2,2,4);imshow(filtered_img);title("Filtered Image");

for u=1:h
    for v=1:w
        D(u,v)=sqrt(((u-(h/2))^2)+((v-(w/2))^2));
        if D(u,v) >= Do
            H(u,v)=1;
        else
            H(u,v)=0;
        end
    end
end
f_ft2=fft2(img_double);
f_shift2=fftshift(f_ft2);
f_img2=H.*f_shift2;
if_ft2=ifft2(f_img2);
filtered_img2=uint8(abs(if_ft2));
figure(2);
subplot(2,2,1);imshow(img_gray);title("Original Image");
subplot(2,2,2);imshow(H);title("High Pass Filter Mask");
subplot(2,2,3);mesh(H);title("Filter Response");
subplot(2,2,4);imshow(filtered_img2);title("Filtered Image");
```
