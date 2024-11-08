![Header](../main/AFDA_Logo.png)

# Machine Learning Project: Early Detection of Alzheimer's Disease

## Project Overview
This project is a deep dive into the intersection of machine learning and healthcare, aimed at studying Alzheimer's Disease and showcasing how AI can assist in early diagnosis. Leveraging TensorFlow and audio data, the model is designed to predict if a person shows signs of Alzheimer's based on a 4-second audio clip, achieving a validation accuracy of 78%.

## Data Source
The project utilized the **DementiaNet** dataset, which includes medical data from patients with dementia and healthy individuals collected specifically for machine learning research. More details about the dataset can be found [here](https://github.com/shreyasgite/dementianet).
But the proccesed and cleaned data can be found at my Google Drive at the end of this README

### Dataset Summary
- The original dataset consists of 359 audio samples sourced from public figures, with 131 samples from individuals diagnosed with dementia. The audio samples vary in length, covering cases from recent diagnoses to those over 15 years.
- The data was downloaded, processed locally, and uploaded to Google Drive for further analysis.

### Data Processing
To prepare the data for training:
- Samples related to other conditions were filtered out, resulting in a reduced dataset of approximately 54 Alzheimer's patients.
- To balance the dataset and enable faster processing, the Alzheimer's audio samples were segmented into four 4-second clips each, while healthy patient samples were split into two 4-second segments.
- The CSV file was cleaned to retain only relevant data, yielding a final dataset of 202 samples from healthy individuals and 202 from Alzheimer's patients.

## Technical Details
### Model Architecture
- **Conv1D**: One-dimensional convolutional layers were chosen due to the sequential nature of the problem, allowing the model to detect special features within the patients' voices.
- **LSTM**: Long Short-Term Memory layers were incorporated to understand the sequential information of the data. After extracting key audio features using MFCC and Conv1D layers, LSTM captures long-term dependencies and mitigates gradient vanishing.
- **Batch Normalization**: This technique normalizes activations between layers, improving processing efficiency and acting as a regularization method to enhance the model's generalization.
- **Pooling**: Reduces the information processed by the network while retaining the most relevant values, lowering data dimensionality.

### Training Techniques
- **ModelCheckpoint**: Saves the best-performing models during training.
- **Early Stopping**: Stops training early if no improvements are observed, optimizing the training process and computational efficiency.
- **ReduceLROnPlateau**: Adjusts the learning rate when no improvements are detected over a specified period, allowing better adaptation and convergence.

### Model Approach
Our model combines convolutional and LSTM layers to capture both local and temporal patterns in audio data. The parameter tuning aimed to explore even subtle patterns, supported by an analysis of prior technologies and techniques.

## Results Discussion
The outcomes were as follows:

- **Training Precision**: 95%, indicating that the model learned the features from the training data effectively.
- **Validation Precision**: 78%, lower than training precision, suggesting potential overfitting, though it remains a strong result that could be enhanced with additional data and configuration tweaks.
- **Training Loss**: 0.28, showing that the predictions were generally accurate, but validation results hint at overfitting.
- **Validation Loss**: 0.98.
- **Training AUC**: 0.87, demonstrating a good capacity for class discrimination during training.
- **Validation AUC**: 0.89, indicating reliable class discrimination in validation as well.

### Performance Visualization
The model's performance is illustrated in the following confusion matrix:

<img src="../main/Matriz.PNG" alt="Confusion Matrix" style="height: 300px; width:500px;"/>

### Comparative Analysis
Compared to other studied projects, the results were strong given the limited dataset, showcasing the power of convolutional layers and MFCC in disease discrimination. The performance was similar to projects 1 and 4, but there is room for improvement to build even more robust models.

## Explore and Collaborate
For more details, code, and resources, check out the full project here or read The Paper found in this repository in spanish or in english:
[Download the project code](https://drive.google.com/drive/folders/1E8C5mfUhUIn2kf5w-dWC5QCEYz7wVLqw?usp=drive_link)

---
**Interested in collaborating or bringing innovative AI solutions to your team?** Connect with me to discuss how we can push the boundaries of AI-driven healthcare together!
