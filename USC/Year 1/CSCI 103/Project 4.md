Look for pixels that are foreground and touching

 upper left pixel of its bounding box

grab background color, get its rgb value
scan through the image until you encounter a pixel that is sufficiently different

once you get the first foreground pixel, use VFS to find the connected pixels and update the max, min row and column
build bounding box

resume scan once you finish bfs

update the labeled/explored array, so that when you encounter the pixel again after resuming the search

for layers, the first object you find should be the backmost layer. order and layer are equal

save - while you are making transformations and forward/backwards, save this information (dont make a new image while doing it). at the end, create a new blank array and use the information you used to fill it in/render.

Cimage class
**pointer to image**
**h and w**
**background color**
**labeled array (2d vector)
threshhold for background difference**

Component class - objects in image
stored in vectors of objects
upper left coordinate of bounding box
h,w,label
new location if you want to translate it (initialize as -1,-1)
Forward and backward (rearrange the components vector or add new data member to class)

tips - 
dont change input image
when I say i want to move to a new location, dont move all the pixels aka dont copy the whole bounding box, only move over the right pixels
