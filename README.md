# Water Quality Analysis 
This is a project our group, Peer Learning Group 6 worked on which focuses on using an AI model with TensorFlow/Keras for analyzing water quality data and predicting water quality. We predict the quality of water samples as either "Safe" or "Unsafe." Our model can generalize well on unseen data, thereby assisting in identifying potentially unsafe water samples.


## Group Structure and Task Allocation

This project was completed as part of a collaborative effort among five members of a peer learning group. The responsibilities were divided as follows:

### Team Members and Roles
1. **Loue Sauveur Christian**  
   - **Email**: [I.christian@alustudent.com]
   - **Contribution**: Loue focused on building the model using L2 Regularization and the Adam optimizer. 


Joel Karekezi MugishaJoel Karekezi MugishaJolly UmulisaJolly Umulisagroup leader Kanisa Rebecca Majok ThiakKanisa Rebecca Majok Thiak Loue Sauveur ChristianLoue Sauveur Christian


2. **Favour Akinwande**  
   - **Email**: [f.akinwande@alustudent.com]

   - **Contribution**: Favour worked on optimizing the model using L1 Regularization with the SGD optimizer for the model Implementation. 


3. **Kanisa Rebecca Majok Thiak**  
   - **Email**: [K.thiak@alustudent.com]    
   - **Contribution**: Kanisa worked on optimizing the model using L2 Regularization with the SGD optimizer for the model Implementation. 

4. **Joel Karekezi Mugisha**  
   - **Email**: [j.mugisha@alustudent.com](mailto:a.ndayishim@alustudent.com)  
   
   - **Contribution**:  Mugisha worked on optimizing the model using both L1 and Regularization with the  RMSprop optimizer for the model Implementation. 


5. **Joel Karekezi Mugisha**  
   - **Email**: [j.umulisa@alustudent.com]
   
   - **Contribution**:  Jolly worked on optimizing the model using both L1 and Regularization with the  RMSprop optimizer for the model Implementation. 

#
## Outcome of Different Implementations in Summary

| Train Instance         | Engineer Name                    | Regularizer                  | Optimizer               | Early Stopping                        | Dropout Rate | Accuracy | F1 Score | Recall | Precision
----------------------|----------------------------------|------------------------------|-------------------------|----------------------------------------|--------------|----------|----------|--------|-----------
4                     | Favour Akinwande                 | L1 (0.0001)                  | SGD (lr=0.001)          | Yes (Patience=15, monitor=val_loss)    | 0.2 /0.2     |  0.736    | 0.498    | 0.426  | 0.498
5                     | Kanisa Rebecca Majok Thiak       | L2 (0.01)                    | SGD (lr=0.01)           | Yes (Patience=10, monitor=val_loss)    | 0.3 / 0.2    | 0.7027	   | 0.5185   | 0.4102 | 0.7047
6                     | Loue Sauveur Christian (lscblack)| L2 (0.001)                   | Adam (lr=0.0015)        | Yes (Patience=15, monitor=val_loss)    | 0.2          | 0.7027   | 0.5255   | 0.4219 | 0.6968
7                     | Jolly Umilisa                    | L1 (0.005)                   | RMSprop (lr=0.002)      | Yes (Patience=6, monitor=val_loss)     | 0.4          |  0.6789       |  0.373 | 0.2541   |  0.7015
8                     | Mugisha Karekezi Joel            | L1 + L2 (1e-4, 1e-3)         | RMSprop (lr=0.0008)     | Yes (Patience=15, monitor=val_loss)    | 0.3, 0.3          | 0.7012   | 0.5172   | 0.4102 | 0.7000


## 📊 Performance Analysis

### 🔹 Accuracy
**Favour Akinwande** achieved the highest overall **accuracy** at **73.6%**, indicating effective generalization across the dataset.  
The other models—**Loue**, **Kanisa**, and **Mugisha**—were very close, hovering around **70%**, showing good but slightly less consistent performance.  
**Jolly's model**, while slightly lower at **67.9%**, still managed respectable results given the challenges of class imbalance.

### 🔹 F1 Score
**Loue’s model** had the highest **F1 score (0.5255)**, followed closely by **Kanisa (0.5185)** and **Mugisha (0.5172)**, suggesting more balanced precision-recall trade-offs.  
**Favour’s model**, despite leading in accuracy, had a lower F1 score (**0.498**), which could reflect class imbalance.  
**Jolly's lower F1 score (0.373)** suggests difficulty in maintaining consistency across classes.

### 🔹 Precision & Recall
**Kanisa** and **Mugisha** demonstrated strong **precision** (~0.70), meaning they were good at avoiding false positives, especially in detecting class 0.  
**Favour** and **Jolly** had **lower recall**, indicating their models struggled more with detecting class 1 instances.  
**Loue’s model** had a good balance between **precision** and **recall**, reflected in the top F1 score.

---

## Insights from Each Model

###  Favour Akinwande
- Used **L1 regularization** with **SGD** at a learning rate of `0.001`.
- **Early stopping** patience of 15 allowed enough time to avoid underfitting.
- Achieved the **highest accuracy (73.6%)** 

###  Kanisa Rebecca Majok Thiak
- Used **L2 regularization** and **SGD** with a slightly aggressive learning rate of `0.01`.
- Performed best in **precision (0.7047)**, showing strong confidence in positive predictions.
- The **dual dropout rates (0.3/0.2)** helped control overfitting, though recall for class 1 could be improved.

###  Loue Sauveur Christian
- Combined **L2 regularization (0.001)** with the **Adam optimizer**, leveraging adaptive learning.
- Achieved the **best F1 score (0.5255)** with a well-balanced precision-recall profile.
- Learning rate of `0.0015` and **early stopping** ensured stable convergence with minimal overfitting.

###  Jolly Umilisa
- Used **L1 regularization (0.005)** and **RMSprop** with a relatively high **dropout rate (0.4)**.
- Achieved good **precision (0.7015)**, but **recall was very low (0.2541)**, leading to the lowest F1 score.
- The high dropout may have limited the model's learning capacity for minority class predictions.

###  Mugisha Karekezi Joel
- Combined **L1 + L2 regularization** with **RMSprop** at a learning rate of `0.0008`.
- Achieved **strong precision (0.7000)** and balanced **recall and F1 score**.
- Dual dropout (0.3, 0.3) helped maintain stable training, and regularization improved generalization.

---

##  Key Findings

- **Regularization** and **dropout** were critical in preventing overfitting.
- **Adam** and **RMSprop** optimizers generally outperformed **SGD** in terms of stability and overall accuracy.
- Most models performed better on **class 0**, indicating the need to address **class imbalance** via:
  - `class_weight` adjustments
  - **SMOTE** or **data resampling**
  - Custom **loss functions** or **focal loss**
- Models with **dropout rates around 0.2–0.3** and **early stopping patience of 10–15 epochs** showed the best trade-off between generalization and performance.

---


