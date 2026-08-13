# AgriNex-Rover-Autonomous-Smart-Farming-
**Dataset Structure:**

The dataset is based on 2000 images. The 2000 image dataset is classified into three groups for the purpose of training, testing and validation. The training, testing and validation sub-groups contain 1250,500 and 250 images respectively. Each image in the dataset consists of a corresponding ground truth image. Numeric values of the labelled coordinates are stored in .mat files.

The filenames in the training and testing splits are ordered sequentially by the data class IDs listed in Table 2. In the Train Dataset, each class contains 25 images, so images 0–24 correspond to Class 1, images 25–49 to Class 2, and so on. In the Test Dataset, each class contains 10 images, so images 0–9 correspond to Class 1, images 10–19 to Class 2, and so on.
.
│
├── Train Dataset              # 1250 images and ground truth segmentations from 50 data classes. [25 Images per class x 50 Classes]
|   └──labels.mat             # .mat file containing image label coordinates for 1250 images
│
├── Test Dataset               # 500 images and ground truth segmentations from 50 data classes. [10 Images per class x 50 Classes]
|    └──Labels                  # .mat file containing image label coordinates for 500 images
│
└── Validation Dataset               # 250 images and ground truth segmentations from CRDLDv1.0 base images.
    └──Labels                  # .mat file containing image label coordinates for 250 images

**    Table 1: Data Categories:**
Table 1 contains the different field variations represented in the dataset.
| ID | Data Category                   | Description                                                           |
| -- | ------------------------------- | --------------------------------------------------------------------- |
| a  | **Unploughed Soil**             | Field condition before ploughing; hard or undisturbed soil surface    |
| b  | **Ploughed Soil**               | Soil after ploughing with visible furrows and prepared seed bed       |
| c  | **Shallow Ploughing**           | Insufficient plough depth requiring correction                        |
| d  | **Deep Ploughing**              | Proper/deep furrow formation suitable for sowing                      |
| e  | **Straight Furrow**             | Uniform furrow aligned with the robot's travel direction              |
| f  | **Curved Furrow**               | Non-straight furrow requiring navigation correction                   |
| g  | **Seed Drop Correct**           | Seed deposited at the target location and spacing                     |
| h  | **Seed Drop Missing**           | Expected seed position has no seed                                    |
| i  | **Seed Overlap**                | Two or more seeds dropped too close together                          |
| j  | **Seed Spacing Error**          | Distance between seeds differs from the target spacing                |
| k  | **Fertilizer Applied**          | Fertilizer successfully dispensed at the target location              |
| l  | **Fertilizer Under-Dispensing** | Less fertilizer than the calibrated quantity is released              |
| m  | **Fertilizer Over-Dispensing**  | More fertilizer than the target quantity is released                  |
| n  | **Fertilizer Blockage**         | Hopper/nozzle is blocked and fertilizer flow stops                    |
| o  | **Empty Hopper**                | Seed or fertilizer container reaches an empty/low level               |
| p  | **Crop Row**                    | Visible crop row used for autonomous navigation                       |
| q  | **Obstacle**                    | Stone, equipment, person, plant mass, or other obstruction            |
| r  | **Uneven Terrain**              | Rough or irregular soil affecting wheel movement                      |
| s  | **Wet Soil**                    | High-moisture field condition affecting traction and operation        |
| t  | **Dry Soil**                    | Low-moisture field condition requiring different operating parameters |


**Table 2: Data Classes Formed by Combinations of Field Variations**
| Data Category               |  a |  b |  c |  d |  e |  f |  g |  h |  i |  j |
| --------------------------- | -: | -: | -: | -: | -: | -: | -: | -: | -: | -: |
| **a. Unploughed Soil**      |  1 |    |    |    |    |    |    |    |    |    |
| **b. Properly Ploughed**    |    |  2 |    |    |    |    |    |    |    |    |
| **c. Shallow Ploughing**    |  3 |    |  4 |    |    |    |    |    |    |    |
| **d. Uneven Ploughing**     |  5 |    |  6 |  7 |    |    |    |    |    |    |
| **e. Correct Seed Spacing** |    |  8 |    |    |  9 |    |    |    |    |    |
| **f. Missing Seed**         |    |    |    |    | 10 | 11 |    |    |    |    |
| **g. Seed Overlap**         |    |    |    |    | 12 |    | 13 |    |    |    |
| **h. Correct Fertilizer**   |    |    |    |    |    |    |    | 14 |    |    |
| **i. Under Fertilizer**     |    |    |    |    |    |    |    | 15 | 16 |    |
| **j. Over Fertilizer**      |    |    |    |    |    |    |    |    |    | 17 |

**Sample Data:**
The crop row is labelled with white lines on black background. The line width of the white line is 6 pixels. The labels could be regenerated with custom line width using the labels .mat files.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/e5feb8d8-2dd1-45e7-bc25-88f804af9b91" />
