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

