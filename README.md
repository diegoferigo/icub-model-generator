# icub-model-generator

Resources and programs to generate models (URDF,SDF) of the iCub robot.

**Note: this repository is meant to streamline the process of producing iCub URDF/SDF models by iCub mantainers. It is not meant to be used directly by users of iCub. For offical info on the kinematic parameters of the iCub, please see [the documentation in iCub's wiki](http://wiki.icub.org/wiki/ICubForwardKinematics).**

Currently, it is possible to generate iCub models by means of two different pipelines. 

1) The generation is achieved by using Denavit Hartenberg parametsrs based on robot-model hardcoded data in the iKin/iDyn source code, and meshes postprocessed by ISIR at UPMC, Paris, available in `dh` directory.

2) The generation is achieved from CAD models converted to simmechanics file, as described in http://wiki.icub.org/wiki/Creo_Mechanism_to_URDF , available in the `simmechanics` directory.

As the two pipeline process data from different sources, **the link frames are not guaranteed to have the same orientation 
or location across different models**. The only frames (that are represented in URDF as massless links) whose position is guaranteed to be consistent across different models are the one documented in http://wiki.icub.org/wiki/ICub_Model_naming_conventions#Frames . 

Both generation pipelines are still in `a work in progress` state, and several issues need to be properly solved, e.g.:
* [Meshes are not properly handled #28](https://github.com/robotology-playground/icub-model-generator/issues/28)
* [Gazebo SDF Models are not generated #25](https://github.com/robotology-playground/icub-model-generator/issues/25)
* [Hands and eyes are not generated #29](https://github.com/robotology-playground/icub-model-generator/issues/29)

## Generated models 

| `YARP_ROBOT_NAME` | Pipeline     | Notes                 |
|:-----------------:|:------------:|:---------------------:|
| `iCubDarmstadt01` | simmechanics | v2.5 without backpack |
| `iCubGenova01`    | simmechanics | v2.5 without backpack | 
| `iCubGenova02`    | simmechanics | v2.5   with backpack  | 
| `iCubGenova03`    | dh | v2 with legs v1 and feet v2.5   | 
| `iCubLisboa01`    | dh           | v1 with head v2       |
| `iCubNancy01`     | dh           | v2.5 with arms v2     |
| `iCubParis01`     | dh           | v1 with feet v2.5     | 
| `iCubParis02`     | dh           | v2 with feet v2.5     | 
