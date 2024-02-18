 RANSAC fitting straight line 

#  First, the principle of the algorithm 

   For the specific algorithm principle and parameter analysis, see: PCL RANSAC fitting straight line 

##  1. Algorithm improvement 

   SampleConsensusModelParallelLine, a model is defined that uses additional angular constraints for 3D line segmentation. The inspection of the inner line involves not only the "distance to model" criterion, but also an additional "maximum dimensional deviation" between the orientation of the line and the user-specified axis. 

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248939
  ```  
>  Set the fitting model used to RANSAC with additional angle constraints 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248939
  ```  
>  Set the axis at an angle to the straight line to be fitted 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248939
  ```  
>  Set the angle between the straight line and the axis to be fitted, and the angle is in radians 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248939
  ```  
#  III. Display of results 

 ![avatar]( 202104101034496.png) 



--------------------------------------------------------------------------------

 + 1. Algorithm principle 1. Calculation step 2. Algorithm source code 3. Function analysis 4. References

 + 2. Code implementation 

 + 3. Results display 

 + 4. The reason why there is no change after filtering 

 + 5. Solutions 

 + 6. Display of results 

#  First, the principle of the algorithm 

##  1. Calculation steps 

 The calculation steps of the bilateral filter in PCL: input: a certain point, two Gaussian weights, output: the point after intensity smoothing 

 Therefore, as far as the principle of the algorithm and the implementation of the source code are concerned, the number of points in the point cloud processed by this bilateral filter in PCL is constant, and the only change is the intensity value.  

##  2. Algorithm source code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
>  PCL :: Bilateral Filter < PointT > to realize intensity-based bilateral filtering of point cloud data. The intensity information of the point cloud needs to be used. For the method of obtaining the pcd point cloud with intensity information, see: PCL obtains the pcd point cloud with intensity information. 

##  3. Function analysis 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 constructor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 Filter the input data and store the result to the output. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 Calculates the average strength for a given single point. input: 

 Outputs the calculated average strength for that point. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 Sets half the size of the window for Gaussian bilateral filtering. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 Obtain the half size parameter of the window for Gaussian bilateral filtering. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 Set the standard deviation parameter to sigma_r. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 The standard deviation parameter is sigma_r. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
 Provides a pointer to the search object. 

##  4. References 

>  [1] Digne J , Franchis C D . The Bilateral Filter for Point Clouds[J]. Image Processing On Line, 2017, 7:278-287. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
#  III. Display of results 

 ![avatar]( b3700f06bd0a4a93b669890e711df9a8.png) 

#  Fourth, the reason why there is no change after filtering 

>  After actual measurement, the processed point cloud intensity value is also unchanged, and the problem mainly lies in the 100th line of the source code and the 61st line of the source code provided by this blog. 

 ![avatar]( dcb06438a4e44c02aa4ef143a53292d0.png) 

 There is a problem with this line of code  

 ![avatar]( cf264fc1ab224695a80255c5e596715c.png) 

 In PCL 1.12.1, the source code here has been revised to: its essence should be that it has not changed, but uses the new features of C++ 11 (not tested with the latest version of PCL 1.12.1, this is just speculation). 

#  V. Solutions 

