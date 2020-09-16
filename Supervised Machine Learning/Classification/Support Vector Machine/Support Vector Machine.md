# Support Vector Machine
- SVM is a supervised machine learning algorithm which can be used for classification or regression problems. It uses a technique called the kernel trick to transform your data and then based on these transformations it finds an optimal boundary between the possible outputs.

- The goal of a support vector machine is to find  the optimal separating hyperplane which maximizes the margin of the training data.

- SVM constructs a hyperplane in multidimensional space to separate different classes. SVM generates optimal hyperplane in an iterative manner, which is used to minimize an error. The core idea of SVM is to find a maximum marginal hyperplane(MMH) that best divides the dataset into classes.

![Support Vector Machine](https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/support-vector-machine-algorithm.png)

#### What is Support Vectors?
- support vectors are datapoints which are closest to the hyperplane. These points will define the separating line better by calculating margins. These points are more relevant to the construction of the classifier.

#### What is Hyperplane?
- A hyperplane is a decision plane which separates between a set of objects having different class memberships.

#### What is Margin?
- A margin is a gap between the two lines on the closest class points. This is calculated as the perpendicular distance from the line to support vectors or closest points. If the margin is larger in between the classes, then it is considered a good margin, a smaller margin is a bad margin.

![Bad and Good Margin](https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/B%26G%20Margin.png)

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

![Scenario 1](https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s1.png)

- You need to remember a thumb rule to identify the right hyper-plane: 
    **“Select the hyper-plane which segregates the two classes better”.** 
- In this scenario, hyper-plane “B” has excellently performed this job.

**Scenario 2**
- Here, we have three hyper-planes (A, B and C) and all are segregating the classes well. Now, How can we identify the right hyper-plane?

![Scenario 2-1](https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s2.png)

- Here, maximizing the distances between nearest data point (either class) and hyper-plane will help us to decide the right hyper-plane. This distance is called as Margin. Let’s look at the below snapshot:

![Scenario 2-2](https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s2_1.png)

- Above, you can see that the margin for hyper-plane C is high as compared to both A and B. Hence, we name the right hyper-plane as C. Another lightning reason for selecting the hyper-plane with higher margin is robustness. If we select a hyper-plane having low margin then there is high chance of miss-classification.

**Scenario 3**
- Here, we have two hyper-planes (A, B). Now how we can identify right Hyper-Plane?

![Scenario 3](https://github.com/imdhruv99/Machine-Learning/blob/master/Supervised%20Machine%20Learning/Classification/Support%20Vector%20Machine/assets/svm_s3.png)

- Here Hyper-Plane **B** has higher margin compared to **A**. But, here is the catch, SVM selects the hyper-plane which classifies the classes accurately prior to maximizing margin. Here, hyper-plane B has a classification error and A has classified all correctly. Therefore, the right hyper-plane is A.