# AutoDrive
Use TensorFlow and openCV 

模拟自动驾驶

semi-finished product!

## PS: 现实环境中的测试：https://github.com/YanZiQinKevin/object_detection/blob/master/README.md  


Self_ driving at Euro Truck Simulator2
 -----《欧洲卡车模拟2》


#Implementation:

Control part: Use win32 api to control keyboard, which self play Euro Truck Simulator2.

Trace the traffic-line part： (openCV):

  1, transfer original image to gray  cv2.COLOR_BGR2GRAY
  
  2, than using Canny to due with the image:
  ![Canny](https://github.com/YanZiQinKevin/AutoDrive/blob/master/screenshoot/truck_Canny.png)
  作用是勾勒路线的轮廓
  
  3， using cv2.HoughLinesP() function to analyze 道路的虚线和实线
         原理是计算条线之间的空隙。而实线比较好处理。
         ![enter image description here](https://github.com/YanZiQinKevin/AutoDrive/blob/master/screenshoot/truck_line.png)
   
 4， Using two lines to figure out "Turn", and the signal will call  win32 to keyboard.


二， Use TensorFlow to recognized front of view, such as Car or Traffic_light. 
      This part based on  :[object_detection](https://github.com/YanZiQinKevin/object_detection)
		
Problem： 通过CNN训练模型，但还是未能解决红绿灯信号识别的问题，打算用openCV做颜色归纳
![enter image description here](https://github.com/YanZiQinKevin/AutoDrive/blob/master/screenshoot/truck_light.png)  
行人检测
![enter image description here](https://github.com/YanZiQinKevin/AutoDrive/blob/master/screenshoot/WechatIMG60.jpeg)
