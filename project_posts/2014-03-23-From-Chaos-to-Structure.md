This post presents several thoughts about **SoundMemory** feature. 

####Stage 1. Filling the memory.
Let the traveler is walking through previously unexplored area. During the walk, system gets traveler's location data with some predefined period of time (every 1 minute, for example). After location data retrieving server-side generates waveform (see *Simple spatial synth* post for detail) and save it into database, along with current traveler’s coordinates. At this stage we create relation in database between the area of the city and the sound, waveform. 
![memory1](../project_images/memory_gen.png?raw=true "memory1")

####Stage 2. Applying of SoundMemory.
After a while, other traveler is walking in this area. It could be not exactly the same route, but closer to it.
During the sound's generating, the *Generator* gets previously saved waveform for current area and makes *The Operation* between just created waveform and *SoundMemory's* form (marked with grey color). Thus, traveler hears combination of these waveforms.
![memory2](../project_images/memory_apply.png?raw=true "memory2")

*The Operation*( (triangle symbol on picture) is the subject of researches. Possible variants:
- echo/delay effect (SoundMemory waveform processing with  echo effect);
- simple addition of waveforms;
- modulations;

Problem here is from one hand is to make clear for traveler to hear and define his own waveform and from the other - creating complex sound.

####Stage 3. Musical information retrival.
For melodical approach we could retrival possible note information from the *SoundMemory* for current area or point.
![note](../project_images/note retrieval.png?raw=true "note")  
Interesting technology solution for this is Essentia library for audio analysis and audio-based music information retrieval:
http://essentia.upf.edu/
Further development of this stage is musical scale forming, creating from clusters of notes and relations between them.

Reading for inspiration in context of theme - **A Geometry of Music** by Dmitry Tymoczko.
http://dmitri.tymoczko.com/geometry-of-music.html 

