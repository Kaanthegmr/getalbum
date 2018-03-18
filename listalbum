#!/usr/bin/python
#-*- encoding:utf-8 -*-
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
import time
import os
import sys
a=0
arg=sys.argv[1]
driver = webdriver.Chrome()
driver.get(arg)
urls=driver.find_element_by_id("contents").find_elements_by_css_selector(".style-scope.ytd-playlist-video-renderer")
mps=[]
albumname=raw_input("Album Name:")
for i in urls:
    if i.get_attribute("href")!=None:
        mps.append(i.get_attribute("href").split("&list")[0])
print "\nUrls added"
driver.close()
os.system("mkdir ~/%s" %(albumname))
time.sleep(3)
os.chdir("~/%s/" %(albumname))
for i in mps:
    os.system('youtube-dl -x --audio-format mp3 --output "%%(title)s.%%(ext)s" %s > output.dat' %(i))
    sys.stdout.write('\rDownloaded:(%s/%s)' %(mps.index(i)+1,len(mps)))
    sys.stdout.flush()
print "\nDone"
#detailed explanation: https://www.youtube.com/watch?v=dQw4w9WgXcQ
