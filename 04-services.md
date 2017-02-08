---
layout: lesson
root: .
title: Services in OpenRefine
minutes: 
---

## Augmenting data using a web service

For this lesson, we will use the Google Geocoding API (application programming interface) to take some of our Rodents data (massaged a bit from our current data), send to a web service, get the response, and then process that response. It won't be as accurate as the data already present in the JSON column, but it will show you the same process...

* Create text filter that only shows counties in Florida. The text filter is another handy way to slice your data.
* From the 'county' column, use the drop down menu to add a new column based on it. In the next menu we'll set the contents of the new column to be the values in 'county' and 'state' joined together:   

```cells['county'].value + "," + cells['state'].value.``` 

* Name that column something meaningful like 'county-state  '

* Using the county-state column, create a new column named 'geocode' that will store the responses from the web service. 

* This code should be 
```http://maps.google.com/maps/api/geocode/json?sensor=false&address=" + escape(value, "url")```

* Make sure to change the delay to something like 1500ms to 5000ms to keep the Google hounds at bay.
    
* Now create another new column, 'latlng', based on the new geocode column, with code to parse the JSON as follows:

```
with(value.parseJson().results[0].geometry.location, pair, pair.lat +", " + pair.lng)
``` 

Can you make sense of what this code is doing?

### Practice
- Using the same method as above, create a latlng column for all the locations in Washington state.
- Then, for all the geocoded rows you now have, create two separate columns, 'lat' and 'lng'.

Previous: [Saving and Exporting files and projects](03-save-export.html)
