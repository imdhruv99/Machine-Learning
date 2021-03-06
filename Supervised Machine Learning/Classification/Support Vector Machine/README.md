# Support Vector Machine
- SVM is a supervised machine learning algorithm which can be used for classification or regression problems. It uses a technique called the kernel trick to transform your data and then based on these transformations it finds an optimal boundary between the possible outputs.

- The goal of a support vector machine is to find  the optimal separating hyperplane which maximizes the margin of the training data.

- SVM constructs a hyperplane in multidimensional space to separate different classes. SVM generates optimal hyperplane in an iterative manner, which is used to minimize an error. The core idea of SVM is to find a maximum marginal hyperplane(MMH) that best divides the dataset into classes.

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/support-vector-machine-algorithm.png" width="600" height="500" />

#### What is Support Vectors?
- support vectors are datapoints which are closest to the hyperplane. These points will define the separating line better by calculating margins. These points are more relevant to the construction of the classifier.

#### What is Hyperplane?
- A hyperplane is a decision plane which separates between a set of objects having different class memberships.

#### What is Margin?
- A margin is a gap between the two lines on the closest class points. This is calculated as the perpendicular distance from the line to support vectors or closest points. If the margin is larger in between the classes, then it is considered a good margin, a smaller margin is a bad margin.

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/B%26G%20Margin.png" width="650" height="400" />

### Types of SVM

**Linear Support Vector Machine**
-  Linear SVM is used for linearly separable data, which means if a dataset can be classified into two classes by using a single straight line, then such data is termed as linearly separable data, and classifier is used called as Linear SVM classifier.

**Non-Linear Support Vector Machine**
- Non-Linear SVM is used for non-linearly separated data, which means if a dataset cannot be classified by using a straight line, then such data is termed as non-linear data and classifier used is called as Non-linear SVM classifier.

---

#### How Linear SVM works?

##### Identify the right Hyper-Plane

- We will use scenario to identify right hyperplane for each unique dataset.

**Scenario 1**
- Here, we have three hyper-planes (A, B and C). Now, identify the right hyper-plane to classify star and circle.

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s1.png" width="300" height="300" />

- You need to remember a thumb rule to identify the right hyper-plane: 
    **“Select the hyper-plane which segregates the two classes better”.** 
- In this scenario, hyper-plane “B” has excellently performed this job.

**Scenario 2**
- Here, we have three hyper-planes (A, B and C) and all are segregating the classes well. Now, How can we identify the right hyper-plane?

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s2.png" width="300" height="300" />

- Here, maximizing the distances between nearest data point (either class) and hyper-plane will help us to decide the right hyper-plane. This distance is called as Margin. Let’s look at the below snapshot:

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s2_1.png" width="300" height="300" />

- Above, you can see that the margin for hyper-plane C is high as compared to both A and B. Hence, we name the right hyper-plane as C. Another lightning reason for selecting the hyper-plane with higher margin is robustness. If we select a hyper-plane having low margin then there is high chance of miss-classification.

**Scenario 3**
- Here, we have two hyper-planes (A, B). Now how we can identify right Hyper-Plane?

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s3.png"  width="300" height="300" />

- Here Hyper-Plane **B** has higher margin compared to **A**. But, here is the catch, SVM selects the hyper-plane which classifies the classes accurately prior to maximizing margin. Here, hyper-plane B has a classification error and A has classified all correctly. Therefore, the right hyper-plane is A.

**Scenario 4**
- Below, we are unable to segregate the two classes using a straight line, as one of the stars lies in the territory of other(circle) class as an outlier. 

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s4_1.png" width="300" height="300" />

- The SVM algorithm has a feature to ignore outliers and find the hyper-plane that has the maximum margin. Hence, we can say, SVM classification is robust to outliers.

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s4_2.png" width="300" height="300" />

#### How Non-Linear SVM Works?

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s5_1.png" width="300" height="300" />

- In the scenario above, we can’t have linear hyper-plane between the two classes, so how does SVM classify these two classes?

- SVM can solve this problem by converting lower dimensional data into higher dimensional data.  Here, we will add a new feature z = x^2 + y^2. Now, let’s plot the data points on axis x and z:

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s5_2.png" width="300" height="300" />

- In above plot, points to consider are:
- All values for z would be positive always because z is the squared sum of both x and y
- In the original plot, red circles appear close to the origin of x and y axes, leading to lower value    of z and star relatively away from the origin result to higher value of z.

- For this, SVM algorithm has a Technique called **Kernel Trick**.

- When we look at the hyper-plane in original input space it looks like a circle:

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s5_3.png" width="300" height="300" />

#### What is Kernel & Kernel Trick?
- The SVM kernel is a function that takes low dimensional input space and transforms it to a higher dimensional space i.e. it converts not separable problem to separable problem. It is mostly useful in non-linear separation problem.
- Simply put, it does some extremely complex data transformations, then finds out the process to separate the data based on the labels or outputs you’ve defined.

<img src="https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/kernel.png" width="300" height="200" />

#### Pros and Cons associated with SVM

**Pros:**

- It works really well with a clear margin of separation

- It is effective in high dimensional spaces.

- It is effective in cases where the number of dimensions is greater than the number of samples.

- It uses a subset of training points in the decision function (called support vectors), so it is also memory efficient.

**Cons:**

- It doesn’t perform well when we have large data set because the required training time is higher

- It also doesn’t perform very well, when the data set has more noise i.e. target classes are overlapping

- SVM doesn’t directly provide probability estimates, these are calculated using an expensive five-fold cross-validation. It is included in the related SVC method of Python scikit-learn library.