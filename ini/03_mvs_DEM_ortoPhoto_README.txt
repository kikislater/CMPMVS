[global]
dirName="fullPathDirName\"
prefix=""
imgExt="jpg"
ncams=XX
width=XXXX
height=XXXX
scale=X
workDirName="_tmp"
doPrepareData=FALSE
doPrematchSifts=FALSE
doPlaneSweepingSGM=FALSE
doFuse=FALSE

[DEM]
doComputeDEM=TRUE
meshFileName="fullPathMeshDirName\mesh.bin"
outDir="fullPathMeshDirName\"
demW=8000					: The resolution of the 16-bit gray level DEM.png and DEM_ortoPhoto.tiff images.
demH=8000

[orthomosaic]
doComputeOrthomosaic=TRUE
meshFileName="fullPathMeshDirName\mesh.bin"
meshPtsCamsFileName="fullPathMeshDirName\meshPtsCamsFromDGC.bin"
outDir="fullPathMeshDirName\"

#This will generate DEM and ortoPhoto from the mesh. The fullPathMeshDirName is the directory where the mesh is located.
#It can be fullPathDirName\_OUT\ or fullPathDirName\_OUT_LARGE_SCALE\ or fullPathDirName\_OUT_LARGE_SCALE\PART00000\ or any other directory where the input mesh is located.
#The resulting DEM and ortoPhoto will be in the directory DEM:outDir (DEM:outDir and orthomosaic:outDir should be the same directory!)


#EOF


