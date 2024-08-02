# **DRIVER BEHAVIOUR DETECION USING CNN**
 
![image](https://github.com/user-attachments/assets/b188a764-6884-49cd-a347-d85947672f30)![image](https://github.com/user-attachments/assets/b188a764-6884-49cd-a347-d85947672f30)


## **BUSINESS CASE**:

   The target of this project is to use a number of CNN structures to claasiy images for each class , then we use the best structure for prediction.This project is Image classification.
   
## **TASK:MULTICLASS CLASSIFICATION**


## **ABOUT DATASET**:

   The dataset contains diffrenet images of drivers behaviours consist of 5 classes which are from 2 different image formats(jpg , png) .
### **CLASSES**

**As I mentioned  before , the whole the folder contains of 5 classes which are :**
   
   

1: Other_activities : The driver is doing something except the other 4 classes which we have , this folder has 2128 images.

2: Safe_driving     : The driver is driving safely,this folder has 2203 images in itself.

3: Talking Phone    : The driver is talking on the phone , this folder has 2169 images.

4: Texting Phone    : The driver is texting on the phone , this folder has 2203 images.

5: Turning          : The driver is turning back doing something , there are 2063 images in this folder.

 ### **PROBLEM**


 This image folder contains a number of flawed images which must detect them and remove them from the list of images , that I will find them and show the address of each one and then remove them.
   


**Brief Explanation :**

 * In summary , we are going through this folder of images and load images and put them in different lists for each class , we define how many images are 
 * jps format and , how many images are png format , then I show the flawed images    , which must be deleted, next I illustrate 6 images for each 5 classes for**
 * having better understanding,after that i split images into Train , Test and Validation , consequently , I put each one in a dataset and then concat them 
 * then use ImageDataGenerator to prepare the images for out models , then use models and then shows each models in details(layers and structures) 
 * and in the end compare all models and then use the best one for prediction.


## **DEVICE PROJECT INTO MULTIPLE STEPS**
* Importing Libraries
* Loading Dataset
* JPG & PNG Format
* Flawed Images Cleaning
* Images Illustration
*  Training, Validation and Testing set
* Image Preprocessing
* Used ResNet50,VGG16, InceptionV3 and Xception pre-trained model
* Model Compilation
* Model Training
* Model Evaluation
* Model Saving
* Prediction on Xception model
*  Models Comparison


##  **Importing libraries**
* NUMPY
* PANDAS
* MATPLOT
* KERAS
* TENSORFLOW
  
  ## **Dataset Loading**

**Description:**

* There are directory which is the address of file , folders which are 5 for each class we have , and we make 5 empty lists with the same name 
* for each class,then we load images for each class with the end of(JPG or PNG) formats with endswitch order then combine the address again for having the same address structure for each class in the lists.Before that lest see the version of Tendoeflow and after that lets see that we are using CPU or GPU.

 **Description :**

 * Now , it is better to know exactly how many images we have for each class and how many images for each class are JPG or PNG format To do this , we creat a function to show it , by split() fuction and then a simple comparison we are able to detect them and put them in a seperated list.

   ## **JPG & PNG Formats**
**Description :**

* We can see that the number of images with PNG format is much less then JPG format.This issue is the same for all classes**

  **The folder name is : other activities**

* The number of all images : 2128

* The number of images with jpg format is : 2068

* The number of images with png format is : 60

  **The folder name is : safe_driving**

* The number of all images : 2203

* The number of images with jpg format is : 2179

* The number of images with png format is : 24

**The folder name is : talking_phone**

* The number of all images : 2169

* The number of images with jpg format is : 2145

* The number of images with png format is : 24
  
**The folder name is : turning**

* The number of all images : 2063

* The number of images with jpg format is : 2002

* The number of images with png format is : 61

  ## **Flawed Images Cleaning**
  
**Description :**

* There are a number of images which have problems and must be deleted . It was really hard to detect these flawed images , the note is that all flawed images are from just two classes ,Other activities(9 flawed images) and turning(6 flawed images),The name of these images are written in a list and then showed the address and next will be removed from the list. In total we have 15 flawed images**

  ## **Images illustration**
![image](https://github.com/user-attachments/assets/e6e60c73-9a72-43d1-b8b7-deeac098cbf4)
![image](https://github.com/user-attachments/assets/34d4dc1b-b8d6-4772-a06c-c599560c43f3)
![image](https://github.com/user-attachments/assets/2a462eb4-3860-4393-9629-e3c124b0ebda)
![image](https://github.com/user-attachments/assets/406cb127-b39e-4af2-b29a-f901aa5157ad)
![image](https://github.com/user-attachments/assets/428f5ed4-6d7e-4e16-b995-8f7fd030a9cc)

  **Description :**

 * Now , for better understanding I creat a function to show 6 images , then we apply it for each class.I also add the size of each image to realize about the height and width of the images*

   ## **Train,Test & Validation**

    **Description:**

  * Here , I create Train , Test and Validation lists for each class , then a fucntion to calculate the size of Train , Test and Validation images based on the number of each class it will be splited.The note is that I put 85% for Train , 10% for Test and 5% for validation which can be changed , but the result on this seperation seems acceptable.Then, I show that how many images are exactly from this division.

 **Name : Other_activities**

* Number of all images : 2119

* Train(85%) : 1801

* Test(10%) :211

* Valid(5%) : 107


**Name : Driving safe**

* Number of all images : 2203

* Train(85%) : 1872

* Test(10%) :220

* Valid(5%) : 111

**Name : Texting on the phone**

* Number of all images : 2203

* Train(85%) : 1872

* Test(10%) :220

* Valid(5%) : 111

  **Name : Turning**

* Number of all images : 2057

* Train(85%) : 1748

* Test(10%) :205

* Valid(5%) : 104
 
**Description :**
 * If we do need to use Flow_From_Dataframe() we have to convert images to dataframes to be able to load the images. To do this we create dataFrames for each Train , Test and validation for all classes and put the label for each class(2 columns we have one for image and the other for label).After doing that the only we need to do is that concat all Trains , Test and Validations together.**
   
 * The shape of Train DataFrame is : (9136, 2)

* The shape of Test DataFrame is : (1072, 2)

* The shape of Valid DataFrame is : (543, 2

**Found 9136 validated image filenames belonging to 5 classes.**

**Found 1072 validated image filenames belonging to 5 classes.**

**Found 543 validated image filenames belonging to 5 classes.**

**Description :**

* I want to create two functions for showing the result of our model (accuracy and loss)

  **Description :**

**Before going through CNN models I just want to indicate that I just define a couple of hyperparameters the same for all 4 models , such as Number of epochs(6) , learning rate(0.001), and the Optimizer(BinaryCrossEntropy)**

# MODELS:

1.**VGG16**

2.**RESNET50**

3.**INCEPTIONV3**

4.**EXCEPTION**

## RESULT:

1.**VGG16**

![image](https://github.com/user-attachments/assets/a09a7f3d-9744-48b7-a128-846c0eda699e)
![image](https://github.com/user-attachments/assets/e9df0263-51c1-47fa-89a4-4f0ff922c86d)

2.**RESNET50**

![image](https://github.com/user-attachments/assets/f879aa78-6014-453f-87d9-773d9ba1d733)
![image](https://github.com/user-attachments/assets/0f85eecf-aff2-46a7-b313-71f0da713254)

3.**INCEPTIONV3**

![image](https://github.com/user-attachments/assets/fb934e17-4cbb-4d25-bba7-3d1eff15c2f9)
![image](https://github.com/user-attachments/assets/be37b665-b6e9-4016-abf7-6595125b5723)

4.**XCEPTION**

![image](https://github.com/user-attachments/assets/a4ccb6e4-9d11-4090-8f08-5f7938b17a4a)
![image](https://github.com/user-attachments/assets/41d9648a-e4dd-4234-a05b-8adab0f383cd)

## Models Comparison

**Description :**

**We have totally discussed about all models , but let's see all 4 models together ,for Train-acc , Val-acc , Train-loss and Val-loss.The thing which is obvious that in just 6 epochs , Inceptionv3 and Xception seem reliable and great in all comparision , also VGG shows logical behaviour based on its structure but ResnEt completely overfited... In conclusion , Xception model with 99% accuracy on the Test data would be the best for this task amongs these models.**

![image](https://github.com/user-attachments/assets/0d9bf1bb-94e0-49d0-8743-b3d6568fdc59)

![image](https://github.com/user-attachments/assets/5ee70148-4377-4495-9dab-7a4e85a4f081)

![image](https://github.com/user-attachments/assets/04fffd7c-496f-4462-a1bb-afa66e12a615)

![image](https://github.com/user-attachments/assets/b9390991-ad24-4a73-b05f-a1b740181cde)


## **Xception Model Prediction**

![image](https://github.com/user-attachments/assets/64749166-4dea-4928-a0bd-5906362b3d73)

## MODEL ACCURACY PLOTS:

![image](https://github.com/user-attachments/assets/292917bf-c17f-4ce2-be59-f25adcb68956)












