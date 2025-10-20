## Region-based CNN (for detecting multiple objects)
Split into regions and apply CNN on each region to detect a particular object
CNN is used for image detection and feature detection, and SVM is used for the classification.
- Each SVM individually determines whether the example contains a specific class, so multiple SVMs are trained
- After classifying you have to know where the objects are located in the picture, so you have to propose bounding boxes with a linear regression model (make the region as small as possible, smaller than the CNN detected region)
- 
