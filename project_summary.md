# SoundSphere

## Authors
- Alexey Kalinin, http://github.com/alexptic
- Vladimir Doroshevskiy

## Description
###Core idea

Network sonic service. Users (“travelers”) can connect to the web-service using the custom smartphone application. The application sends travelers’s coordinates to the server. The server collects the location data of the travelers, generates a music composition (soundscape) from it and streams it back to the traveler. Movement of the traveler changes the soundscape.  Thus, the traveler becomes a listener and a “source” of the sound at the same time.

### Core features

####Individual mix

Each user hears thier own version of composition (soundscape) depending on thier location. The server generates an individual mix for each connected user. For example - highlights melodic line, specific for current area, or changes timbral characteristics of sound. 

####Sound memory of the area

The amount of users, which visited a particular area of the city, affects the next generated sounds from this area.The area has its own memory. For example - streets where there have already been 10 users, create different sounds than streets on which there have been only 2 users, and both sound different than an abandoned street.

## Images & Videos
Experimental musical performance at the Night of the Museums 2013 for Moscow Museum of Modern Art.
Score, performed by musicians, was generated in real-time based on the GPS data from movements of travelers in the city.
http://www.youtube.com/watch?v=a7s7hlUYkms
