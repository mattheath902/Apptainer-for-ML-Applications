# Apptainer YOLOv8 Example

This repository shows how to containerize and deploy an existing machine learning model using [Apptainer](https://apptainer.org/) on NCSU's infrastructure. It's intended as a reference for students looking to create reproducible environments—especially on NCSU systems where sudo access and personal installations are restricted.

## Purpose

Containerization is a key part of reproducible research and scalable deployment. This project shows how to:

- Wrap a third-party ML model in an Apptainer container
- Create a portable, isolated environment
- Run the model on NCSU's HPC systems or other Linux-based environments

## Instructions

### Build the image from the definition file (container name does not matter):  
```bash
    apptainer build container_image_name.sif neuralnet.def  
```
This will take some time as apptainer has to make an independent environment and perform all the specified installs in the definition file.  

### Once the container finishes downloading dependencies you can go into the container by running:  
```bash
    apptainer shell container_image_name.sif
```  

This will take you into the container that has the dependencies specified in the definition file  

From our example you can run the model by running the python script as shown below.  
```bash
    python action_recognition.py 
```  

To play with the model more refer to the ultralyics markdown file.  

## Included Example: YOLOv8 Action Recognition

To demonstrate the process, we’ve included an example model from the [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) repository — specifically the `YOLOv8-Action-Recognition` example.

**Note:** We do not claim ownership of this code. It is used here under the terms of its original license (see below) for educational and demonstrative purposes.

## ⚖️ License & Attribution

The original YOLOv8 example is from the [Ultralytics GitHub repo](https://github.com/ultralytics/ultralytics) and is subject to their [GPL-3.0 license](https://github.com/ultralytics/ultralytics/blob/main/LICENSE).

If you use or modify this repository, please also credit Ultralytics accordingly.

## 📚 Resources

- [Apptainer Documentation](https://apptainer.org/docs/)
- [NCSU HPC User Guide](https://hpc.ncsu.edu/)
- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)

