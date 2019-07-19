In this directory are located several ini files that might be usefull in different situations.

For simplicity we it is needed to run:
CMPMVS.exe fileName.ini
but we assume that user runs it from commandline and from directory where the CMPMVS.exe is located!
Further we assume:
CMPMVS.exe fullPathToIniFileName\fileName.ini

For example:
The CMPMVS.exe is loceted in directory D:\CMPMVS_0_5_1\
The statue.ini is located in directory D:\CMPMVS_0_5_1\ini\
The command line should look like:
D:\CMPMVS_0_5_1>CMPMVS.exe D:\CMPMVS_0_5_1\ini\statue.ini


For each fileName.ini there is fileName_README.txt file. See fileName_README.txt for more details on parameters.


--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------


First, it is needed to run:
CMPMVS.exe 01_mvs_firstRun.ini
It will precompute all needed data and usually takes at least 60% of overall time. All needed data are located in global:workDirName ("_tmp") directory.
DO NOT ERASE the global:workDirName ("_tmp") directory when you want to furter process other things.

Next, it is needed to decide if you want 
(i) one mesh in level of detail that will fit to the largeScale:planMaxPts (3000000) number of 3D points or 
(ii) if you want the reconstruction in largest possible level of detail.

(i) it is needed to run:
CMPMVS.exe 02_mvs_limitedScale.ini
It will reconstruct mesh and save it into global:dirName\_OUT directory.

(ii) it is needed to run:
CMPMVS.exe 02_mvs_largeScale.ini
It will reconstruct mesh and save it into global:dirName\_OUT_LARGE_SCALE directory. If the scene is larger than largeScale:planMaxPts it will be reconstructed by parts. 
Each part is watertight mesh. All the parts together produce one globally visibility consistent mesh without artefacts on the borders of the neighbouring parts. 
The result should be the same as it would be in (i) when the largeScale:planMaxPts is large enough. Due to memory limitations it needs to be computed by parts. 
Using this approach the CMPMVS binary is able to reconstruct basically unlimited large scenes in highest possible level of detail.


--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------


Next, you can choose one (or more) of the following ini files to postprocess a resulting mesh:
03_mvs_retexture.ini		: generate textured mesh
03_mvs_simplify.ini		: generate simplified mesh (user can choose number of triangles in simplified mesh)
03_mvs_DEM_ortoPhoto.ini	: generate DEM and ortoPhoto from the mesh
03_mvs_video.ini		: generate flyover video from the mesh
03_mvs_mergeTextrueFiles.ini	: if the mesh has multiple texture files user can regenerate it into new mesh with one texture file


--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------


The default.ini is basically the sequence:
CMPMVS.exe 01_mvs_firstRun.ini
CMPMVS.exe 02_mvs_limitedScale.ini
CMPMVS.exe 03_mvs_simplify.ini
CMPMVS.exe 03_mvs_DEM_ortoPhoto.ini
CMPMVS.exe 03_mvs_video.ini
in one ini file.


--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------


The default_largeScale.ini is basically the sequence:
CMPMVS.exe 01_mvs_firstRun.ini
CMPMVS.exe 02_mvs_largeScale.ini
in one ini file.


--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------

In lionHanauIniExample directory there is example sequence of ini files for first five images of lionHanau dataset for testing purposes. None that you need to replace "D:\jancom1\DATA\lionHanauTest\cmp.nvm.cmp\00\data\" with your path where the lionHanau dataset is located in all ini files.

--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------


You can georegister the reconstruction once the DEM and ortoPhoto is created and regenerate the georegistered DEM and ortoPhoto. Following sequence is needed to do that:
04_01_mvs_visualize_given_GPS.ini	:
	- given GPS coordinates are listed in the fullPathDEMDirName\givenMarksGPSTxtFileName.txt file.
	- this will create the fullPathDEMDirName\givenMarksGPSTxtFileName.kml file that can be opened by googleEarth in order to be able to visualize them
	- the given GPS coordinates must be in following format:
		- in each line one GPS coordinte of a landmark
		- the GPS coordinate must be in decimal degrees format : Latitude Longitude Altitude
		- For example :
			50.099052 14.419517 223.633983
			50.099095 14.419668 223.570112
			50.098981 14.419739 223.736305
			50.099037 14.419774 223.743006
 
04_02_mvs_align_to_GPS.ini		: 
	- user needs to write down list of pixel coordinates from previously generated ortoPhoto image into the new fullPathDEMDirName\demMarksPixelsTxtFileName.txt file of the landMarks corresponding to the list of the GPS coordinates of the landmarks
	- this will compute the transformation from the global coordinate system of the mesh to the GPS

04_03_mvs_georegister_DEM_ortoPhoto.ini	: 
	- this will regenerate DEM and ortoPhoto so that they will be geopregistered



