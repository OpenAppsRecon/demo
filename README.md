# open recon and open apps demo
## Table of Contents
**[How to setup the python environment](#How-to-setup-the-python-environment)**<br>
**[How to modify OpenApps sample](#How-to-modify-OpenApps-sample)**<br>

## How to setup the python environment

open recon and open apps demo files
1.	Download the PyCharm community edition and install it.
https://www.jetbrains.com/pycharm/download/?section=windows
2.	Download Python and install it.
https://www.python.org/downloads/
3.	Point to Python installed directory in the command prompt.
     ![image](https://github.com/punithbv06/open_recon_apps_demo/assets/33754175/47116361-4f7c-408f-94f5-a72619e9aa45)

   install required packages
   python.exe -m pip install SimpleITK 
   python.exe -m pip install pydicom  
   python.exe -m pip install numpy  
   python.exe -m pip install matplotlib 
   
   
5.	Open a new project in Pycharm and add a new Python file.
  a.	Print(“Welcome to workshop on open recon/Apps”)
  b.	 Run the welcome.py file.

Enjoy the session

### How to modify OpenApps sample
1. Browse the folder 'OpenApps' in Project pane present to the left of your workspace.
2. Double click on the file 'main.py'
   ( *This is a sample program. 
     It reads 2 dicom series – T1 images and Flair images which are available in the 'data' folder, finds the difference between T1 and Flair images, displays the result in the pane right side of your window, 
     and converts the result which is in numpy array to DICOM images. Finally it exports the results to syngo via.* )
3. Replace the logic of finding the difference between two images to your own logic. For instance thresholding, inverting, masking the images etc.
   It can be done in the function "def computeResult(t1_data, flair_data)" in the line number 52
  
   ```
     def computeResult(t1_data, flair_data):  
         Logger.info("Computation of result started")
         t1_data /= np.max(t1_data)
         flair_data /= np.max(flair_data)
         difference = np.abs(t1_data - flair_data) * 4095
         difference = difference.astype(np.uint16)
         Logger.info("Computation of result finished")
         return difference
   ```
5. Select the current file in ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/b6fc629e-a4c2-4d9d-b0c2-c08e64a72e06) in the top right corner of the window
6. Run the application by clicking the button ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/57f76a87-b6fe-41e7-9b06-cb5cdbec9122) in the top right corner of the window
7. You can also debug the applicaiton by clicking the button ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/a2e80267-a69f-43d2-91e0-a8340d24ca6d) in the top right corner of the window  
