# MNIST
The agenda of this project to reach an accuracy of 99.4 % within 15 epochs and 15000 parameters

### [**Step by Step Network Update**](https://docs.google.com/spreadsheets/d/1NUM1eW6RdCb2L5-g2rbJ2UoGToiRC5IRQzwvw-CcVtU)

#### **Code 1 - Setup**

1. Get the set-up right
2. Set Transforms
3. Set Data Loader
4. Set Basic Working Code
5. Set Basic Training  & Test Loop
6. Network <br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x20 | 22x22x20<br/>22x22x20 | MP | 11x11x20<br/>11x11x20 | 1x1x10 | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x20 | 7x7x20<br/>7x7x20 | 1x1x10 | 7x7x10<br/>7x7x10 | 7x7x10 | 1x1x10

7. Results:
   - Parameters: 10790
   - Best Training Accuracy: 99.12
   - Best Test Accuracy: 99.8
8. Analysis:
   * This is good enough model, but we have reach an accuracy of 99.4 % within 15 epochs and 15000 parameters 

#### **Code 2 - Batch Normalization**

1. Include Batch Normalization
2. Network <br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x10 | 7x7x10<br/>7x7x10 | 1x1x10 | 7x7x10<br/>7x7x10 | 7x7x10 | 1x1x10
3. Results:
   - Parameters: 8690
   - Best Training Accuracy: 99.21
   - Best Test Accuracy: 99.03
4. Analysis:
   * Though accuracy is increased, we are observing slight overfitting here.
   - For other variations in this step, refer to Code_2_(Batch_Norm)_EVA4S5F2.ipynb
