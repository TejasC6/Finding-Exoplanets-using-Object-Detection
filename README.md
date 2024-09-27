# Finding Exoplanets using Object Detection
# Project by VS Navneet Kanna, Aasees Kaur and Tejas C
## Guidance of Dr SR Mani Sekhar

# Publication:
## S. R. Mani Sekhar, C. Tejas, V. S. Navneet Kanna and Aasees Kaur. “Finding exoplanets using object detection.” Springer, Astrophysics and Space Science, 368, 75 (2023)
## [Link to Research Paper](https://link.springer.com/article/10.1007/s10509-023-04232-z)


## DATASET 
The dataset used in this project contains images generated from the data available free and open source at https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=PS&constraint=default_flag=1&constraint=disc_facility+like+%27%25TESS%25%27. 

Select all and copy the TIC IDs of all the confirmed planets detected by TESS and paste them into a .txt file. From the folder containing this .txt file, open up jupyter notebook and run [Extract Lightcurves from TIC_IDs.ipynb](https://github.com/TejasC6/Finding-Exoplanets-using-Object-Detection/blob/main/Extract%20Lightcurves%20from%20TIC_IDs.ipynb). This will generate and save lightcurves of all the confirmed planet detected by TESS as .png files into the **images** folder. Filter out lightcurves that do not show a clear dip in brightness. Finally obtaining 233 lightcurves' .png files. 

## ANNOTATIONS 
Using python shell terminal or anaconda navigator, install LabelImg using the command **'pip install labelImg'**. Run LabelImg from the images folder. The LabelImg interface pops up. Here, precise bounding boxes are drawn around dips in brightness observed in the light curves. Create a folder **annotations** and save all the annotation XML files. 

## YOLO Algorithm
Upload the **images** and **annotations** folder to your Google Drive. Open a Google Colab notebook. Follow the code in [YOLOv5.pynb](https://github.com/TejasC6/Finding-Exoplanets-using-Object-Detection/blob/main/YOLOv5.ipynb)


### Converting .png files to .jpg files
Some of the other object detection models like the ones included in this project require the lightcurve images to be in .jpg format instead of .png. In the folder containing the images, run [To convert files to jpg.ipynb](https://github.com/TejasC6/Finding-Exoplanets-using-Object-Detection/blob/main/To%20convert%20files%20to%20jpg.ipynb)
### Making changes in XML files 
It is required to make changes in XML files whenever there is a change in the directory containing the required image data, while uploading to Drive or simply to make any changes in the XML files run [To change path in XML files.ipynb](https://github.com/TejasC6/Finding-Exoplanets-using-Object-Detection/blob/main/To%20change%20path%20in%20XML%20files.ipynb)

## Comparison with other Object Detection Models
### SSD MobileNet v2
To compare the results obtained from the YOLO algorithm, use any of the many Object Detection models available in [Tensorflow 2 Objection Detection API](https://github.com/tensorflow/models/tree/master/research/object_detection/models). In this project, we use the SSD MobileNet v2 but you can easily switch between any of the other models available. Follow the [SSD_MobileNetv2.ipynb](https://github.com/TejasC6/Finding-Exoplanets-using-Object-Detection/blob/main/SSD_MobileNetv2.ipynb)
### EfficientDet Lite Model architectures
To run this project on mobile phones, Raspberry Pi and other microcomputers that have less computation power, make use of the TensorFlow Lite Model Maker and compare the different architectures included in EfficientDet Lite, a family of state-of-the-art model architectures that are built specifically to run machine learning models on edge devices. Follow [EfficientDet_Lite_Models.ipynb](https://github.com/TejasC6/Finding-Exoplanets-using-Object-Detection/blob/main/EfficientDet_Lite_Models.ipynb). Experiment with this colab notebook by changing number of epochs and switching between versions of EfficientDet Lite. 

 References: 
 
 [Techzizou](https://techzizou.com/training-an-ssd-model-for-a-custom-object-using-tensorflow-2-x/)
 
 [NS Tiwari](https://techzizou.com/training-an-ssd-model-for-a-custom-object-using-tensorflow-2-x/)
