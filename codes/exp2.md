# Exp.2
```
% % Exp2
clc;
clear all;
close all;

img=imread("image2.jpeg");
img_gray=rgb2gray(img);
img_double=im2double(img);

% Negative img
neg_img=255-img_gray;

% Contrast Stretching
con_img=imadjust(img_gray,stretchlim(img_gray));

% Thresholding, Log, Power
c=1;
gamma=1;
threshold=100;
for i=1:size(img_gray,1)
    for j=1:size(img_gray,2)
        log_img(i,j)=c*log(1+img_double(i,j));
        power_img(i,j)=c*(img_double(i,j)^2);
        if (img_gray(i,j) > threshold)
            thr_img(i,j) = 1;
        else
            thr_img(i,j) = 0;
        end
    end
end


% Bit plane slicing and removing
for n=1:8
    s=255-(2^(n-1));
    s1=2^(n-1);
    for i=1:size(img_gray,1)
        for j=1:size(img_gray,2)
            bit_remove(i,j)=bitand(img_gray(i,j),s);
            bit_slice(i,j)=bitand(img_gray(i,j),s1);
        end
    end
    figure(1);
    subplot(4,2,n);imshow(bit_slice);title("Bit plane slicing");
    y=sgtitle("Bit Plan slicing");
    figure(2);
    subplot(4,2,n);imshow(bit_remove);title("Bit plane Remove");
    y=sgtitle("Bit Plan Removing");
end
```
