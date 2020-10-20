# Hand-eye-Calibration
This repository provides code for single plane hand-eye calibration. To cite the work, please use the following paper:
S. Sharifzadeh, I. Biro, P. Kinnell, “Robust hand-eye calibration of 2D laser sensors using a single-plane calibration artefact”, 
Robotics and Computer-Integrated Manufacturing, 61, 101823, 2020.


The hand-eye calibration project include required files for a sample 3D reconstruction code. This code can be used for the data of one of the single plane circular patterns 
published in the above paper. 

In the code folder, all required files to run the code is available.  
For this aim, the scan files including the pose and rotation information should be read. They are located in ‘CircularPattern_run1‘ folder. By running the ‘ReadingFiles.m’ file
in the same directory where the 1-plane circular pattern scan data is located, two arrays ‘Scan Lines’ and ‘Poses’ will be obtained.
Then, by running the ‘SampleReconstruction.m’ code that uses these two arrays together with the hand-eye calibration matrix and the simulated circular points, 
the reconstructed lines exactly lie on a plain and match to the simulated data.
There are some comments within the reconstruction code that helps understanding the procedures.
------------------------------------------------------------------------------------------------------
In the following you can find the answers to some previous questions received on this code:

•	I see that you use some “compensation” for recovering the actual 3D pose of each points of the scan lines: for example in the R_form_compense2 function you are removing 
some constant delta values.
answer: the pose files include the transformation from robot to tool combined with estimated hand-eye by operator [rotations 0 and translations like deltaxyz) 
that should be cancelled to only have the base to tool transformation  

•	 In the main sampleReconstruction you remove a constant -19 value to the Z component, are these values (in mm I guess) computed in some particular way? What do they actually
represent? 
answer: The operator added a constant to the tool estimation when acquiring the poses, and asked me to cancel it at time of reconstruction.




