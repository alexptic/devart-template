Main goal of this feature is creating realistic representation of sound's sources in virtual space and helps users to define their placement and feel their presence in SoundSphere.

For creating individual mix for each traveler-listener could be used standard sound mixing techniques with some adaptation.
Since user would listen soundscape through individual headphones, here appears limitations in using of physical sound sources - its only two.  But it's enough to make clear and distinguishable mix of all  virtual sound sources. 

![mixing](../project_images/mixing.png?raw=true "mixing")

Two standard techniques could be used.

1. Panning
With variation in amount of audio signal for each speaker of headphones we could define virtual (hearable) placement of sound’s sources in horizontal direction.    

2. Distance.
Applying filtering effects to sound source we could define virtual (hearable) placement of sound sources in the depth.
Effective technics here are:
- filtering of high-frequency component of the sound from distant sources  (when distance to the source is increasing);
- more reverberation applying and more dissipation to the sounds from distant sources; 
- small or no reverberation to closer sources and to the waveform of current traveler;

Mixing of sounds sources from behind of the traveler is quiet tricky since we use two-channel headphones. Good approach and could be solution for all mixing feature is using 3D FMOD engine. In addition, FMOD is integrated in OF platfrom.
http://www.fmod.org/

