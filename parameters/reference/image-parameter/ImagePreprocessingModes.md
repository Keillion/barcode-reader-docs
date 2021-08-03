---
layout: default-layout
title: Dynamsoft Barcode Reader Parameter Reference for ImageParameter Object - ImagePreprocessingModes
description: This page shows Dynamsoft Barcode Reader Parameter Reference for ImageParameter Object - ImagePreprocessingModes.
keywords: ImagePreprocessingModes, ImageParameter, image process control parameters, parameter reference, parameter
needAutoGenerateSidebar: false
---
# ImageParameter Object | ImagePreprocessingModes


## ImagePreprocessingModes  

### Mode Properties
`ImagePreprocessingModes` is a parameter for setting the mode for image preprocessing algorithms. It consisits of one or more `ImagePreprocessingMode` items and each item has its own arguments. The array index represents the priority of the item. The smaller index is, the higher priority is.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *string array* or *[`ImagePreprocessingMode`]({{ site.enumerations }}parameter-mode-enums.html#imagepreprocessingmode) array* | "IPM_SKIP"<br>"IPM_AUTO"<br>"IPM_GENERAL"<br>"IPM_GRAY_EQUALIZE"<br>"IPM_GRAY_SMOOTH"<br>"IPM_SHARPEN_SMOOTH"<br>"IPM_MORPHOLOGY" | ["IPM_GENERAL", "IPM_SKIP", "IPM_SKIP", "IPM_SKIP", "IPM_SKIP", "IPM_SKIP", "IPM_SKIP", "IPM_SKIP"] |

**See Also**    :   
    [`ImagePreprocessingMode` Enumeration]({{ site.enumerations }}parameter-mode-enums.html#imagepreprocessingmode)
    
#### Mode Arguments
- [Sensitivity](#sensitivity)
- [SmoothBlockSizeX](#smoothblocksizex)
- [SmoothBlockSizeY](#smoothblocksizey)
- [SharpenBlockSizeX](#sharpenblocksizex)
- [SharpenBlockSizeY](#sharpenblocksizey)
- [MorphOperation](#morphoperation)
- [MorphShape](#morphshape)
- [MorphOperationKernelSizeX](#morphoperationkernelsizex)
- [MorphOperationKernelSizeY](#morphoperationkernelsizey)
- [LibraryFileName](#libraryfilename)
- [LibraryParameters](#libraryparameters)
 
##### Sensitivity 
Sets the sensitivity used for gray equalization.

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *int* | [1, 9] | 5 |         

**Remarks**         
  If you have an image with a low level of contrast, you can set the property to a larger value. A larger value means a higher possibility that gray equalization will be activated. This may cause adverse effect on images with a high level of contrast.  


##### SmoothBlockSizeX 
Sets the horizontal block size for the smoothing process.

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *int* | [3, 1000] | 3 |         

**Remarks**         
  Block size refers to the size of a pixel neighborhood used to calculate the threshold for the pixel. An appropriate value can help increase the accuracy of barcode localization.


##### SmoothBlockSizeY 
Sets the vertical block size for the smoothing process.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *int* | [3, 1000] | 3 |         

**Remarks**         
  Block size refers to the size of a pixel neighborhood used to calculate the threshold for the pixel. An appropriate value can help increase the accuracy of barcode localization.  
  

##### SharpenBlockSizeX 
Sets the horizontal block size for the sharpening process.

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *int* | [3, 1000] | 3 |         

**Remarks**         
  Block size refers to the size of a pixel neighborhood used to calculate the threshold for the pixel. An appropriate value can help increase the accuracy of barcode localization.


##### SharpenBlockSizeY 
Sets the vertical block size for the sharpening process.

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *int* | [3, 1000] | 3 |         

**Remarks**         
  Block size refers to the size of a pixel neighborhood used to calculate the threshold for the pixel. An appropriate value can help increase the accuracy of barcode localization.
  


##### MorphOperation 
Sets the morph operation for the morphology process. 

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *string* | "Erode"<br>"Dilate"<br>"Open"<br>"Close" | "Close" |         

**Remarks**        
   - "Erode": Perform erosion process.
   - "Dilate": Perform dilation process.
   - "Open": Perform erosion first, then perform dilation.
   - "Close": Perform dilation first, then perform erosion.
   
   For more information, please check out [Image Processing in OpenCV - Morphological Transformations](https://docs.opencv.org/master/d9/d61/tutorial_py_morphological_ops.html) for reference.


##### MorphShape  
 Sets the morph shape for the morphology process.  

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *string* | "Rectangle"<br>"Cross"<br>"Ellipse" | "Rectangle" |         

**Remarks**        
   - "Rectangle": 
   - "Cross": 
   - "Ellipse": 



##### MorphOperationKernelSizeX  
Sets the horizontal kernel size for the morphology process. 

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *int* | [0, 1000]  | 0 |         



##### MorphOperationKernelSizeY  
 Sets the vertical kernel size for the morphology process.  

| Value Type | Value Range | Default Value | 
| ---------- | ----------- | ------------- |
| *int* | [0, 1000]  | 0 |       


##### LibraryFileName 
Sets the file name of the library to load dynamically.

| Value Type | Value Range | Default Value | Valid For | 
| ---------- | ----------- | ------------- | ----------- |
| *string* | A string value representing file name. | "" | All `ImagePreprocessingMode` items except IPM_SKIP and IPM_AUTO |         


**Remarks**         
  The library must be in the same place with Dynamsoft Barcode Reader Library.


##### LibraryParameters 
Sets the parameters passed to the library to load dynamically.

| Value Type | Value Range | Default Value | Valid For | 
| ---------- | ----------- | ------------- | ----------- |
| *string* | A string value representing parameters. | "" | All `ImagePreprocessingMode` items except IPM_SKIP and IPM_AUTO |         


### Setting Methods

#### As JSON Parameter
`ImagePreprocessingModes` as a JSON parameter is a JSON Object array. Each JSON Object has several keys for setting the mode and the value of arguments. The array index decides the priority the mode for image preprocessing algorithms.
Default values will be used if there is no manual setting.   


| Json Object |	Json Parameter Name | Value Type |
| ----------- | ------------------- | ---------- |
| ImageParameter | ImagePreprocessingModes | *JSON Object Array* | 

**Json Parameter Example**   
```
{
    "ImagePreprocessingModes": [
        {
            "Mode": "IPM_GRAY_EQUALIZE",
            "Sensitivity": 5
        },
        {
            "Mode": "IPM_SHARPEN_SMOOTH",
            "SmoothBlockSizeX": 5,
            "SmoothBlockSizeY": 5,
            "SharpenBlockSizeX": 5,
            "SharpenBlockSizeY": 5
        }
    ]
}
```


&nbsp;



#### As `PublicRuntimeSettings` Member
`ImagePreprocessingModes` is a [`ImagePreprocessingMode`]({{ site.enumerations }}parameter-mode-enums.html#imagepreprocessingmode) array defines in `furtherModes` which is a struct member of `PublicRuntimeSettings`. It is used for setting the modes and the priority for image preprocessing algorithms. Default value will be used if there is no manual setting.

| Struct |	Struct Member Name | Value Type |
| ------ | ------------------ | ---------- |
| [`PublicRuntimeSettings`]({{ site.structs }}PublicRuntimeSettings.html)->[`furtherModes`]({{ site.structs }}PublicRuntimeSettings.html#furthermodes) | [`imagePreprocessingModes`]({{ site.structs }}FurtherModes.html#imagepreprocessingmodes) | [`ImagePreprocessingMode`]({{ site.enumerations }}parameter-mode-enums.html#imagepreprocessingmode)[8] |


**Remarks**     
[`GetModeArgument`]({{ site.cpp_methods }}parameter-and-runtime-settings-basic.html#getmodeargument) and [`SetModeArgument`]({{ site.cpp_methods }}parameter-and-runtime-settings-basic.html#setmodeargument) need to be called for getting or setting the value of [arguments](#mode-arguments).


**See Also**      
- [`PublicRuntimeSettings` Struct]({{ site.structs }}PublicRuntimeSettings.html)
- [`FurtherModes` Struct]({{ site.structs }}FurtherModes.html)
- [`ImagePreprocessingMode` Enumeration]({{ site.enumerations }}parameter-mode-enums.html#imagepreprocessingmode)
