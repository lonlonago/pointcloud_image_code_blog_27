![avatar]( 20210115122014605.gif) 

 CloudCompare software implementation:  

##  First, the principle of the algorithm 

 The principle of point cloud density calculation can be referred to: PCL point cloud average density calculation (version 1) PCL library has ready-made code for calculating the average density of points, which is different from the previous one in that the distance constraint is added when searching for K nearest neighbors, which avoids the influence of empty areas on the overall density and is more robust. It can be found at line 51 of the ia_fpcs .hpp folder, and it seems that the calculation cannot be called directly. So write the implementation process of the PCL library code yourself. The specific implementation code is as follows. 

##  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294961
  ```  
 ![avatar]( 20210115114108453.png) 

