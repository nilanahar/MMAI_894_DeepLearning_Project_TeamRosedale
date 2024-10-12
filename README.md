# MMAI'25 894 Deep Learning Project - Team Rosedale
Model Developer: Shamsun Nila 

## Visual Question Answering (VQA) Project

This repository contains the code for a Visual Question Answering (VQA) system that processes both image and text data to answer questions related to the image. The project includes feature engineering, model building, hyperparameter tuning using Optuna, and performance evaluation.

### Overview
The goal of this project is to build a machine learning model capable of answering questions about images by combining text (questions) and image data. The model is trained using PCA-transformed features from images and embeddings from questions, answers, and other textual inputs.

### Features
- **Feature Engineering**: ResNet50 for extracting image features, Google Word2Vec similarity filtering for multiple-choice answers, PCA transformation for image inputs, and label encoding of categorical features.
- **Model Architecture**: A neural network that concatenates PCA-transformed image features, question embeddings, answer embeddings, and additional encoded features like `answer_type_encoded` and `answer_confidence_encoded`.
- **Hyperparameter Optimization**: Automated hyperparameter tuning using Optuna to find the optimal network architecture and training parameters.
- **Evaluation Metrics**: Categorical cross-entropy and accuracy are used to evaluate model performance.

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/vqa-project.git
   cd vqa-project
   ```

2. **Install the required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up your data**:
   - Place your training, validation, and test datasets in the `data/` directory or adjust the paths in the scripts as needed.


### Model Architecture

The model consists of:
- **Input Layers**: PCA-transformed image features, question embeddings, answer embeddings, `answer_type_encoded`, and `answer_confidence_encoded`.
- **Dense Layers**: Two fully connected layers with ReLU activation and dropout for regularization.
- **Output Layer**: Softmax output layer for multi-class classification.

The architecture is optimized using hyperparameter tuning for the number of units in each dense layer, dropout rate, and learning rate.

### Hyperparameter Tuning

Hyperparameter tuning is performed using Optuna to maximize validation accuracy. The following hyperparameters are optimized:
- Number of units in the dense layers.
- Dropout rate.
- Learning rate.

### Performance Evaluation

After training, the model is evaluated using:
- **Accuracy**: The percentage of correct answers.
- **Categorical Cross-Entropy Loss**: Loss function used for multi-class classification.
- Optionally, you can compute additional metrics like F1-score, precision, and recall depending on your task requirements.

### Contributing

Contributions are welcome! If you have ideas for improving the project or would like to fix issues, feel free to submit a pull request.

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to customize this README to fit your specific project details and repository structure! Let me know if you'd like help with any particular section or improvement.
