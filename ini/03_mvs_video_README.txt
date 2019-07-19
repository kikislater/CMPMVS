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

[generateVideoFrames]
doGenerateVideoFrames=TRUE
meshFileName="fullPathMeshDirName\mesh.bin"
meshWrlFileName="fullPathMeshDirName\meshAvImgTex.wrl"
meTextureCorrdsFileName="fullPathMeshDirName\meshAvImgTex.bin"
nintermed=20								: The number of frames between two camera positions in automatically generated flyover-camera-positions video. We recommend to set this value to 10 or 5 for large datasets in order to speedup the computation time.
width=1280
height=720
stereoCamsPixSizeDist=20.0


#This will generate flyover video from the mesh. The fullPathMeshDirName is the directory where the mesh is located. 
#It can be fullPathDirName\_OUT\ or fullPathDirName\_OUT_LARGE_SCALE\ or fullPathDirName\_OUT_LARGE_SCALE\PART00000\ or any other directory where the input mesh is located.
#The resulting video will be in directory fullPathDirName\workDirName\video\


#EOF