>  According to the principle of the algorithm, write the implementation process yourself. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574143959
  ```  
#  VI. Display of results 

 ![avatar]( cec1735fd8db4324aa238594080ea0bb.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Preface 

    The bilateral filtering algorithm in PCL is based on the intensity information of the point cloud and only filters the intensity field. The xyz coordinates and normals of the point cloud have not changed, and the built-in function cannot get the correct calculation results. Previously, the correct implementation of intensity-based bilateral filtering based on PCL based on intensity bilateral filtering has been given on the basis of analyzing the source code. In this paper, the PCL is used to realize the bilateral filtering based on point cloud normals proposed by Fleishman et al., and the processed point cloud will become smoother. The bilateral filtering based on point cloud normals has a complete set of online running open source codes and cases. For details, see: IPOL Journal · Image Processing On Line. 

##  2. Algorithm overview 

    Fleishman et al. proposed a grid bilateral filter. The bilateral filter was first applied to grey release images. The algorithm not only considers the distance from the point to the neighborhood point, but also uses the distance along the normal direction as the basis for judgment. In addition, the algorithm has no restrictions on the normal direction. The bilateral filter is applied to the point cloud data. For a certain point in the middle, first use the point within the neighborhood range of the point to calculate the unit normal vector of the point, and then the position of the point is updated by the equation. In the formula, it is the new point after the measurement point has been filtered bilaterally; it is the weight factor of the bilateral filter. In the formula, it is the unit normal vector of the near-neighborhood point of the measurement point; it is the Gaussian kernel function that is the standard deviation, that is, the two Gaussian weights in the point cloud bilateral filtering algorithm. Among them is the influence factor of the distance from the measurement point to its near-neighborhood point on the point, but the influence factor of the distance vector from the measurement point to its near-neighborhood point projected on the normal vector of the point on the measurement point; it is the spatial domain weight, which controls the smoothness degree; it is the feature domain weight, which can capture the change of the normal between neighborhood points, thereby controlling the feature retention degree. 

 ![avatar]( 20210613083258295.png) 

    As can be seen from Figure 1, the weight of the neighborhood point distance will be balanced by the weight of the normal direction, which is conducive to bringing the target point close to the tangent plane. The normal is obtained by computing the least squares regression plane of the neighborhood points, which is calculated from the average value of the neighborhood points and the covariance matrix.  

##  3. Calculation steps 

 Bilateral filtering calculation steps based on normal: input: a certain point, neighborhood radius, two Gaussian weights, output: denoising point 

 Therefore, the position of the point cloud after bilateral filtering based on normal will change, and the number of points will remain unchanged. 

##  4. References 

>  [1] Digne J, Franchis C D. The Bilateral Filter for Point Clouds [J]. Image Processing On Line, 2017, 7:278-287. [2] Yuan Zhicong. Research on point cloud registration method based on Harris feature [D]. Donghua University of Technology, 2019. [3] Liu Chuncheng. Column target change detection based on point cloud data [D]. Beijing University of Civil Engineering and Architecture, 2018.p43-44 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574181351
  ```  
#  III. Display of results 

     The red is the point cloud before filtering, and the green is the point cloud after filtering. The data and parameters are from IPOL Journal · Image Processing On Line.  



--------------------------------------------------------------------------------

#  First, the callback function 

 registerAreaPickingCallback () PCL implements the point cloud box selection function, and its callback function has three kinds. Method 1: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574221642
  ```  
>  Cd A std function that will be registered as a callback for locale selection events 

 Method two: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574221642
  ```  
>  Callback This function will be registered as a callback function for locale selection events Cookie user data passed to the callback function 

 Method three: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574221642
  ```  
>  Callback This function passes the instance of the callback function registered as a locale selection event to the class that implements the callback function. Cookie passes user data to the callback function 

#  Example code 

 Press the "x" key to enter the circle selection state, and then press to exit. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574221642
  ```  
