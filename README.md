# Diffusion Dataset Captioning from YOLOv8 Format Dataset

This repository provides a pipeline to convert a YOLOv8-formatted CCTV surveillance dataset into a caption-based dataset suitable for training and fine-tuning diffusion models.

The notebook automatically generates multiple scene-aware captions per image using object annotations. This enables the creation of text–image pairs, which are required for training text-to-image diffusion models such as Stable Diffusion.

The project is designed to support synthetic surveillance data generation, particularly for tasks such as violence detection and weapon detection in CCTV environments.

# Project Motivation

Diffusion models require paired text and image data to learn the relationship between visual content and textual descriptions. However, many object detection datasets (such as YOLO datasets) contain only bounding box annotations without textual descriptions.

This project solves that problem by automatically converting object annotations into descriptive captions, enabling object detection datasets to be used for diffusion model training and synthetic data generation.

# Dataset Description

The input dataset follows the YOLOv8 annotation format and is designed for CCTV-based violence and weapon detection.

# Dataset Classes

# The dataset contains three main classes:

Violence
Fighting
Physical aggression
Snatching or violent interactions
Weaponized
Knife
Gun
Rifle
Blunt weapons
Background
Scenes without violence or weapons

Images labeled as background contain empty annotation files.

YOLOv8 Annotation Format

Each image has a corresponding .txt annotation file in YOLO format:

class_id x_center y_center width height

These annotations are used to identify objects present in the scene and generate meaningful captions.

# Caption Generation Pipeline

The notebook processes the YOLO dataset and generates multiple captions per image based on the objects detected.

Steps in the Pipeline
Load YOLO dataset images and labels
Parse object annotations
Identify scene objects and classes
Generate descriptive captions
Create text–image pairs for diffusion training
Example Generated Captions

# For an image containing a weapon:

"A surveillance camera captures a person holding a weapon."
"A person is carrying a knife in a CCTV surveillance scene."
"A security camera view showing a weapon-related activity."

# For violent scenes:

"Two individuals involved in a fight captured by CCTV."
"A violent altercation happening in a surveillance camera frame."

For background scenes:

"A normal surveillance camera view with no suspicious activity."

Multiple captions improve text diversity, which helps diffusion models learn better visual–text relationships.

# Output Dataset Format

After processing, the dataset is converted into a caption-based format suitable for diffusion model training.
