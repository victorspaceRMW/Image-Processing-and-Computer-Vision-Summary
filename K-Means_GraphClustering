# -*- coding: utf-8 -*-
"""
Created on Sat Feb 16 06:35:54 2019

@author: wrm
"""

import numpy as np
import pandas as pd

from PIL import Image
#im=Image.open("C:/Users/wrm/Desktop/lady.jpg")
def loadData(filePath):
    f = open(filePath,'rb')
    data = []
    img = Image.open(f)
    m,n = img.size
    for i in range(m):
        for j in range(n):
            x,y,z = img.getpixel((i,j))
            data.append([x/256.0,y/256.0,z/256.0])
    f.close()
    return np.mat(data),m,n

imgData,row,col = loadData('C:/Users/wrm/Desktop/lady.jpg')

#print (imgData.shape)
#print (row)
#print (col)

from sklearn.cluster import KMeans
label=KMeans(n_clusters=4).fit_predict(imgData)
#print (label.shape)

label = label.reshape([row,col])
pic_new = Image.new("L", (row, col))
for i in range(row):
    for j in range(col):
        pic_new.putpixel((i,j), int(256/(label[i][j]+1)))
pic_new.save("result-bull-4.jpg", "JPEG")
