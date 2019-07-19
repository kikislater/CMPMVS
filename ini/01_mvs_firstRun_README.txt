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

[prematching]
minAngle=3.0						: Controls the minimal apical angle for each 3D point. (Set to a smaller (2.0 or 1.0) value when you have the cameras next to each other and you want to reconstruct objects which are further from the cameras.)

[grow]
minNumOfConsistentCams=6				: Number of neighbouring target cameras used for planesweeping

[filter]
minNumOfConsistentCams=2				: Controls the minimal number of cameras associated with each tetrahedralization vertex. (For densely captured scenes it is very usefull to set this parameter to 3 in order to obtain better result faster.)

[semiGlobalMatching]
wsh=4							: To speedup the computation you can change the wsh to 2 (or 1). WARNING: This can cause lower quality of final reconstruction in some situations.

[refineRc]
wsh=4							: To speedup the computation you can change the wsh to 2 (or 1). WARNING: This can cause lower quality of final reconstruction in some situations.


#do not erase empy lines after this comment otherwise it will crash ... bug


