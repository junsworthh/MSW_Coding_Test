# MSW_Coding_Test

import json
import os
import sys
import urllib2
import requests

TempLat = input("Enter required latitude in the decimal-degree format: ")		
print(TempLat)

TempLong = input("Enter required longitude in the decimal-degree format: ")			
print(TempLong)

print("You have entered a longitude of " + str(TempLong) + " with a latitude of " + str(TempLat) + ".")

Lat = [TempLat,TempLat]			#Lat = [50.4164582,50.4164582] for NEWQUAY
Long = [TempLong,TempLong]		#Long = [-5.100202299999978,-5.100202299999978] for NEWQUAY

API_key = "AIzaSyAoqck6QwJBr-dQR2V9w3q0v1jq9DNCsgs"

url = "https://maps.googleapis.com/maps/api/place/nearbysearch/json?location=" + str(Lat[0]) + "," + str(Long[0]) + "&radius=1000type=lodging&keyword=surf&key=" + API_key
temp=urllib2.urlopen(url)
B=json.load(temp)

try:
	print(len(B))
	for item in B:
		# print(B[0]["location"]['latitude'])
		# print(item)
		# print(B[0]["name"])
		print(item["name"]["rating"]["opening hours"])
except:
	print("No known lodges in this area. Camp out brah!")



## TECHNICAL QUESTIONS ##
#
#
# 1) I would say I spent a few hours researching the basics of python, multiple hours of setting up a build system and downloading the right packages (and attempting to
# install both the requests and urllib2 modules) and then about 3-4 working days of coding.
#
# 2) Using the PIP Package Installer within terminal to successfully and efficiently install the correct packages (once I'd learned about PIP) made my life a lot easier!
#
# 3) I would run the code and see what problem the console gave me, and if I was unaware of what was stated in the console I would research it online and see if anybody 
# else had been having similar problems with their code which would hopefully give me a solution to the problem.
