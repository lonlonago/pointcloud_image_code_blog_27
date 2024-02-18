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

