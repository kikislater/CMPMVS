[global]
dirName="fullPathDirName\"				: The full path to the directory containing data (the '\' is needed!)
prefix=""						: Prefix of the images names (default four digits number).
imgExt="XXX"						: Extension of the images.
ncams=XX						: Number of the images.
width=XXXX						: Width of the images.
height=XXXX						: Weight of the images.
scale=1							: The input images (and P matrices) in in the dirName are downscaled scale-times and saved to the workDirName. The pipeline further works with downscaled images and corresponding P-matrices. It is usefull when you have huge images in order to speed-up the computation. We usually use scale=2 for large images calibrated by VisualSFM, then our pipleine (due to several reasons) gives slightly better results.
workDirName="_tmp"					: The directory name that will contain application 

[uvatlas]
texSide=4096						: The resolution of texture file. Must be a power of 2.
scale=1							: The downscale factor of the texture file. (For large datasets we recommend to set texSide=8192 and scale=2 (or 4) in order to obtain smaller number of texture files.)

[delanuaycut]
saveMeshTextured=TRUE					: Set this to FALSE if do not want to have textured mesh of (each part) on the output. You can texture it later using mvs_retexture.ini. The colored mesh will be computed anyway!

[hallucinationsFiltering]
useSkyPrior=FALSE					: Set this to TRUE if you have just street-view images (i.e. city-like dataset) (first camera must be landscape oriented i.e. first camera y-axis must be almost equal to a gravity vector!) in order to filter out hallucinations from the sky area. We recomend to first reconstruct the dataset (constisting of street-view images only!!!) using useSkyPrior=FALSE and if you are not satisfied with the result (i.e. there are a lot of hallucinations in the sky area) then we recomentd to try to use useSkyPrior=TRUE.
doLeaveLargestFullSegmentOnly=FALSE			: Set this to FALSE if you want to have multiple objects reconstructed. Having this parameter TRUE means that the software will automatically segment the resulting mesh into connected components and put just the largest one into the output.
doRemoveHugeTriangles=TRUE				: This option causes that the appliaction will remove huge triangles. It is recomended to have turned it on!

[largeScale]
doGenerateAndReconstructSpaceMaxPts=TRUE		
doGenerateSpace=TRUE
planMaxPts=3000000					: Maximim number of vertices in the tetrahedralization. Set it to smaller value if you have less than 12GB of ram.
doComputeDEMandOrtoPhoto=FALSE				: Set it to FALSE in order to turn off the DEM and OrtoPhoto computation. 
doGenerateVideoFrames=FALSE				: Set it to FALSE in order to turn off the video.avi and stereo_video.avi computation. The delanuaycut:saveMeshTextured must be TRUE!

[meshEnergyOpt]
doOptimizeOrSmoothMesh=FALSE				: Set it to TRUE if you want to run final mesh refinement step. Note that this is experimental feature. We are still working on it. It is suitable for beta testing. The dafault vaule is FALSE. Let us know your opinion on the result when using TRUE please.


#do not erase empy lines after this comment otherwise it will crash ... bug


