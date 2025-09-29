# Cat vs Dog Image Classification

A machine learning project that uses Convolutional Neural Networks (CNN) to classify images as either cats or dogs. This project implements a binary image classifier using TensorFlow and Keras.

## 🐱 🐶 Project Overview

This project builds and trains a CNN model to automatically detect and classify images of cats and dogs. The model uses deep learning techniques including convolutional layers, pooling layers, and data augmentation to achieve accurate classification results.

## 🚀 Features

- **CNN Architecture**: Custom convolutional neural network with multiple Conv2D and MaxPooling2D layers
- **Data Augmentation**: Implements image preprocessing techniques like rescaling, shearing, zooming, and horizontal flipping
- **Binary Classification**: Distinguishes between cat and dog images with high accuracy
- **Real-time Prediction**: Load and classify new images using the trained model

## 🛠️ Technologies Used

- **Python**: Core programming language
- **TensorFlow**: Machine learning framework
- **Keras**: High-level neural networks API
- **NumPy**: Numerical computing
- **Jupyter Notebook**: Development environment

## 📋 Requirements

```bash
tensorflow
keras
numpy
matplotlib (optional, for visualization)
```

## 🏗️ Model Architecture

The CNN model consists of:

1. **Convolutional Layers**: 
   - Conv2D(32, (3,3)) with ReLU activation
   - Conv2D(16, (3,3)) with ReLU activation
2. **Pooling Layers**: MaxPooling2D with (2,2) pool size
3. **Dense Layers**: 
   - Multiple fully connected layers (64, 32, 16, 8, 4 neurons)
   - Output layer with sigmoid activation for binary classification
4. **Compilation**: Uses binary crossentropy loss and Adam optimizer

## 📊 Data Preparation

The model expects:
- **Training Data**: Images organized in folders by class (cats/dogs)
- **Testing Data**: Separate validation dataset
- **Image Size**: 64x64 pixels
- **Color Channels**: RGB (3 channels)
- **Data Augmentation**: Applied to training data to improve model generalization

## 🚀 Usage

### Training the Model

1. Open `catsdogs.ipynb` in Jupyter Notebook
2. Ensure your dataset is organized in the following structure:
   ```
   training data/
   ├── cats/
   └── dogs/
   
   testing data/
   ├── cats/
   └── dogs/
   ```
3. Update the file paths in the notebook to match your dataset location
4. Run all cells to train the model

### Making Predictions

```python
import numpy as np
from keras.preprocessing import image

# Load and preprocess image
img = image.load_img('path_to_your_image.jpg', target_size=(64,64))
img = image.img_to_array(img)
img = np.expand_dims(img, axis=0)

# Make prediction
prediction = cnn.predict(img)

# Interpret result
if prediction[0][0] > 0.5:
    print("DOG")
else:
    print("CAT")
```

## 📈 Training Parameters

- **Epochs**: 50
- **Batch Size**: 32
- **Steps per Epoch**: 2000
- **Validation Steps**: 100
- **Input Shape**: (64, 64, 3)

## 📁 Files Description

- `catsdogs.ipynb`: Main notebook containing the complete model implementation
- `catsdogs-checkpoint.ipynb`: Checkpoint file for the notebook
- `README.md`: Project documentation

## 🎯 Performance

The model uses binary crossentropy loss function and is optimized with the Adam optimizer. Performance can be evaluated using:
- Training accuracy
- Validation accuracy
- Loss curves
- Confusion matrix

## 🔮 Future Improvements

- [ ] Add model evaluation metrics and visualization
- [ ] Implement transfer learning with pre-trained models
- [ ] Add support for multi-class classification (more animal types)
- [ ] Create a web interface for easy image upload and prediction
- [ ] Optimize model architecture for better performance
- [ ] Add data visualization and exploratory data analysis

## 🤝 Contributing

Feel free to fork this project and submit pull requests for any improvements!

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

**Note**: Make sure to update the file paths in the notebook to match your local dataset location before training the model.