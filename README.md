import cv2 as cv
import numpy as np


def bi_demo(image):#边缘保留滤波
    dst=cv.bilateralFilter(image,0,40,15)
    cv.imshow("bi_demo",dst)


def shift_demo(image):#均值迁移
    dst=cv.pyrMeanShiftFiltering(image,10,50)
    cv.imshow("bi_demo",dst)


src1 = cv.imread('D:/laoma1.jpg', cv.IMREAD_COLOR)  # 读入彩色图片
res=cv.resize(src1,(1400,800),interpolation=cv.INTER_CUBIC)#第二个参数用来设置输出图像的长宽
print(src1.shape)

cv.namedWindow("input image",1)
cv.imshow('image1', res)
bi_demo(res)
k = cv.waitKey(0)