#  III. Display of results 

 ![avatar]( 20210222200534140.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

 Fast PFH pcl::FPFHEstimation  

##  2. Specific process 

 ![avatar]( 20210529115939219.png) 

   Assuming that there are points in the three-dimensional point cloud, the complexity of computing the feature histogram is to represent the number of points within the neighborhood radius of any query point in the point cloud data. In practical applications, due to the large number of point cloud data points, it usually takes a long time to calculate the feature histogram of the point cloud. In order to improve the computational efficiency, simplify the process and reduce the complexity of the algorithm, an algorithm is proposed. The main flow of the algorithm is as follows: (1) For each point required, calculate a group between the point and its neighborhood points. The result of this step is called a simplified feature histogram. (2) Re-determine the neighborhood points of each point, and use the neighboring ones to calculate the final histogram (called). The formula is as follows: In Equation (6), the weight is expressed, which is measured according to the distance between the points within its neighborhood. Figure 3 helps us understand this weighting method.  

   In Figure (3), it can be seen that the algorithm is mainly divided into two steps. First, for any query point, the calculated value is based only on the corresponding point pair between its neighbor points (the red line segment in Figure 3). The second step is to calculate the weighted values of the nearest neighbor points (,,, and in Figure 3) and accumulate them. The accumulated results are obtained by adding the SPFH values. In summary, the algorithm is proposed based on the algorithm, and there are differences between them, mainly in the following aspects: (1) The algorithm does not connect all points in the neighborhood of the query point, so there is a possibility of losing some values, and these values may have some clear geometric characteristics; (2) The scope of the algorithm is only within the neighborhood radius of the query point, and the algorithm includes not only the neighborhood range with the center radius, but also the neighborhood with the adjacent points,,, as the center, and the radius; (3) Different from the descriptor, it divides each dimension into 11 intervals and counts the number of points on each dimensional interval, thus replacing the way the entire high-latitude space is divided and only superimposed on three dimensions The final descriptor has only 33 dimensions, which greatly reduces the dimensionality of the descriptor. (4) Compared with the descriptor, the overall complexity is greatly reduced and the calculation speed is faster, so it has high real-time application value. 

##  3. References 

>  [1] Rusu, Radu Bogdan, Nico Blodow, and Michael Beetz. "Fast point feature histograms (FPFH) for 3D registration." In 2009 IEEE International Conference on Robotics and Automation, pp. 3212-3217. IEEE, 2009. [2] Han Yifei, Yang Ziqian, Zheng Fu, Wang Yanqiu, Sun Zhibin. Improved point cloud registration algorithm based on FPFH and normal vector [J/OL]. Semiconductor optoelectronics: 1-6 [2021-08-26]. https://doi.org/10.16818/j.issn1001-5868.2021.04.001. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574297890
  ```  
#  III. Display of results 

 ![avatar]( 2020050419052284.png) 



--------------------------------------------------------------------------------

#  First, the code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220996
  ```  
#  III. Display of results 

 The curvature information of the first 10 points is output as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220996
  ```  


--------------------------------------------------------------------------------

##  First, the main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574289621
  ```  
>  Correspondences: The input is a list of corresponding point pairs, mean, stddev: The output is the mean and standard deviation of the square of the distance between corresponding point pairs. Note: The mean and standard deviation of the square of the distance between corresponding points are calculated, not the mean and standard deviation of the distance between corresponding points. 

##  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574289621
  ```  
##  III. Display of results 

 ![avatar]( 20210311122148667.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

![avatar]( 20210115122014605.gif) 

 CloudCompare software implementation:  

##  First, the principle of the algorithm 

 The principle of point cloud density calculation can be referred to: PCL point cloud average density calculation (version 1) PCL library has ready-made code for calculating the average density of points, which is different from the previous one in that the distance constraint is added when searching for K nearest neighbors, which avoids the influence of empty areas on the overall density and is more robust. It can be found at line 51 of the ia_fpcs .hpp folder, and it seems that the calculation cannot be called directly. So write the implementation process of the PCL library code yourself. The specific implementation code is as follows. 

##  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294961
  ```  
 ![avatar]( 20210115114108453.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   Calculate the area of a polygon from the point cloud of a given polygon 

##  2. Main functions 

    PCL :: calculatePolygonArea () Calculates the area of a polygon from the point cloud of a given polygon 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574288870
  ```  
##  3. Function source code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574288870
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574288870
  ```  
#  III. Display of results 

 ![avatar]( 8b677755abc949b8a117a1cc83a7230a.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Calculation formula 

   The center of mass refers to the center of mass, which is considered to be the imaginary point where the mass of the object is concentrated at this point. Usually, the coordinates of the center of mass of the object are calculated as follows: Among them, the coordinates of each mass point are the corresponding mass of the mass point. 

##  3. Main functions 

   The PCL :: compute 3D Centroid () function is used to calculate the centroid of the point cloud. The function has 12 overloading methods, the most commonly used one is shown below. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428892
  ```  
##  4. Function source code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428892
  ```  
>  Centroid is a [4x1] vector, the first three values store the centroid coordinates [X, Y, Z], and the last value is 1. 

#  Code implementation 

##  1. Method 1 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428892
  ```  
##  1. Method 2 

   It is directly called in PCA. For the specific application method, see: Application of PCL Principal Component Analysis (PCA) in 3D Point Cloud 

#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428892
  ```  
 ![avatar]( 6afc834ce0124bc397077f10ad1083c3.png) 

#  IV. Relevant links 

 [1] centroid.h  



--------------------------------------------------------------------------------

#  First, the main function 

##  1、std::min_element 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  
   Returns an iterator pointing to the smallest element in the range [first, last). The first version uses the < operator for comparison, and the second version uses the comp operator for comparison; if no other element is smaller than one, then the element is the smallest. If more than one element satisfies this condition, the iterator returns a pointer to the first element. 

 The behavior of this function template is equivalent to: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  
##  2、std::max_element 

   Returns an iterator pointing to the element with the largest value in the range [first, last). 

 Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  
##  3、std::minmax_element 

   Returns a pair where the iterator points to the first element with the smallest value in the range [first, last) and the second element with the largest value. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  
 Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  
#  Second, the maximum coordinate 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270822
  ```  


--------------------------------------------------------------------------------

#  First, the main function 

   Calculates the distance from a point outside the plane to the plane. This function is located in the header file #include < pcl/sample_consensus/sac_model_plane .h >. 

 Call method 1: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574245225
  ```  
 Call method 2: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574245225
  ```  
   Calculates the distance from a point outside the plane to the plane (signed convention) i.e. the function is located in the header file #include < pcl/sample_consensus/sac_model_plane h >. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574245225
  ```  
 Call method 2: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574245225
  ```  
#  Code implementation 

 The code calculates the distance from the centroid of the source point cloud to the plane where the target point cloud is located, and the fitting plane uses least squares fitting. For another implementation, see: PCL least squares fitting plane 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574245225
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574245225
  ```  


--------------------------------------------------------------------------------

#  First, the main function 

##  std::distance 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574243971
  ```  
   Count the number of elements between [first, last). 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574243971
  ```  
#  Second, the maximum coordinate and its index 

   Here, to calculate the minimum value of the coordinate Z value and its index, for example, to calculate the maximum value of x, y, the minimum value coordinate and its index, simply modify the code. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574243971
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574243971
  ```  


--------------------------------------------------------------------------------

 + 1. 3D point cloud  

 + 2D point cloud 

#  Three-dimensional point cloud 

##  1. Detailed explanation of the function 

   There is a point cloud and you want to get its maximum and minimum values on the three axes x, y, and z. You can use the pcl :: get Min Ma x 3D function. The function form is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
 This function has four overloading modes: Overloading mode 1: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
 Overload method 2: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
 Reload method 3: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
 Reload method 4: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
##  2. Code implementation 

   Calculate the axial maximum of the actual three-dimensional point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
##  3. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
##  4. Another approach 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
#  Two-dimensional point cloud 

##  1. Detailed explanation of the function 

   PCL :: get MinMax 3D function name comes with "3D", obviously not for two-dimensional point cloud, for two-dimensional point cloud calculation can use C++ 11 standard library #include < algorithm > min and max functions. The max () function is a library function of the algorithm header to find the maximum value from the two given values, it accepts two values and returns the maximum value, if the two values are the same, returns the first value. 

 Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
##  2. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
##  3. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095742534
  ```  
##  4. Test data 

 ![avatar]( 90bb48a586aa46a1830b687c3bf81afb.png) 

 2D point cloud  



--------------------------------------------------------------------------------

 + 1. Algorithm principle 1. Normal vector estimation 2. Normal vector orientation 3. Surface curvature 4. Reference 5. Understanding of normal vector orientation 6. CloudCompare

 Definition of PCL :: Normal 

 Several output methods of pcl :: Normal 

 + 4. Calculate the normals and display 1. Calculate the normals of all points in the input point cloud 2. Calculate the normals of a subset of the input point cloud data 3. Special operations

 + 5. Use OMP error handling 

 + 6. Calculate the normal of a point 

 + 7. Normal Orientation in PCL 

 + 8. Results display 

#  First, the principle of the algorithm 

>  Let me emphasize:

There are two methods to calculate the normal vector in PCL, one of which is the method in PCL :: Normal Estimation in this paper; this method is based on PCA principal component analysis; when fitting the neighborhood plane with least squares, KD tree is used to find neighborhood points. 

##  1, normal vector estimation 

   Based on the local surface fitting method for normal vector estimation: when the sampling surface of the point cloud is smooth everywhere, the local neighborhood of any point can be well fitted by the plane;

##  2, normal vector orientation 

   The normal vector calculated earlier is ambiguous, that is, only the straight line where the normal vector is located is obtained, but the direction of the straight line is not determined as the final direction of the normal vector.

##  3. Surface curvature 

 Smaller is a flatter neighborhood.  

 The larger it is, the greater the fluctuation of the neighborhood. 

##  5, understanding of normal vector orientation 

 ![avatar]( 20210312192602821.png) 

##  6、CloudCompare 

>  CloudCompare software also has the function of computing normal vector, here is the specific operation. 

 ![avatar]( 202012291022296.gif) 

 Normals > Compute: Compute the normals of the selected entity Normals > Invert: Invert the normals of the selected entity Normals > Orient Normals > With Minimum Spanning Tree: Reposition all normals of the point cloud in the same way (minimum spanning tree) Normals > Orient Normals > With Fast Marching: Reposition all normals of the point cloud in the same way (fast marching method) Normals > Convert to > HSV: Convert the normals of the cloud to the HSV color field Normals > Convert to > Dip and Dip direction SFs: Convert the normals of the point cloud to the two scalar fields Normals > Clear: removes normals for the selected entity  

#  Definition of PCL :: Normal 

>  The result calculated in compute (* normal) is: the x, y, z coordinates of the normal vector and the surface curvature curvature curvature. Its internal structure is: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
#  Three, pcl :: several normal output methods 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
#  IV. Calculate the normal and display it 

##  1. Calculate the normals of all points in the input point cloud 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
##  2. Compute the normal of a subset of the input point cloud data 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
##  3. Special operations 

>  Estimate its nearest neighbor using another dataset (which is relatively complete), estimating a set of surface normals for all points in the input dataset (sparse). This method works (similarly) for a downsampled point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
#  Fifth, the use of OMP error handling 

 When applying OpenMP, an error may be reported "User Error 1001: argument to num_threads clause must be positive". This is because the number of threads set must be positive, which may not be set in the program. Sometimes it is even set in environment variables, but it still reports an error. Manually set it as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
#  Calculate the normal of a point 

 The computePointNormal function can be used to calculate the normal of a single point at a given index. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
#  Normal Orientation in PCL 

   The known viewpoint is, the coordinates of any point are, and the normal vector is. For all normal vectors to orient them towards the viewpoint, the following formula must be satisfied: The setViewPoint (0, 0, 0) in the code is used to set the viewpoint: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
   To manually redirect the normal of a known point in PCL, you can use the following code: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574220414
  ```  
   If the dataset is integrated after registration from multiple captured viewpoints, then the above approach is no longer applicable. 

#  Results display 

 ![avatar]( 2020123109281681.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Calculation formula 

    Where, is the length of the three sides of the triangle and the area of the triangle. Can be obtained by Helen's formula. 

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574236425
  ```  
 PCL :: getCircumcircleRadius () calculates the circumcircle radius of a triangle composed of three points, and. 

##  3. Source code analysis 

 The functions of the commmon module do not need to be compiled, and can be used directly by including the header file. The source code is located in the PCL's #include < pcl/common/impl/common.hpp > path. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574236425
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574236425
  ```  
#  III. Display of results 

 The three points in the code example are relatively simple: you can verify it orally. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574236425
  ```  


--------------------------------------------------------------------------------

 + 1. Algorithm principle 1. Vector inner product 2. Vector outer product 3. Vector angle 4. References

 + 2. Code implementation 

 + 3. Results display 

 + 4. Related links 

 + 5. Python code 

#  First, the principle of the algorithm 

##   1. Vector inner product 

   For non-zero vectors, the inner product of vectors can describe the projection relationship between vectors. 

##   2. Vector outer product 

   For non-zero vectors, the direction of the outer product of the vector is perpendicular to the two vectors and is the directed area of the quadrilateral formed by the two vectors. The outer product exists only for three-dimensional vectors. 

##   3. Vector angle 

   For vectors, the angle between vectors is: Note: (1) when = 1, in the same direction as; (2) when = -1, in the opposite direction; (3) when = 0,; (4) The value range of the angle between the vector and is:. 

   From the definition of vector inner product and outer product, the angle of the vector can also be calculated by the following formula: in the point cloud, the normal vector usually needs to be oriented after calculating the normal vector. When the normal vector is not oriented, the formula for calculating the angle of the normal vector is as follows: 

#  Code implementation 

##  1. Call the function 

>  The operation of calculating the angle between two vectors is implemented in the PCL library, which can be realized by the pcl :: get Angle 3D call. The form of this function is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421018
  ```  
 There are two overloading methods, overloading method 1: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421018
  ```  
 Overload method 2: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421018
  ```  
>  The angle is expressed in radians and angle values. False means that the calculation result is expressed in radians, and the value range is [0, PI); true means that the calculation result is expressed in angles, and the value range is [0, 180 °). 

##  2. Source code 

 The specific implementation process in PCL is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421018
  ```  
##  3. Application examples 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421018
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421018


--------------------------------------------------------------------------------

#  I. Overview of the problem 

   PCL1.13.0 uses VTK9.2 for point cloud visualization. During use, it is found that setWindowName () in PCL1.13.0 will appear garbled when displaying Chinese names. As follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957417100
  ```  
 ![avatar]( beb272f991714190932d43707617cee2.png) 

#  II. Solutions 

    Vtk version 5.x display Chinese is a more difficult problem, basically need to modify the underlying code. Since vtk 6.1, its Chinese support is no longer a big problem. The key is that Chinese text needs to use utf-8 format. The following code is shown: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957417100
  ```  
 ![avatar]( 8b7000594f4d4776a32d20b49ccd8a75.png) 



--------------------------------------------------------------------------------

