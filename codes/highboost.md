# Highboost
```
% Highboost

img=imread("image1.jpeg");

img_gray=rgb2gray(img);
subplot(1,2,1);imshow(img_gray);title("Og Image");
h=1/25*ones(5,5);

blur_img=conv2(double(img_gray),double(h),'same');

mask= img_gray - uint8(blur_img);


sharpen= img_gray + 4.5*mask;
subplot(1,2,2);imshow(sharpen);title("Sharpen for k=4.5");

y = sgtitle("Highboost Filtering")
```
