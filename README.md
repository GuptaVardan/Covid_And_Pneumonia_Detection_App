# COVID and Pneumonia Detection using Deep Learning

A Flask-based web application that analyzes chest X-ray images to detect **COVID-19**, **pneumonia**, or **normal** conditions. Users can **upload an X-ray image** or **capture one via a webcam**; the app then uses a pre-trained deep learning model to classify the image. The model (`models/detector_model.h5`) and its label encoder (`models/label_encoder.pkl`) are loaded on startup.

## Features

- **Image Upload**: Select and upload a chest X-ray image (PNG/JPEG) through the web interface.  
- **Webcam Capture**: Real-time camera view for capturing a chest X-ray photo directly from your webcam.  
- **Deep Learning Classification**: Convolutional Neural Network classifies images as **COVID-19**, **Pneumonia**, or **Normal**.  
- **Instant Results**: Displays predicted label and confidence score immediately after submission.  

## Tech Stack

- **Python 3**  
- **Flask**  
- **TensorFlow / Keras**  
- **OpenCV**  
- **scikit-learn**  
- **HTML / CSS / JavaScript**  

## Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/GuptaVardan/Covid_And_Pneumonia_Detection_App.git
   cd Covid_And_Pneumonia_Detection_App
    ````

2. **Create and activate a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate     # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Prepare model files**
   Ensure the following files are present in the `models/` directory:

   * `detector_model.h5`
   * `label_encoder.pkl`


## Usage

1. **Run the Flask server**

   ```bash
   python app.py
   ```

2. **Open the app in your browser**
   Navigate to `http://127.0.0.1:5000`.

3. **Upload an X-ray image**

   * On the home page, use the file upload form to select a chest X-ray image.
   * Click **Upload Image**.
   * View the predicted label and confidence score.

4. **Capture via webcam**

   * Click **Open Camera** or visit `http://127.0.0.1:5000/camera`.
   * Allow camera access, then click **Capture Image**.
   * The snapshot will be classified and results displayed.

### Final Performance Metrics

- **Training Accuracy:** 99.47%  
- **Training Loss:** 0.0129  
- **Validation Accuracy:** 94.80%  
- **Validation Loss:** 0.2469  

### Confusion Matrix on Test Set

| True \ Pred   | COVID-19 | Pneumonia | Normal |
|---------------|----------|-----------|--------|
| **COVID-19**  | 663      | 58        | 2      |
| **Pneumonia** | 52       | 1981      | 6      |
| **Normal**    | 5        | 17        | 247    |