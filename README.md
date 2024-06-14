# Autonobee-Public

This repository contains the code for a website that classifies and segments images of bees using deep learning models. The website features a React frontend and a Firebase backend to manage user authentication, database, and storage. The image classification and segmentation tasks are handled locally in the browser using TensorflowJS.


<img width="1505" alt="Screenshot 2024-06-14 at 7 00 34 PM" src="https://github.com/ShawnPad/Autonobee-Public/assets/59770535/4a647781-af2b-48a6-97b0-7eb40efc0c2e">

<img width="541" alt="Screenshot 2024-06-14 at 7 07 36 PM" src="https://github.com/ShawnPad/Autonobee-Public/assets/59770535/b2c7a4a7-3bed-4bc9-8d22-a07575447219">

## Table of Contents

- [Features](#features)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Models and Data](#models-and-data)
  - [Image Classification Model](#image-classification-model)
  - [Image Data Preprocessing](#image-data-preprocessing)
  - [Sound Data](#sound-data)
- [Contributing](#contributing)
- [License](#license)

## Features

- **User Authentication**: Secure user authentication using Firebase.
- **Image Classification**: Classify uploaded bee images into one of five species using a trained InceptionV3 model.
- **Image Segmentation**: Detect and segment bees in images using the YOLOv4 model.
- **Image and Sound File Handling**: Preview, upload, and download images and associated sound files.
- **TensorflowJS Integration**: Perform image classification and segmentation directly in the browser.

## Setup and Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/yourusername/autonobee-public.git
    cd autonobee-public
    ```

2. **Install dependencies**:
    ```sh
    npm install
    ```

3. **Configure Firebase**:
    - Create a Firebase project.
    - Set up Firebase authentication, Firestore database, and storage.
    - Add your Firebase configuration to a `.env` file in the root directory.

4. **Run the application**:
    ```sh
    npm start
    ```

## Usage

- **Upload Images**: Users can upload images of bees for classification and segmentation.
- **Classification**: The InceptionV3 model classifies the uploaded bee images into one of five species.
- **Segmentation**: The YOLOv4 model segments the bee in the image.
- **Download**: Users can download the processed images and associated sound files.

## Models and Data

### Image Classification Model

The image classification model is based on InceptionV3 with transfer learning to achieve ~91% validation accuracy in classifying five common bee species found in Massachusetts. The model was trained using 11,500 images from the iNaturalist database, covering the following species:

- **Agapostemon Virescens**
- **Apis Mellifera**
- **Bombus Griseocollis**
- **Bombus Impatiens**
- **Xylocopa Virginica**

Training involved a 90-10 split over 500 epochs.

### Image Data Preprocessing

The preprocessing of images from iNaturalist involved the following steps:

1. **Resizing**: Images were resized to 416x416px for YOLOv4.
2. **Bounding Box Creation**: YOLOv4 was trained to detect bees and crea
