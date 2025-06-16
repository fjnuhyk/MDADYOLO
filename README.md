# 1 Requirements
Install the following dependencies (if not already available):
```
pip install torch torchvision opencv-python
pip install ultralytics
```

# 2 Clone the YOLO repository

```
git clone https://github.com/MDADYOLO/
cd MDADYOLO
```
# 3 Place model weight file

Pre-trained model weights are located in the weights/ directory:

`MDADYOLO_for_Eggplant.pt` — Trained on the Eggplant dataset

`MDADYOLO_for_Pepper.pt` — Trained on the Pepper dataset

Choose the appropriate weight file depending on your target dataset.

# 4 Prepare test image
Representative test images are provided in the dataset/ directory. You may also add your own images for testing.


# 5 Run inference
To perform inference using a specific model weight and test image, run the following command:
For Eggplant:
```
yolo task=detect mode=predict \
  model=weights/MDADYOLO_for_Eggplant.pt \
  source=dataset/eggplant_test.jpg
```

For Pepper:
```
yolo task=detect mode=predict \
  model=weights/MDADYOLO_for_Pepper.pt \
  source=dataset/pepper_test.jpg
```

`model`: Path to the weight file
`source`: Path to the test image

# 6 Output
After inference, the results will be saved in the `runs/detect/predict/` directory. Outputs include:
The image with bounding boxes overlaid
Detection results (e.g., bounding box coordinates and class probabilities)

# 7 Project Structure
```
MDADYOLO/
├── weights/                  # Model weights
│   ├── MDADYOLO_for_Eggplant.pt
│   └── MDADYOLO_for_Pepper.pt
├── dataset/                  # Sample test images
│   ├── eggplant_test.jpg
│   └── pepper_test.jpg
├── README.md (or readme.txt)
└── ...                      # Other project files
```

If you require the full dataset or source code, please contact the first author.

