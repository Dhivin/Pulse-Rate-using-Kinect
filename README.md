# Pulse rate using kinect


![](http://imgur.com/a/hYXeG)

The basic approach is simple. When a person's heart pumps blood, the volume of blood is pushed through various veins and muscles. As the blood pumps through the muscles, particularly the face, the more light is absorbed, and the less brightness the a web camera sensor picks up. This change in brightness value is very minute and can be extracted using matematical tricks. The change in brightness is periodic. In otherwords, a signal or wave. If we can match the signal/wave to that of a blood pulse, we can calculate the heart rate.

In order to match the change in brightness to a blood pulse we use the Independent Component Analysis (ICA) concept. This concept is the cocktail party concept and is the basis for finding hidden signals within a set of mixed signals. If you have two people talking in a crowded room, and you have microphones placed at various locations around the room, ICA algorithms let you take a mixed sample of signals, such as sound waves, and calculates an estimated separattion mixture of components. If you match the separate components to the orignal signal of a person speaking you have found that person in the crowded room.

This ICA concept is also known as blind source separation, and this project uses the JADE algorithm for R, to provide the separation matrix of commponents for the R,G, B, IR mixture of data. The separate components then have their signals extracted using a fast Fourier transform to find a matching frequency range of a heart rate.

