#  First, the principle of the algorithm 

##  1. Overview of the principle 

PCL :: conventions ShapeContext3DEstimation 3D shape context descriptors are:

If the nearest neighbor of the query point cannot be estimated, the property descriptor is set to NaN (not a number) and the RF is set to 0. For a point without finite 3D coordinates, it is impossible to estimate the 3D shape context descriptor. Therefore, any point that contains NaN data on x, y, or z sets its boundary feature property to NaN. 

##  2. References 

>  [1]Daniel, Carlos, Guimarães, et al. Using contextual spaces for image re-ranking and rank aggregation[J]. Multimedia Tools & Applications, 2014. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574249171
  ```  
#  III. Display of results 

 ![avatar]( 20210227165238604.png) 

