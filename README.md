# flighttrack
INTRODUCTION:

Using Android Termux Terminal API , collected GPS data for flight from Mumbai to Kolkata city and plotted the GPS coordinates using python gmplot and Google Maps API Key

Link : https://asura22nov.github.io/flighttrack/

REQUIREMENTS:

1. Android Mobile with TERMUX terminal app installed

2. Google Maps API key

PROCEDURE:

1.Get Familiar with termux-location command in your Android Mobile

$ termux-location

{

  "latitude": 22.5717891
  
  "longitude": 88.4332954
  
  "altitude": -39.0
  
  "accuracy": 20.759000778198242
  
  "bearing": 0.0
  
  "speed": 0.0
  
  "elapsedMs": 4
  
  "provider": "gps"
    
}

2.Create a shell script to record the gps records to a file in your moile

#!/bin/bash

while :

do

	echo`termux-location |head -n9|tail -n8|awk -v ORS= -F: '{print $2}'` >> location.txt
	
	sleep 30
	
done


3. Run the script during your flight 

$termux-loc.sh &

4.After your flight, format your Latitude and Longitude data accordingly to the use them in the python gmplot.

indigo-flight-mumbai-kolkata.py

5. Generate your Google Maps APIs.


REFERENCE:

https://wiki.termux.com/wiki/Termux-location

https://wiki.termux.com/wiki/Termux:API

https://developers.google.com/maps/documentation/embed/get-api-key

https://github.com/vgm64/gmplot

https://www.tutorialspoint.com/plotting-google-map-using-gmplot-package-in-python


