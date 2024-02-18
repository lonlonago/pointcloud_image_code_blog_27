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

