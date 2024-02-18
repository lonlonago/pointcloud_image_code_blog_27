#  First, the principle of the algorithm 

##  1. Overview of the principle 

 pcl::PFHEstimation 

##  2. Specific process 

 ![avatar]( 20210529102826964.png) 

   It is a commonly used point local feature descriptor. According to the spatial differences between points and points within their neighborhood radii, such as the angular differences in the direction of the point cloud's estimated normals, a multi-dimensional histogram is finally established to represent the geometric properties of the point and its neighborhood points. The high-latitude hyperspace where the histogram is located provides a measurable information space for the feature representation of points and their neighborhood points. The information space is invariant to the six-dimensional attitude of the point cloud corresponding to the surface, and the sampling density is also very stable in the case of noise points. Based on the geometric relationship between the point and the point in its neighborhood and their estimated normal vectors, we want to understand the neighborhood surface changes more clearly, so as to describe the geometric features in the local area of the point cloud. Therefore, the quality of the estimated normal of each point in the neighborhood directly affects the quality of the feature space. As shown in Figure 1, the red point is the query point, and the dotted line is the calculated influence area of. Inside the dotted line is the set sphere containing points, which is the center of the sphere, which is the radius, and the points in the sphere are the neighborhood points. Connect all points in the neighborhood in pairs to form a regional network, and obtain the PFH descriptor by calculating the interaction relationship of all points in the neighborhood. Therefore, the complexity of the calculation is, representing the number of points in the neighborhood other than the query points, and representing the number of query points.  

 ![avatar]( 20210529105822672.png) 

   The detailed calculation process of the algorithm is as follows: (1) Assume the sum of any two points in the neighborhood grid, and set their corresponding estimation normals as sum, and use the formula (1) to calculate the source point, if it is determined to be, then is, and vice versa. The essence of formula (1) is that the connection between two points and the point's estimated normal angle is smaller as the point. (2) The relative deviation existing between the source point and the non-source point and their corresponding estimated normal sum, in order to calculate the relative deviation, we need to establish a fixed coordinate system on a point, as shown in Figure 2,   

   (3) According to the local coordinate system of Figure 2, we use three angle values,,, to represent the relative deviation between the estimated normal and 

    Equation (3) represents the Euclidean distance between and. Calculate four sets of values for each point pair within the neighborhood radius of the feature point, so that the two points and their corresponding estimated normal correlation 12 parameters (coordinate values and estimated normal information) can be reduced to 4. In this way, the estimated normal relationship between each point pair is formed, which can also be used to represent the geometric features of the surface. (4) Establish a point feature histogram of the query point. First, put the values of all points into the feature histogram. Usually we use (default value is 5) interval classification by default, divide the first three feature values into sub-intervals, and form the feature vector of () latitude. Calculate the number of points in each sub-interval according to the value of. In some cases, the eigenvalue in the 2.5-latitude dataset has a negligible impact on the overall geometric features, so we usually ignore the eigenvalue in our calculations. The formula for calculating the dimensional space that falls into can be expressed as: where, respectively, correspond to the values to be regularized, and are integers. After regularization, it can be guaranteed and is an integer. The formula for determining the latitude value is: Represents pairs of points with the same value in the neighborhood grid of the query point, and the number of neighborhood points can be expressed as 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957422167
  ```  
#  III. Display of results 

 ![avatar]( 20200504193206141.png) 

  This is the PFH signature of a point. 

