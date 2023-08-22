# open recon and open apps demo
## Table of Contents
**[How to setup the python environment](#How-to-setup-the-python-environment)**<br>
**[How to modify OpenApps sample](#How-to-modify-OpenApps-sample)**<br>

## How to setup the Python environment

open recon and open apps demo files
1.	Download the PyCharm community edition and install it.
https://www.jetbrains.com/pycharm/download/?section=windows
     * While installing PyCharm, please check the checkbox “Create Desktop Shortcut”.      
![image](https://github.com/OpenAppsRecon/demo/assets/142770538/58ae3a7e-2892-4405-a9e2-879fb0427db4)



2.	Download Python and install it. Remember the path where Python is installed.
https://www.python.org/downloads/

3. Open PyCharm by double-clicking on the icon (as shown below) on your desktop
   ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/3047ddad-19fc-4c68-8cce-b7dfef8de40e)

4. When the PyCharm is started the first time after installation, the following popup will appear.
        Please click OK and continue
   ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/58254e72-e9aa-4267-a1d2-27e23e97179d)

5. PyCharm opens and it appears as shown below
   
     ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/57e82f8b-f37e-4706-9df7-0e2511b26473)

6. Click on the button  ![image](https://github.com/OpenAppsRecon/demo/assets/142770538/48018137-a52f-43cc-abd0-ed28e018b1b0) to open the project, below window appears

7. Browse to the folder where you have downloaded the project from the GitHub repository.
    ![image](https://github.com/OpenAppsRecon/demo/assets/33754175/4c9f152e-7c7b-495e-a8ea-ef9448b23f16)
    ![image](https://github.com/OpenAppsRecon/demo/assets/33754175/2b8c2556-adfa-4b0c-ab60-9dc83d3eb25e)
    ![image](https://github.com/OpenAppsRecon/demo/assets/33754175/8e74b232-e19d-4eca-bfb2-5e204394351f)
8.  Click on "This Window" to open the project.


   install required packages
   python.exe -m pip install SimpleITK 
   python.exe -m pip install pydicom  
   python.exe -m pip install numpy  
   python.exe -m pip install matplotlib 
   
   
9.	Open a new project in Pycharm and add a new Python file.
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
