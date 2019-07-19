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
texSide=8190
scale=1

[simplify]
doSimplify=TRUE
meshFileName="fullPathMeshDirName\mesh.bin"
meshPtsCamsFileName="fullPathMeshDirName\meshPtsCamsFromDGC.bin"
simplifiedMeshFolderName="fullPathMeshDirName\simplified\"		: resulting simplified mesh will be located in this directory
maxNTriangles=10000							: number of triangles in simplified mesh

#This will generate simplified mesh (user can choose number of triangles in simplified mesh). The fullPathMeshDirName is the directory where the mesh is located. 
#It can be fullPathDirName\_OUT\ or fullPathDirName\_OUT_LARGE_SCALE\ or fullPathDirName\_OUT_LARGE_SCALE\PART00000\ or any other directory where the input mesh is located.
#The resulting simplified mesh will be located in directory simplify:simplifiedMeshFolderName
#It wil produce the textured mesh as well




#EOF


