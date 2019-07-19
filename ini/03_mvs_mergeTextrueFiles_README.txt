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

[groupToOneTextureFile]
doGroupToOneTextureFile=TRUE
meshDir="fullPathMeshDirName\"			: input mesh directory
outDir="fullPathMeshDirName\ONETEXTURE\"	: output mesh directory
newTextureSide=8192				: The resolution of texture file. Must be a power of 2.

#This will regenerate mesh it into new mesh with one texture file. The fullPathMeshDirName is the directory where the mesh is located. 
#It can be fullPathDirName\_OUT\ or fullPathDirName\_OUT_LARGE_SCALE\ or fullPathDirName\_OUT_LARGE_SCALE\PART00000\ or any other directory where the input mesh is located.
#The resulting video will be in directory groupToOneTextureFile:outDir



#EOF


