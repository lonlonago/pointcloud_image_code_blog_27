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

