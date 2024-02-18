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

