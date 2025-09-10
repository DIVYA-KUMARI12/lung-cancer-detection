#📘 Lung Cancer Detection System

A deep learning-based system to classify lung CT scans into 4 categories (cancer/non-cancer) using Convolutional Neural Networks (CNNs) with residual connections. The project also includes a Flask API for real-time predictions.

#📂 Project Structure
├── app.py                     # Flask API for serving predictions
├── prediction.py              # Prediction pipeline
├── Lung_Cancer_Detection.ipynb # Model training notebook
├── README.md                  # Project documentation
├── .gitignore                 # Ignore unnecessary files
└── lung-cancer-detection/     # Project folder (images, models, etc.)

#🎯 Features

Classifies CT scans into 4 categories:

{
  "adenocarcinoma": 0,
  "large.cell.carcinoma": 1,
  "normal": 2,
  "squamous.cell.carcinoma": 3
}


• Achieved ~99% training accuracy and ~83% validation/test accuracy.

• Implemented learning rate scheduler for stable convergence.

• Flask API for easy integration into applications.

• Supports real-time image uploads for prediction.

#🧠 Model Training

• Framework: TensorFlow / Keras

• Optimizer: Adam

• Techniques: Residual connections, interpolation, ImageDataGenerator for preprocessing

• Metrics: Accuracy, Precision, Recall

**Training Logs Snapshot:**

**Epoch	Accuracy**
1	52%
12	99%
20	Training: 99.8%, Validation: 82.8%

#🧪 **Testing**

• Dataset: 315 CT scan images (4 classes)

• Test Accuracy: ~79–83%

• Example Prediction Output:

• array([0, 3, 3, 3, 0, 3, 1, 2, ...])


# **Interpretation:**

0 → adenocarcinoma

1 → large.cell.carcinoma

2 → normal

3 → squamous.cell.carcinoma

#🚀 **API Usage**

Endpoint: POST http://127.0.0.1:5000/predict

Request Body:

Type: form-data

Key: image → Upload CT scan image

**Example (using curl):**

curl -X POST http://127.0.0.1:5000/predict \
-F "image=@sample_image.jpg"


**Example Response:**

{
  "class": "adenocarcinoma",
  "confidence": 0.92
}

#📊 **Future Improvements**

• Apply data augmentation to balance underrepresented classes.

• Explore transfer learning with models like InceptionResNet or EfficientNet.

• Deploy API on Heroku / AWS / GCP for public use.

#⚙️ **Tech Stack**

1. Python

2. TensorFlow / Keras

3. Flask

4. NumPy, Matplotlib

5. Google Colab / Jupyter Notebook

#📜 **How to Run Locally**
# Clone the repository
git clone https://github.com/DIVYA-KUMARI12/Lung-Cancer-Detection.git
cd Lung-Cancer-Detection

# Install dependencies
pip install -r requirements.txt

# Train the model (optional)
jupyter notebook Lung_Cancer_Detection.ipynb

# Run Flask API
python app.py

# Test API
# Open Postman/curl and hit http://127.0.0.1:5000/predict with an image file
