![](https://github.com/didiooi/UnconformityDetection/blob/master/misc/frontpage2.png)
# The Unconformist  
### *(Automating Uncertainty: Seismic Unconformity Mapping)*  

Collaborators: Didi Ooi, Karin Maria (Shell), Zoe Zhang (Chevron), Alana Finlayson (Oil and Gas Authority)

...*Part of [Agile*](https://agilescientific.com) Subsurface Hackathon 2018 in Salt Lake City*

  
## Motivation  
* Manual interpretation is time-consuming  
* Auto-tracking is far from perfect and still requires human QC  
* The problem of improving our unconformity mapping is widespread for geologists and geophysicists in exploration.  
  
## Background  
Unconformity is the maximum flooding surface between discontinuous beds in the subsurface. Understanding unconformities locally, regionally, and globally is the basis of sequence stratigraphy. Importance of understanding unconformity include:  
* Hydrocarbon migration indicators (if the unconformity is permeable)  
* Reservoir trap (if beds overlying the eroded surface are impermeable)  

Can we utilize AI to help identify and map key unconformities in earth models? In Seismic?  
  
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

1. Create a bulk of seismic images and generate the paired binary model of the unconformity line. However, due to sparsity of the data this may not be possible.  
2.	Use a velocity model (derived from existing earth model) and assign velocity constraints on beds above and below unconformity to create binary model for the paired image.  
  
...How can we create training data? Synthetic Seismic Data and Real Seismic Data  
...How do you make labels from the data?  
...How do you make the tile model? Binarisation?  
...How can we increase of training data set? Minor rotate of XX degrees.  

## Step 2: Model Training Deep Learning
Goal: Train image-to-image translation with as many data as possible and predict.  
Current Training Data: 600 earth models derived from 
Algorithm: CycleGAN
Software: Tensorflow

  
## Step 3: Using GAN to predict  
Current prediction on 5 blind test data: 80% accuracy 

## Step 4: UI
Mock-up of [UI for Deep Learning Application on Seismic](https://share.proto.io/9PV78C/)
1[](https://github.com/didiooi/UnconformityDetection/blob/master/misc/Mock-up%20of%20data%20vis.JPG)

## Other Applications
Channel detection in Deepwater Turbidite systems 

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
