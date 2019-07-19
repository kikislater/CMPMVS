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

[uvatlas]
texSide=8190				: The resolution of texture file. Must be a power of 2.
scale=1					: The downscale factor of the texture file. (For large datasets we recommend to set texSide=8192 and scale=2 (or 4) in order to obtain smaller number of texture files.)

[retexture]
doRetexture=TRUE
meshDir="fullPathMeshDirName\"		: input mesh directory
outDir="fullPathMeshDirName\TEXTURED\"	: output mesh directory
doSaveMeshTextured=TRUE			: set it to TRUE if you want to have textured mesh on the ouput
doSaveMeshColored=TRUE			: set it to TRUE if you want to have colored mesh on the ouput
doRegenerateImages=FALSE		: experimental feature. If is TRUE it should generate less fragmented texture files

#This will generate textured mesh. The fullPathMeshDirName is the directory where the mesh is located. 
#It can be fullPathDirName\_OUT\ or fullPathDirName\_OUT_LARGE_SCALE\ or fullPathDirName\_OUT_LARGE_SCALE\PART00000\ or any other directory where the input mesh is located.
#The resulting textured mesh will be located in directory retexture:outDir


#EOF


