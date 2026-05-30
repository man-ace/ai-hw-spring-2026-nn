Multi-Layer Perceptron (MLP)

● Layer Hierarchy: Input Flatten layer (28x28 to 784 dimensions) -> Dense layer (128
units, ReLU activation) -> Dense layer (64 units, ReLU activation) -> Dense Output layer
(10 units, Softmax activation).

● Optimization Strategy: Compiled via the Adam optimizer, utilizing Sparse Categorical
Crossentropy as the objective loss function.

● Training History: Commenced at an initial epoch accuracy of 92.96% (loss: 0.2408) and
advanced steadily to finish at 98.63% accuracy (loss: 0.0432) by the fifth epoch.

● Evaluation Outcome: Sustained robust generalization with a final evaluation test
accuracy of 97.14% and a test loss of 0.0938.


Convolutional Neural Network (CNN)

● Layer Hierarchy: Conv2D (32 filters, 3x3 kernel, ReLU) -> MaxPooling2D (2x2) ->
Conv2D (64 filters, 3x3 kernel, ReLU) -> MaxPooling2D (2x2) -> Flatten -> Dense layer
(64 units, ReLU) -> Dropout layer (0.5 rate) -> Dense Output layer (10 units, Softmax).

● Optimization Strategy: Evaluated with a 10% validation split from the training dataset,
structured with a batch size of 64, optimized via Adam, and tracked using Sparse
Categorical Crossentropy.

● Training History: Opened epoch 1 with a baseline training accuracy of 89.75%
(validation accuracy: 98.25%). Progressed to a final training accuracy of 97.93% with a
validation accuracy peaking at 99.12% and validation loss minimizing to 0.0346.

● Evaluation Outcome: Delivered the benchmark-leading performance, registering an elite
test accuracy of 98.78% paired with a minimal test loss of 0.0327.


Transformer Model Details

● Layer Hierarchy: Input tensor (28x28x1) -> Conv2D patch extractor (64 filters, 7x7
kernel, stride 7, valid padding) -> Reshape layer to sequence dimensions (16, 64) ->
Lambda wrapped Multi-Head Attention (8 heads, key dimension of 64) -> Layer
Normalization (epsilon 1e-6) -> Global Average Pooling 1D -> Dense layer (64 units,
ReLU) -> Dense Output layer (10 units, Softmax).

● Optimization Strategy: Structured with a batch size of 64, using the Adam optimizer and
Sparse Categorical Crossentropy loss.

● Training History: Showed slower convergence behavior. Initialized at 53.14% accuracy
(loss: 1.3378) in epoch 1, climbing incremental margins to conclude epoch 5 at 65.14%
training accuracy (loss: 1.0082).

● Evaluation Outcome: Finished with a final test accuracy of 66.05% and a test loss of
0.9958.

Final Results
| Model Architecture | Final Training Accuracy (Epoch 5) | Final Test Accuracy | Final Test Loss |
| :--- | :--- | :--- | :--- |
| **Convolutional Neural Network (CNN)** | 97.93% | **98.78%** | **0.0327** |
| **Multi-Layer Perceptron (MLP)** | 98.63% | **97.14%** | 0.0938 |
| **Transformer Model** | 65.14% | **66.05%** | 0.9958 |
