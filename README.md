# e4040-2020Fall-project
Seed repo for projects for e4040-2020Fall-project
  - distributed as Github Repo and shared via Github Classroom
  - contains only README.md file
  - Students must have at least one main Jupyter Notebook, and a number of python files in a number of directories and subdirectories such as utils or similar, as demonstrated in the assignments
  - The organization of the directories has to be meaningful

# Detailed instructions how to submit this assignment/homework/project:
1. The assignment will be distributed as a github classroom assignment - as a special repository accessed through a link
2. A students copy of the assignment gets created automatically with a special name - students have to rename the repo per instructions below
3. The solution(s) to the assignment have to be submitted inside that repository as a set of "solved" Jupyter Notebooks, and several modified python files which reside in directories/subdirectories
4. Three files/screenshots need to be uploaded into the directory "figures" which prove that the assignment has been done in the cloud

## (Re)naming of a project repository shared by multiple students (TODO students)
INSTRUCTIONS for naming the students' solution repository for assignments with more students, such as the final project. Students need to use a 4-letter groupID): 
* Template: e4040-2020Fall-Project-GroupID-UNI1-UNI2-UNI3. -> Example: e4040-2020Fall-Project-MEME-zz9999-aa9999-aa0000.

# Organization of this directory
To be populated by students, as shown in previous assignments


# Project Details

## Files
We only have one Jupiter notebook named 'RAN_model_submission.ipynb'. We used CIFAR10 dataset, which could be loaded using API. Thus, you could directly run the notebook from the start to the end.

## Functions
There are totally 5 functions

> conv_unit
> - Parameters: x, filters, kernel_size, weight_decay, strides
> - It is a function containing  one Conv2D layer and BatchNormalization layer, using for residual unit.

> residual_unit
> - Parameters: x, filters, kernel_size, weight_decay
> - It consists of two branches. We designed this block according to the ResNet, but different with the original paper, we only used one combination [CONV, BN, RELU] instead of three.

> attention_module
> - It consists of two branches: Trunk Branch and Soft Mask Branch. Trunk Branch is quite simple. It contains only 2 residual units. While the Soft Mask Branch is much more complex. It includes process of down-sampling and up-sampling, in our implementation, they are coded as ‘MaxPooling2D’ and ‘UpSampling2D’. We set the parameters same as the paper, that is, {𝑝 = 1,𝑡 = 2, 𝑟 = 1}.

The whole Residual Attention model consists of Conv, MaxPooling, Dense layers, 6 Residual Units (UR) and 3 Attention Modules (AM). The ordinary layers are stacked similar with other classic neural network models, while URs and AMs blocks are stacked alternatively.

> lr_scheduler
> - Parameters: epoch
> - It controls the learning rate according to the current epoch.

> plot_history
> - Parameters: history
> - It used for plotting the training and validation loss and accuracy.
