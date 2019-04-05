# file_grouping_k_means

objective is to copy file from pen drive to the specified group of folders automatically when we insert the pen drive.
Below is the sample code to detect the drive of the inserted pen drive.

import string
from ctypes import windll
import time
import os

def get_drives():
    drives = []
    bitmask = windll.kernel32.GetLogicalDrives()
    for letter in string:
        if bitmask & 1:
            drives.append(letter)
        bitmask >>= 1
    return drives


if __name__ == '__main__':
    before = set(get_drives())
    pause = input("Please insert the USB device, then press ENTER")
    print ('Please wait...')
    time.sleep(5)
    after = set(get_drives())
    drives = after - before
    delta = len(drives)

    if (delta):
        for drive in drives:
            if os.system("cd " + drive + ":") == 0:
                newly_mounted = drive
                print ("There were %d drives added: %s. Newly mounted drive letter is %s" % (delta, drives, newly_mounted))
    else:
        print("Sorry, I couldn't find any newly mounted drives.")





# Methodology
# 1.	Converting file name into weight array

Function for converting file name to weight array
def weightmat(filea,fileb):
    c=""
    weight=0
    for i in filea:
        c+=i
        if c in fileb:
            weight+=1
        	        else:
            return weight
    return weight

# 2.	Converting extension into weight array
Function for converting extension into weight array.

def weightext():
if ext.upper() in audiosformat:
            return (0)
        elif ext.upper() in videosformat:
            return (100)
        elif ext.upper() in imagesformat:
            return (200)
        elif ext.upper() in docsformat:
            return (300)





# 3.	Merging two weight array and form weight matrix 



    costfname=[]
    for i in range(len(fname)):
        mxwt=0
        for j in range(len(fname)):
            if i!=j:
                currwt=weightmat(fname[i],fname[j])
                if mxwt<currwt:
                    mxwt=currwt
        costfname.append(mxwt)

# 4.	Find centroids in the weight matrix and make clusters of file with the found centroid.
kmeans = KMeans(n_clusters=6).fit(mxt)



# Steps of installation
1. git clone this project or download it from github page.
2. Install python 3.x
3. There is no pre configuration just plug your pendrive or any external device it will identify it and arrange all the files properly
  e.g pictures in pictures folder, videos in videos and doc in document.
  
4. you can easily find the cluster on the output in console.



 Complete Code is in proj.py

Any modification is highly welcomed


