[global]
dirName="fullPathDirName\"				: The full path to the directory containing data (the '\' is needed!)
prefix=""						: Prefix of the images names (default four digits number).
imgExt="XXX"						: Extension of the images.
ncams=XX						: Number of the images.
width=XXXX						: Width of the images.
height=XXXX						: Weight of the images.
scale=1							: The input images (and P matrices) in in the dirName are downscaled scale-times and saved to the workDirName. The pipeline further works with downscaled images and corresponding P-matrices. It is usefull when you have huge images in order to speed-up the computation. We usually use scale=2 for large images calibrated by VisualSFM, then our pipleine (due to several reasons) gives slightly better results.
workDirName="_tmp"					: The directory name that will contain application temporary data. The directory will be created as the subdirectory of the dirName directory.
doPrepareData=TRUE
doPrematchSifts=TRUE
doPlaneSweepingSGM=TRUE
doFuse=TRUE
nTimesSimplify=10					: Set this to non-zero value if you want to have nTimesSimplify times simplifyed result too.

[uvatlas]
texSide=4096						: The resolution of texture file. Must be a power of 2.
scale=1							: The downscale factor of the texture file. (For large datasets we recommend to set texSide=8192 and scale=2 (or 4) in order to obtain smaller number of texture files.)

[prematching]
minAngle=3.0						: Controls the minimal apical angle for each 3D point. (Set to a smaller (2.0 or 1.0) value when you have the cameras next to each other and you want to reconstruct objects which are further from the cameras.)

[grow]
minNumOfConsistentCams=6				: Number of neighbouring target cameras used for planesweeping

[filter]
minNumOfConsistentCams=2				: Controls the minimal number of cameras associated with each tetrahedralization vertex. (For densely captured scenes it is very usefull to set this parameter to 3 in order to obtain better result faster.)

[hallucinationsFiltering]
useSkyPrior=FALSE					: Set this to TRUE if you have just street-view images (i.e. city-like dataset) (first camera must be landscape oriented i.e. first camera y-axis must be almost equal to a gravity vector!) in order to filter out hallucinations from the sky area. We recomend to first reconstruct the dataset (constisting of street-view images only!!!) using useSkyPrior=FALSE and if you are not satisfied with the result (i.e. there are a lot of hallucinations in the sky area) then we recomentd to try to use useSkyPrior=TRUE.
doLeaveLargestFullSegmentOnly=FALSE			: Set this to FALSE if you want to have multiple objects reconstructed. Having this parameter TRUE means that the software will automatically segment the resulting mesh into connected components and put just the largest one into the output.
doRemoveHugeTriangles=TRUE				: This option causes that the appliaction will remove huge triangles. It is recomended to have turned it on!

[largeScale]
doGenerateAndReconstructSpaceMaxPts=TRUE		
doGenerateSpace=TRUE
planMaxPts=3000000					: Maximim number of vertices in the tetrahedralization. Set it to smaller value if you have less than 12GB of ram.
doComputeDEMandOrtoPhoto=TRUE				: Set it to FALSE in order to turn off the DEM and OrtoPhoto computation. 
doGenerateVideoFrames=TRUE				: Set it to FALSE in order to turn off the video.avi and stereo_video.avi computation. 

[generateVideoFrames]
nintermed=20						: The number of frames between two camera positions in automatically generated flyover-camera-positions video. We recommend to set this value to 10 or 5 for large datasets in order to speedup the computation time.

[DEM]
demW=8000						: The resolution of the 16-bit gray level DEM.png and DEM_ortoPhoto.tiff images.
demH=8000

[semiGlobalMatching]
wsh=4							: To speedup the computation you can change the wsh to 2 (or 1). WARNING: This can cause lower quality of final reconstruction in some situations.

[refineRc]
wsh=4							: To speedup the computation you can change the wsh to 2 (or 1). WARNING: This can cause lower quality of final reconstruction in some situations.


#do not erase empy lines after this comment otherwise it will crash ... bug


