# Exploring AI in Bioinformatics

A personal repository documenting my journey as a Bioinformatics and Data Science student exploring the application of machine learning and AI tools to biological problems. The projects here range from hands-on implementations to exploratory experiments with state-of-the-art tools — built with the intent to learn by doing.

---

## About This Repository

I am a BS-MS student in Bioinformatics and Data Science, currently interning at a computational biology startup. This repository reflects my attempts to bridge the gap between biological questions and modern AI/ML approaches — starting from scratch, making mistakes, and figuring things out along the way.

The work here is exploratory by nature. Some of it is structured, some of it is messy, and all of it is part of learning what these tools can and cannot do when applied to real biological data.

---

## Projects

### 1. Bacterial Flagellar Motor Detection using YOLOv8
**Dataset:** [BYU — Locating Bacterial Flagellar Motors 2025 (Kaggle)](https://www.kaggle.com/c/byu-locating-bacterial-flagellar-motors-2025)  
**Tools:** Python, YOLOv8 (Ultralytics/PyTorch), Pandas, Pillow

**What I did:**  
Cryo-electron tomography (cryo-ET) produces 3D volumetric images of bacteria as stacks of 2D slices. The goal of this competition was to detect bacterial flagellar motors — tiny rotary machines that propel bacteria — and predict their 3D coordinates.

I treated this as a 2D object detection problem: extracted the relevant slice for each annotated motor, converted point coordinates to YOLO-format bounding boxes, and fine-tuned a pretrained YOLOv8s model on 360 annotated slices. Inference was run slice-by-slice on test tomograms, with the highest-confidence prediction selected as the 3D motor location.

- 648 tomograms, 451 with annotated motors
- 80/20 train/validation split at the tomogram level
- Achieved **71% mAP50** on the validation set

**What I learned:**  
How to work with volumetric biological imaging data, adapt a general-purpose object detection model to a specialised biological task, and debug a real ML pipeline end to end — including path errors, offline submission constraints, and annotation format conversion.

**Next:** Exploring 3D CNNs to capture volumetric context across slices.

---

### 2. EDA on the BFM Dataset
**Dataset:** Bacterial Flagellar Motor annotation dataset (from the competition above)  
**Tools:** Python, Pandas, Matplotlib

**What I did:**  
Before building any model, I explored the dataset to understand its structure — motor counts per tomogram, coordinate distributions, tomogram dimensions, and voxel spacing variation. This exploratory step informed preprocessing decisions and helped identify edge cases (e.g., tomograms with 10 motors, or those with no motors at all).

**What I learned:**  
How to approach a new biological dataset systematically — checking for imbalance, understanding the label structure, and visualising spatial distributions before writing a single line of model code.

---

### 3. BioEMU — Conformational Sampling
**Tool:** [BioEMU](https://github.com/microsoft/bioemu) (Microsoft Research)  
**Domain:** Protein conformational ensemble generation

**What I did:**  
Uploaded and experimented with BioEMU, a generative model from Microsoft Research that samples protein conformational ensembles — capturing the range of shapes a protein can adopt, rather than just its static structure.

This is an exploratory experiment. Proteins are not rigid; their function is often tied to conformational dynamics. Tools like BioEMU represent a new frontier in structure-based biology, and this is my attempt to understand what they do and where they might be useful.

**Status:** Ongoing experimentation.

---

## Why This Repository Exists

Most of my formal coursework covers the biological and statistical foundations of bioinformatics. What is less covered is how to actually work with modern AI tools — PyTorch, foundation models, generative models for proteins — in a biological context.

This repository is where I fill that gap myself. The goal is not to produce polished results, but to develop a working intuition for what these methods can do, where they fail, and how to think about applying them to real biological questions.

---

## Author

**Anvitha Chetluri**  
BS-MS in Bioinformatics and Data Science, MIT Pune  
[LinkedIn](https://linkedin.com/in/anvitha-chetluri) · [GitHub](https://github.com/AnviSesh) · anvitha.chetluri@gmail.com
