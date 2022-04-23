# Image_resize_Intern
converts any image into 720 by 720

Created on Tue Apr 12 09:16:59 2022

@author: Kurian Ambat
"""
import cv2 
import numpy as np 
import os 
import glob

source_dir= "D:\DICOM_VI_Intern\RAW_DATA"   #TODO:your source folder
dest_dir= "D:\DICOM_VI_Intern\RESIZED_DATA"     #TODO: your destination folder
counter = 1
for image in glob.glob(source_dir+"/*.jpg"):
    n = cv2.imread(image) 
    sized = cv2.resize(n,(720,720), interpolation = cv2.INTER_AREA)
    file_name= dest_dir + "/%02d.jpg"%(counter)
    cv2.imwrite(file_name,sized)
    counter +=1
