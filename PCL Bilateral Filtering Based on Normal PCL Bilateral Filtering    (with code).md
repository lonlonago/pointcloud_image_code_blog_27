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

