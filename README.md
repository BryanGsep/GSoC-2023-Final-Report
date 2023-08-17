# ML Training-Assistant Final Report
by Do Tien Dung, September, 2023

## Project overview and objective
The utilization of machine learning models, encompassing both segmentation and classification models, within caMicroscope, has been somewhat sporadic thus far. These models have not been seamlessly integrated with the core annotation functions of caMicroscope, namely manual annotation and preset labeling. To address this, the Machine Learning Training Assistant seeks to harmonize these models with the primary annotation functions. This integration aims to enhance user experience, diminish time requirements, enhance precision, and facilitate effortless editing during the annotation process within caMicroscope.

The project entails the implementation of two key functionalities within caMicroscope: ```Annotation Edit``` and ```Annotation Assistant.``` The ```Annotation Assistant``` function is designed to automatically refine user annotations, enabling swifter and more accurate annotation. Subsequent to annotating with the aid of the "Annotation Assistant," users have the flexibility to fine-tune these annotations according to their preferences through the "Annotation Edit" feature.

## Code
<a href="https://github.com/camicroscope/caMicroscope/pull/643">Project Pull Request</a>

## Implemented Functions

### 1.Annotation Assistant
The objective of this function is to seamlessly incorporate a machine learning model aimed at enhancing the functionality of caMicroscope's preset label and annotation subtools. Upon receipt of user-provided annotation details, the model will be activated, subsequently delivering the segmented image. This image will then undergo processing to generate annotations of the utmost quality. The efficacy of the assistant annotation is significantly influenced by the user-imported model. Nonetheless, the assistant annotation feature also encompasses default choices, thereby users would be able to acquire improved annotations even in the absence of an available model.

#### 1.1 Idea
The data from user manual annotations will be employed to identify the Region of Interest (ROI). This ROI picture is subsequently utilized as the starting image for the user input model, also known as the segmentation model. The segmented image produced by the model is then combined with the user's manual annotations. Together, they are used to predict the most suitable final annotations or annotations that best fit the situation.

#### 1.2 Algorithm
<div align="center" style="display: flex; flex-direction: column; align-items: center; text-align: center;">
  <img width="733" alt="Screenshot 2023-08-17 at 17 40 36" src="https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/179cabb3-0bde-4796-878e-b7817dd70ce5">

  <p><i> Figure 1: Annotation Assistant Algorithm flow</i></p>
</div>

#### 1.3 UI
<div align="center" style="display: flex; flex-direction: column; align-items: center; text-align: center;">
  <img width="653" alt="Screenshot 2023-08-17 at 18 18 43" src="https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/a3200c4f-078e-4980-9e10-e49ba0cb6832">

  <p><i> Figure 2: Annotation Assistant Panel</i></p>
</div>

### 2 Annotation Edit
The annotation outcomes from the annotation assistant may not always align precisely with the user's preferences. Consequently, following the annotation creation process, users have the option to refine the annotations through the Layer Management subtools.

#### 2.1 Idea
Upon selecting the annotation that requires editing, the corresponding edit points will become visible. Users can adjust the positions of these points by dragging them to new locations. Furthermore, the ability to delete a point or introduce a new one is conveniently accessible through a simple right-click action.

#### 2.2 UI

<div align="center" style="display: flex; flex-direction: column; align-items: center; text-align: center;">
  <img width="198" alt="Screenshot 2023-08-17 at 19 52 56" src="https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/6fde114f-ca41-4fe3-b5fd-fdbc071ec20b">
  <p><i> Figure 3: Polygon Annotation Edit</i></p>
</div>

<div align="center" style="display: flex; flex-direction: column; align-items: center; text-align: center;">
  <img width="197" alt="Screenshot 2023-08-17 at 19 52 04" src="https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/f475aa12-10d6-44cc-9526-aa908beb67ce">
  <p><i> Figure 4: Brush Annotation Edit</i></p>
</div>

## Usage Example
Below are usage example of 
### Annotation Assistant

#### Polygon Annotate One
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/db93c5f3-3c1b-44a9-a8fd-336b4e65ef56


#### Polygon Annotate Many
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/a2ac4051-0dfc-4de5-89ba-cbb80b9dd1a3



#### Brush Annotate One
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/809a9efc-2939-4535-bb73-5b40d403324b


#### Brush Annotate Many
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/8bac133d-784e-4f21-a850-ba34d14007ae


### Annotation Edit

#### Polygon Edit Point
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/1727734d-53cf-4e65-8c1a-2ac070c6afbb


#### Polygon Add and Delete Point
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/eb9512bf-32fb-4065-86b6-2b5812d9d5c1

#### Brush Edit Point
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/79407eb0-e86d-4083-8739-bf731652b46c


#### Brush Add and Delete Point
https://github.com/BryanGsep/ML-Training-Assistant-Final-Report/assets/77573775/255716d9-22c0-4ead-933b-79919048f296

## GSoC 2023 strace
<a href="https://github.com/BryanGsep/GSoC_2023_caMicroscope_Report">Weekly Report</a>

