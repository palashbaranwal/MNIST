# MNIST
The agenda of this project to reach an accuracy of 99.4 % within 15 epochs and 15000 parameters

### [**Step by Step Network Update**](https://docs.google.com/spreadsheets/d/1NUM1eW6RdCb2L5-g2rbJ2UoGToiRC5IRQzwvw-CcVtU)

#### **Code 1 - Setup**

1. Get the set-up right
2. Set Transforms
3. Set Data Loader
4. Set Basic Working Code
5. Set Basic Training  & Test Loop
6. Network <br/><br/> 28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x20 | 22x22x20<br/>22x22x20 | MP | 11x11x20<br/>11x11x20 | 1x1x10 | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x20 | 7x7x20<br/>7x7x20 | 1x1x10 | 7x7x10<br/>7x7x10 | 7x7x10 | 1x1x10

7. Results:
   - Parameters: 10790
   - Best Training Accuracy: 99.12
   - Best Test Accuracy: 99.8
8. Analysis:
   * This is good enough model, but we have reach an accuracy of 99.4 % within 15 epochs and 15000 parameters 

#### **Code 2 - Batch Normalization**

1. Include Batch Normalization
2. Network <br/><br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x10 | 7x7x10<br/>7x7x10 | 1x1x10 | 7x7x10<br/>7x7x10 | 7x7x10 | 1x1x10

3. Results:
   - Parameters: 8690
   - Best Training Accuracy: 99.21
   - Best Test Accuracy: 99.03
4. Analysis:
   * Though accuracy is increased, we are observing slight overfitting here.
   - For other variations in this step, refer to [**Step by Step Network Update**]

#### **Code 3 - Include Regularization**

1. Include Regularization
2. Network <br/><br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x10 | 7x7x10<br/>7x7x10 | 1x1x10 | 7x7x10<br/>7x7x10 | 7x7x10 | 1x1x10

3. Results (Three Executions):
   - Parameters: 8810
   - **Best Training Accuracy : 99.20, 99.22, 99.23**
   - **Best Test Accuracy: 99.21, 99.15, 99.20**
4. Analysis:
   * This model is really nice, overfitting at its least. 
   * To check the effect of dropout at different levels of convolution, refer to [**Step by Step Network Update**](https://docs.google.com/spreadsheets/d/1NUM1eW6RdCb2L5-g2rbJ2UoGToiRC5IRQzwvw-CcVtU)

#### **Code 4 - Include Global Average Pooling**

1. Include Global Average Pooling
2. Network <br/><br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x10 | 7x7x10<br/>7x7x10 | 1x1x10 | 7x7x10<br/>7x7x10 | GAP | 1x1x10

3. Results :
   - Parameters: 3910
   - Best Training Accuracy : 98.25
   - Best Test Accuracy: 98.62
4. Analysis:
   * Using GAP has decreased the number of parameters to less than 5000, which is a good thing. But our accuracy has dropped. 
   * Since we have reduced model capacity, accuracy reduction is expected. 
   
#### **Code 5 - Increase Capacity**

1. Include further capacity
2. Network <br/><br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x32 | 7x7x32<br/>7x7x32 | 3x3x10 | 5x5x10<br/>5x5x10 | 3x3x10 | 3x3x10<br/>3x3x10 | GAP | 1x1x10

3. Results :
   - Parameters: 9634
   - Best Training Accuracy : 99.28
   - Best Test Accuracy: 99.4 (9th Epoch) 99.44 (11th Epoch)
4. Analysis:
   * We have achieved our target of 99.4 % accuracy. 
   * As number of parameters is already 9500+, we should not be trying to add a layer after GAP.
   * For other variations in this step, refer to [**Step by Step Network Update**](https://docs.google.com/spreadsheets/d/1NUM1eW6RdCb2L5-g2rbJ2UoGToiRC5IRQzwvw-CcVtU)
   
#### **Code 6 - Image Augmentation**

1. Include Image Augmentation
2. Network <br/><br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x32 | 7x7x32<br/>7x7x32 | 3x3x10 | 5x5x10<br/>5x5x10 | 3x3x10 | 3x3x10<br/>3x3x10 | GAP | 1x1x10

3. Results :
   - Parameters: 9634
   - Best Training Accuracy : 99.1
   - Best Test Accuracy: 99.4 
4. Analysis:
   * Rotational variance seems to work just fine. 
   * Rotational Variance and Random Erasing does not seems to work for us.  [Random Erasing](https://arxiv.org/pdf/1708.04896.pdf) - Randomly selects a rectangle region in an image and erases its pixels. 
   * Random Erasing works quite well, with minimizing overfitting. However, it does not meets our target of 99.4 % accuracy.
   * For other variations in this step, refer to [**Step by Step Network Update**](https://docs.google.com/spreadsheets/d/1NUM1eW6RdCb2L5-g2rbJ2UoGToiRC5IRQzwvw-CcVtU)

#### **Code 7 - Adding LR Scheduler **

1. Adding LR Scheduler
2. Network <br/><br/>28x28x1 | 3x3x10 | 26x26x10<br/>26x26x10 | 3x3x10 | 24x24x10<br/>24x24x10 | 3x3x10 | 22x22x10<br/>22x22x10 | MP | 11x11x10<br/>11x11x10 | 3x3x10 | 9x9x10<br/>9x9x10 | 3x3x32 | 7x7x32<br/>7x7x32 | 3x3x10 | 5x5x10<br/>5x5x10 | 3x3x10 | 3x3x10<br/>3x3x10 | GAP | 1x1x10

3. Results :
   - Parameters: 9634
   - Best Training Accuracy : 99.1
   - Best Test Accuracy: 99.41 (12th epoch) 99.42 (13th epoch) 99.42 (14th epoch) 
4. Analysis:
   * **We have again achieved 99.4 % accuracy !!!** 
   * For other variations in this step, refer to [**Step by Step Network Update**](https://docs.google.com/spreadsheets/d/1NUM1eW6RdCb2L5-g2rbJ2UoGToiRC5IRQzwvw-CcVtU)


   
