# -*- coding: utf-8 -*-
"""
Created on Thu Jan 24 19:31:29 2019

@author: wrm
"""
In this project, we could implement pencil-drawing effect towards images. The "Mitao" folder contains the original image,
and the image after the processing.
"""

"""
import numpy as np
from PIL import Image
"""
Here we use the Python Image Library to deal with the images. openCV and other tools maybe useful as well
"""
im0=Image.open("C:/Users/wrm/Desktop/MitaoCat/jiahe.png")
love=np.array(im0)

"""
Ouput the shape and dtype of the photo
"""
#print (love.shape)
#print (love.dtype)

"""
Output the finished photo([255,255,255]-the original photo)
"""

love_orig_L=[255,255,255]-love
im1=Image.fromarray(love_orig_L.astype("uint8"))
#print (b)
#print (im1.show())

"""
Output the gray-sacle photo and the finished photo(255-the original photo)
"""
im2=im0.convert("L")
love_2=255-np.array(im2)
im2_revised=Image.fromarray(love_2.astype("uint8"))
#print (im2_revised.show())

"""
Output the hand-draw picture
"""
depth=50
grad=np.gradient(np.array(im2))
#print (grad)
grad_x,grad_y=grad
#print (grad_x)
#print (grad_y)
grad_x=grad_x*depth/100
grad_y=grad_y*depth/100
A=np.sqrt(grad_x**2+grad_y**2+1)
uni_x = grad_x/A
uni_y = grad_y/A
uni_z = 1./A

vec_el = np.pi/2.2                   
vec_az = np.pi/4.                    
dx = np.cos(vec_el)*np.cos(vec_az)   
dy = np.cos(vec_el)*np.sin(vec_az)   
dz = np.sin(vec_el) 

hand_draw=255*(dx*uni_x+dy*uni_y+dz*uni_z)
hand_draw=hand_draw.clip(0,255)

im_hd=Image.fromarray(hand_draw.astype("uint8"))
#print (im_hd.show())
im_hd.save("C:/Users/wrm/Desktop/MitaoCat/cat_jiahe.jpg")
#Save the image to a certain location.
