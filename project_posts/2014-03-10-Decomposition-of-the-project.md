Application naturally decompose on two parts - client part and server part.

## Thin-client version
In this version most of work performed on server-side - client application only sends location data and receives audio stream.
*Pros:*  easy logic on client-side, less energy consumption.
*Cons:* high internet traffic, potentially delay in response.  


![Thin-client version](../project_images/thin_client.jpg?raw=true "Thin-client version")

Server-side consist of the following functional modules:

####Location data collector
*Purpose:* Collect location data from connected clients and save it into database.
*Implementation:* Server-side web-application. One instance for each connected user. Implementation languages: Dart, C++, Java. Data received via Google map API or directly from device in JSON format. In demo purpose online gps-tracking service http://livegpstracks.com/  can be used which send location data in JSON format on HTTP request. This service was already in my “Concert for city and 4 musicians” media-performance.  

####Sound Generator
*Purpose:* Generate soundscape from location data. Data queried from database using raw SQL or XML. Module output is separate files or audio streams which directed to the Mixer module.
*Implementation:* Possible languages:  
- CSound: http://www.csounds.com/
- PureData (Max/MSP): http://puredata.info/
- Sig++: http://sig.sapp.org/
- SAOL: http://www.cs.berkeley.edu/~lazzaro/sa/
- sfront: http://www.cs.berkeley.edu/~lazzaro/sa/sfman/
- C++, Java.    

Additional links: http://linux-sound.org/swss.html

Main logic of the sound generation concentrated in this module. This is the core of application and it needs more investigations and experiments. Behavior of module can be adjusted by using Strategy pattern in implementation. *SoundMemory feature* will also be implemented in this module.  

####Mixer   
*Purpose:* Mix sound source from Generator to output stream (or file) for Streamer.
*Implementation:* Mixer generate several streams, one for each connected user. Unlike Generator,  Mixer is some kind of “user-specific” module. Mixer module interprets database data as source for several parameters of final mix for soundscape, to ajust Generator output for each user. Most of common music mixing technics can be used here.
Possible languages:  CSound, PureData (Max/MSP), C++.  

####Audio Streamer  
*Purpose:* Stream final audio back to user’s application.
*Implementation:* One instance for each connected user (or claster of users). Can be implemented via Icecast. 
http://www.icecast.org/
 
####Database
*Purpose:* To store locations of users (depersonalized) with timestamp. It is used as data source for Generator and Mixer.
*Implementation:* no specific requirements at the moment.  


## Rich-client version  
In this version server part sends only instructions for sound generating via OSC. Client application generate sound following this instruction and mixing depending on it's own location data.
*Pros:* low internet traffic (OSC message is a text), more flexible local mix (can be used data from device sensors), most of audio processing enviroment (Pd, CSound) have native OSC support.
*Cons:* potentially more energy consumption, more complex global sync, more complex overall logic of client.  

![Rich-client version](../project_images/rich_client.jpg?raw=true "Rich-client version")

####Score Generator
Purpose same as Sound Generator in Thin-client version but generates only instructions for sound creation and send it via OSC to clients.  




