https://compileralchemy.substack.com/p/apriltags-why-robotics-invented-its

April Tags are used as [Fiducial marker](https://en.wikipedia.org/wiki/Fiducial_marker) as seen in robotics in real life.
- an object placed in the field of view of an imaging system as a point of reference

Why are QR codes not sufficient given that they can contain much more information?
- Only the localization markers of QR codes take up 268 pixels, in contrast, 
	- AprilTags take 49 to 100 pixels including the payload

April is a reputable [robotics lab](https://april.eecs.umich.edu/) from the University of Michigan

April tag 
- enables a system to localize features of the 6 degrees of freedom (DOF) from a single image
- 6 DOF, 3 for translation and 3 for rotation

<img src="/images/orientation.png" style="display: block; margin: auto;"width="300"/>
Different families of April Tags:
![[Pasted image 20250305192715.png]]

Naming Convention:
![[Pasted image 20250305192750.png]]
- more bits means more tags are available to choose from
- high hamming distance means the tag can be properly identified despite errors
	- Hamming distance is a measure between strings or the amount of substitutions needed to change from one string or vector to the other
	- AprilTag maintains a minimum hamming distance between tags to ensure better detection, but it also means that fewer tags are available

Obviously, fewer bit tags can be read at longer distances if the tags are of the same sizes
- 16H5 for example can be read at longer distances than 52H13.

