# Automated Uncertain Seismic Unconformities Mapping  

*Part of Subsurface Hackathon 2018 in Salt Lake City*
  
## Motivation  
* Manual interpretation is time-consuming  
* Auto-tracking is far from perfect and still requires human QC  
* The problem of improving our unconformity mapping is widespread for geologists and geophysicists in exploration.  
  
## Background  
Unconformity is the maximum flooding surface between discontinuous beds in the subsurface. Understanding unconformities locally, regionally, and globally is the basis of sequence stratigraphy. Importance of understanding unconformity include:  
1)	hydrocarbon migration indicators (if the unconformity is permeable)  
2)	reservoir trap (if beds overlying the eroded surface are impermeable)  
Popular unconformities include Base Cretaceous Unconformity. Popular reservoirs with permeable unconformity pathways include Permian. Excellent unconformity traps include the Prudhoe Bay oil field and flanks of Central Kansas and Nemaha uplifts, such as the Mississippian limestone of the Central Kansas uplift beneath the Pennsylvanian/Mississippian unconformity.  
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
  
## Step 1: Training Data  
Mini Goal: Create Image Pairs of data and model.  
1.	Create a bulk of seismic images and generate the paired binary model of the unconformity line. However, due to sparsity of the data this may not be possible.  
2.	Use a velocity model (derived from existing earth model) and assign velocity constraints on beds above and below unconformity to create binary model for the paired image.  
  
How can we create training data? Synthetic Seismic Data and Real Seismic Data  
How do you make labels from the data?  
How do you make the tile model? Binarisation?  
How can we increase of training data set? Minor rotate of XX degrees.  
  
## Step 2: GAN for image-to-image translation  
We can use image  

## Resources  
[Earth Model Data](https://github.com/gganssle/cseg-imXlate/tree/master/dat)  
[Gempy](https://github.com/cgre-aachen/gempy)   
[Pynoddy](https://github.com/flohorovicic/pynoddy)   
[CycleGAN repo](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)  
[Paper for CycleGAN](https://arxiv.org/abs/1703.10593)  
    
##  Thanks  
Evan, Gram and Diego from Agile
Steve Purves
  
## Terminology
**Unconformity**: A discontinuity in sediment deposition shown as buried erosional surface separating 2 rock masses or strata of different ages. or Geologic surface separating older from younger rocks and representing a gap in the geologic record.  
**GAN**: Part of convolutional neural network, a class of unsupervised learning, implemented by a competing dual-neural-network system.  
