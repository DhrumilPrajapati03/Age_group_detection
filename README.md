# Age Group Detection Model

This project implements a deep learning model to classify individuals into age groups (e.g., "MIDDLE") based on images. The code uses Python with libraries like TensorFlow/Keras, Pandas, NumPy, and Matplotlib to process image data and train a neural network for age group prediction.

## Overview

The code is written in a Jupyter Notebook and performs the following tasks:
- Loads training and test datasets from CSV files.
- Preprocesses images by resizing them to 128x128 pixels.
- Builds and trains a sequential neural network model using Keras.
- Predicts the age group of a sample image from the test set and visualizes the result.

The model outputs predictions such as "MIDDLE" and compares them to the original labels.

## Prerequisites

To run this project, you need the following installed on your system:
- Python 3.6 or higher
- Jupyter Notebook or JupyterLab
- Required Python libraries (see Installation section)

## Installation

1. **Clone the Repository**  
   Clone this repository to your local machine:
   ```
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Set Up a Virtual Environment** (Optional but recommended)  
   Create and activate a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**  
   Install the required libraries using `pip`:
   ```
   pip install numpy pandas matplotlib tensorflow keras pillow imageio scikit-learn
   ```

4. **Download the Dataset**  
   The code assumes datasets are located at:
   - `C:/Users/user/Desktop/Identifying the age group/agedetectiontrain/train.csv`
   - `C:/Users/user/Desktop/Identifying the age group/agedetectiontest/test.csv`
   - Image files in `C:/Users/user/Desktop/Identifying the age group/agedetectiontrain/Train` and `Test` subfolders.

   Update the file paths in the code if your dataset is stored elsewhere.

## Usage

1. **Launch Jupyter Notebook**  
   Start Jupyter Notebook from the project directory:
   ```
   jupyter notebook
   ```

2. **Open the Notebook**  
   Open the `.ipynb` file containing the code in your browser.

3. **Run the Code**  
   - Execute the cells sequentially to:
     - Import libraries.
     - Load the datasets.
     - Preprocess the data and train the model (assumed to be defined earlier in the notebook).
     - Test the model on a sample image (index 2481 in the test set).
   - The output includes:
     - A resized image display using Matplotlib.
     - The original and predicted age group labels (e.g., "Original: MIDDLE Predicted: ['MIDDLE']").

4. **Modify Parameters** (Optional)  
   - Change the `idx` value (e.g., `idx = 2481`) to test different images from the test set.
   - Adjust image resizing dimensions or model architecture as needed (not fully shown in the snippet).

## Project Structure

```
<repository-folder>/
├── README.md               # This file
├── <notebook-name>.ipynb   # Jupyter Notebook with the code
└── dataset/                # Directory for train and test datasets (not included)
    ├── train.csv
    ├── test.csv
    ├── Train/
    └── Test/
```

## Example Output

When running the code with `idx = 2481`:
- An image from the test set is displayed.
- Console output:
  ```
  Age group: MIDDLE
  208/208 [==============================] - 1s 4ms/step
  Original: MIDDLE Predicted: ['MIDDLE']
  ```

The prediction matches the original label, indicating successful classification for this sample.

## Notes

- **Deprecation Warning**: The code uses `imageio.imread`, which triggers a deprecation warning. To suppress this, replace it with `imageio.v2.imread` as suggested in the warning:
  ```python
  import imageio.v2 as imageio
  img = imageio.imread(img_path)
  ```
- **Model Definition**: The snippet assumes a pre-trained `model` and preprocessed `test_x` and `lb` (LabelEncoder) objects. Ensure these are defined earlier in the notebook.
- **File Paths**: Update the hardcoded file paths to match your local setup.

## Contributing

Feel free to submit issues or pull requests to improve the code, such as adding error handling, optimizing the model, or enhancing documentation.
