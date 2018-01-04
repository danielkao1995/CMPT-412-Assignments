# CMPT-412

--------------------------------------------------------------------------------------------------------------------------------

Modifying Image:

%Create Image from assignment
a=zeros(6,6,3); 
a(:,:,1)=magic(6);
a(:,:,2)=magic(6)'; 
a(:,:,3)=ones(6)/2; 
a=a/max(a(:));
%Another example using bigger picture in MatLab
%a=imread('onion.png')
figure; imshow (a);
 
reflect(a);
subsample(a, 2);
shrink(a);
zoom(a);
dim (a, 1/2);
myrotate (a);
contrast_compress(a);
 
%Declaring functions
function b = subsample(image, factor)
%subsample by using Indexing in both row and col
output = image(1:factor:end,1:factor:end,:)
figure; imshow (output);
end
function c = shrink(image)
% State variables needed
scale = [1/2 1/2]
% Find size of image
oldSize = size(image) 
% Find size of new image
newSize = scale.*oldSize(1:2) 
% Compute the set of indices that will be used for old image
Index = round(((1:newSize(1))-0.5)./scale(1)+0.5),2
% Create new image by indexing the old image
output = image(Index,Index,:)
% Show New Image
figure; imshow (output);
end
function d = zoom(image)
% State variables needed
scale = [2 2]
% Find size of image
oldSize = size(image)
% Find size of new image
newSize = scale.*oldSize(1:2) 
% Compute the set of indices that will be used for old image
Index = round(((1:newSize(1))-0.5)./scale(1)+0.5),2
% Create new image by indexing the old image
output = image(Index,Index,:)
% Show New Image
figure; imshow (output);
end
function e = myrotate(image)
%Set theta to 90 degrees clockwise
theta = degtorad (90)
%Table for calculating the angle
angle = [ cos(theta) sin(theta)  0
        -sin(theta) cos(theta)  0
         0           0          1]
%Create structure for affine transformation
T = maketform('affine', angle)
%Apply the angles calculated in the table
NewImage = imtransform(image, T)
figure, imshow(NewImage);
end
function f = reflect(image)
NewImage = image(:,end:-1:1, :)
figure; imshow (NewImage);
end
function g = dim(image, fraction)
% Create new image by indexing the old image
output = image(:,:,:)*fraction;
% Show New Image
figure; imshow (output);
end
function h = contrast_compress(image)
%Convert image to type double and scale by 255 to fit intensity range [0 1]
NewImage=(double(image(:,:,1))+double(image(:,:,2))+double(image(:,:,3)))/(3*255);
%Square rooting the image as requested by the assignment
NewImage = sqrt (NewImage)
figure; imshow (NewImage);
end

-------------------------------------------------------------------------------------------------------------------------------

