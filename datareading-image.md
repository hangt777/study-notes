#data reading-image
cv2.IMREAD_COLOR：彩色图像

cv2.IMREAD_GRAYSCALE:灰度图像
##显示图像

    import cv2#opencv读取的格式是BGR(蓝绿红)
    img=cv2.imread("E:\Opencv\learn material\image manipulation\dog.jpg")
	#图像的显示，也可以创建多个窗口
    cv2.imshow('img',img)
	#等待时间，毫秒级，也可以表示任意键终止
    cv2.waitKey(0)
    cv2.destroyAllWindows()

![dog image](http://"E:\Opencv\learn material\image manipulation\dog.jpg")

    import cv2#cv2在数组里的顺序是蓝绿红
	import matplotlib.pypolt as plt#matplotlib表示进行图像展示
	import numpy as np#numpy为基本数值工具计算包
	img=cv2.imread('cat.jpg')
##保存图像

1.API

cv.imwrite()

参数：文件名，要保存到哪里；要保存的图像

2.参考代码

	cv.imwrite('dog.png',img)

##总结

	import cv2 as cv#cv2在数组里的顺序是蓝绿红
	import matplotlib.pyplot as plt
	import numpy as np
	import matplotlib.pyplot as plit
	#读取图像
	img=cv.imread("E:\Opencv\learn material\image manipulation\dog.jpg")
	#显示图像
	plt.imshow(img,cmap=plt.cm.gray)
	plt.show()
	#图像保存
	cv.imwrite("image manipulation/dog.png",img)