![](https://github.com/didiooi/UnconformityDetection/blob/master/misc/frontpage2.png)
# The Unconformist  
### *(Automating Uncertainty: Seismic Unconformity Mapping)*  
(Status: WIP)  
Collaborators: Didi Ooi (Uni of Bristol), Karin Eres Maria (Shell), Zoe Zhang (Chevron), Alana Finlayson (UK Oil and Gas Authority)  

...*Part of [Agile*](https://agilescientific.com) Subsurface Hackathon 2018 in Salt Lake City*  

In just one and a half day, our team built a POC deep neural network architecture to predict unconformity on earth model.  
  
## Motivation  
* Manual interpretation is time-consuming  
* Auto-tracking is far from perfect and still requires human QC  
* The problem of improving our unconformity mapping is widespread for geologists and geophysicists in exploration.  
  
## Background  
Unconformity is the contact between discontinuous beds in the subsurface. It represents a break in the geologic record. Understanding unconformities locally, regionally, and globally is the basis of sequence stratigraphy. Importance of understanding unconformity include:  
* Hydrocarbon migration indicators (if the unconformity is permeable)  
* Reservoir trap (if beds overlying the eroded surface are impermeable)  

Can we utilize AI to help identify and map key unconformities in earth models? And potentially in seismic?  
  
## Big Idea / Overarching Goal  
Using Deep Learning to automate mapping of unconformities to improve reconstruction of geologic evolution of rock record.  
This improves including the small-scale mapping of unconformities and using deep learning to validate the auto-tracker.  
  
## Workflow  
1.	Create adequate training images    
2.	Train a deep learning model using Generative Adversarial Network    
  
Generate Training Data -> Deep Learning with GAN -> Model  
Dataset:    
-	Existing Seismic Data or Velocity Data  
-	Earth Model  
  
## Step 1: Training Data (Input) Preparation  
Goal: Generate enough data and transform it to be ready as input files into training model.  
Create Automated Labeling, Tile Maker, Image Pairs of data and model, CycleGAN model.  

1. Initial goal was to create a bulk of interpreted seismic data and generate the paired binary model of the unconformity line. However, due to the sparsity of the data (ratio of unconformity vs whole seismic) this may not be possible.  
2.	Generate synthetic data: Use a velocity model (derived from existing earth model) and assign velocity constraints on beds above and below unconformity to create binary model for the paired image.  
  
...How can we create training data? Synthetic Seismic Data and Real Seismic Data  
...How do you make labels from the data?  
...How do you make the tile model? Binarisation?  
...How can we increase of training data set? Minor rotate of XX degrees.  

![](https://github.com/didiooi/UnconformityDetection/blob/master/misc/Picture1.png)  
Created Tile Maker and used [LabelMe](https://github.com/wkentaro/labelme)

## Step 2: Model Training Deep Learning
Goal: Train image-to-image translation with as many data as possible and predict.  
Current Training Data: 600 earth models derived from 
Algorithm: CycleGAN, Pix to Pix
Tools: Tensorflow, AWS

  
## Step 3: GAN as prediction  
Current prediction on (only) 5 blind test data at the last hour of the hackathon: 80% accuracy 

Tried to use GAN model to predict seismic data that it has never seen before and it could already guess where the unconformity ISN'T.
![](https://github.com/didiooi/UnconformityDetection/blob/master/misc/cycleGAN.PNG)

## Step 4: UI
Mock-up of [UI for Deep Learning Application on Seismic](https://share.proto.io/9PV78C/)
![](https://github.com/didiooi/UnconformityDetection/blob/master/misc/Mock-up%20of%20data%20vis.JPG)

## Judges Q&A
Ways to reduce uncertainty:  
1. Increase training dataset to 10,000 to 20,000 using synthetic data  
2. Every ML algorithm has an output which is a probability  
3. This is a tool to provide second unbiased opinion from the algorithm to assist interpreter.   

## Future and Other Potential Applications
Channel detection in Deepwater Turbidite systems  
Integrate logs to train seismic images

## Resources
[**Presentation Slide**](https://docs.google.com/presentation/d/1vwxIKiREnsplgJSapd_Hqvakvf5Alu5WpRnMS_sSUIw/edit#slide=id.g3ab9f14b8d_0_0)  
  
![](https://github.com/didiooi/UnconformityDetection/blob/master/misc/Logo.png)  

### References
[Earth Model Data](https://github.com/gganssle/cseg-imXlate/tree/master/dat)  
[Gempy](https://github.com/cgre-aachen/gempy)   
[Pynoddy](https://github.com/flohorovicic/pynoddy)   
[CycleGAN repo](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)  
[Paper for CycleGAN](https://arxiv.org/abs/1703.10593)  
    
##  Thanks  
Evan and Diego from [Agile*](https://agilescientific.com)  
Gram Ganssle  
Steve Purves  
  
## Terminology
**Unconformity**: A discontinuity in sediment deposition shown as buried erosional surface separating 2 rock masses or strata of different ages. or Geologic surface separating older from younger rocks and representing a gap in the geologic record.  
...(*Popular unconformities include Base Cretaceous Unconformity. Popular reservoirs with permeable unconformity pathways include Permian. Excellent unconformity traps include the Prudhoe Bay oil field and flanks of Central Kansas and Nemaha uplifts, such as the Mississippian limestone of the Central Kansas uplift beneath the Pennsylvanian/Mississippian unconformity.*)  
**GAN**: Part of convolutional neural network, a class of unsupervised learning, implemented by a competing dual-neural-network system.  
