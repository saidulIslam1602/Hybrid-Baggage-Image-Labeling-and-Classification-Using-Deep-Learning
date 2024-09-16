### Project Overview: Hybrid Baggage Image Labeling and Classification Using Deep Learning

This project focuses on developing a hybrid system for the classification and organization of baggage images, combining manual labeling techniques with automated deep learning-based classification. It is designed for scenarios where a large set of unlabeled baggage images needs to be categorized into different material types (e.g., soft plastic, metal, wood). The goal is to streamline and improve the labeling process by leveraging both human input and a deep learning model.

### Key Features:
1. **Manual Image Labeling Interface**:
   - A Python-based interface for displaying unlabeled images and allowing users to assign class labels manually.
   - After labeling, images are automatically moved to the appropriate class folder.
   - Includes an interactive display function using OpenCV and Matplotlib to visually inspect each image before labeling.

2. **Automatic Classification Using ResNet50**:
   - A pre-trained ResNet50 model is fine-tuned to classify baggage images into predefined categories based on their material type.
   - The model is frozen except for the final fully connected layer, which is adapted to classify the number of classes in the dataset.
   - Once trained, the model automatically predicts the class for each unlabeled image and moves the images to the corresponding class folder.
   
3. **Training Process**:
   - The labeled dataset, organized into class folders, is used to train the model with data augmentation and normalization techniques.
   - The model is optimized using cross-entropy loss and Adam optimizer, training for multiple epochs with a focus on minimizing classification error.
   - Model performance is evaluated after each epoch, providing a loss metric to monitor training progress.

4. **Batch Image Processing and Organization**:
   - Once trained, the model can process batches of unlabeled images and predict their class.
   - The predicted images are then moved to their corresponding class folders for easier organization and further inspection.

### Workflow:
1. **Manual Labeling**:
   - The user loads the unlabeled images and begins labeling them using the provided labeling interface.
   - For each image, the user can assign it to one of the predefined classes (e.g., soft plastic, metal, wood).
   - Once labeled, the images are moved into class-specific folders for future use in training the deep learning model.

2. **Training the Deep Learning Model**:
   - After a sufficient number of images are labeled, the labeled dataset is loaded into PyTorch using the `ImageFolder` format.
   - A pre-trained ResNet50 model is fine-tuned using these labeled images.
   - The model learns to differentiate between the different classes (materials) based on image features and is optimized for several epochs.

3. **Automatic Classification and Organization**:
   - The trained model is then applied to the unlabeled dataset.
   - For each image, the model predicts the class and moves the image to the corresponding folder, organizing the data efficiently without further human intervention.

### Project Applications:
This project is particularly useful in domains where large amounts of visual data need to be classified, such as:
- Airport baggage scanning
- Automated product categorization in warehouses
- Waste material classification for recycling
