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
