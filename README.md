# Water Quality Analysis 
This is a project our group, Peer Learning Group 6 worked on which focuses on using a model with TensorFlow/Keras for analyzing water quality data and predicting water quality. We predict the quality of water samples as either "Safe" or "Unsafe." Our model can generalize well on unseen data, thereby assisting in identifying potentially unsafe water samples.


## Group Structure and Task Allocation

This project was completed as part of a collaborative effort among five members of a peer learning group. The responsibilities were divided as follows:

### Team Members and Roles
1. **Loue Sauveur Christian**  
   - **Email**: [I.christian@alustudent.com]

2. **Favour Akinwande**  
   - **Email**: [f.akinwande@alustudent.com]

3. **Kanisa Rebecca Majok Thiak**  
   - **Email**: [K.thiak@alustudent.com]
     
4. **Joel Karekezi Mugisha**  
   - **Email**: [j.mugisha@alustudent.com]  

5. **Joel Karekezi Mugisha**  
   - **Email**: [j.umulisa@alustudent.com]
   
 #
## Outcome of Different Implementations in Summary

| Train Instance         | Engineer Name                    | Regularizer                  | Optimizer               | Early Stopping                        | Dropout Rate | Accuracy | F1 Score | Recall | Precision
----------------------|----------------------------------|------------------------------|-------------------------|----------------------------------------|--------------|----------|----------|--------|-----------
4                     | Favour Akinwande                 | L1 (0.0001)                  | SGD (lr=0.001)          | Yes (Patience=15, monitor=val_loss)    | 0.2 /0.2     |  0.6606    | 0.5751    | 0.6175 | 0.5381
5                     | Kanisa Rebecca Majok Thiak       | L2 (0.01)                    | SGD (lr=0.01)           | Yes (Patience=10, monitor=val_loss)    | 0.3 / 0.2    | 0.7027	   | 0.5185   | 0.4102 | 0.7047
6                     | Loue Sauveur Christian (lscblack)| L2 (0.001)                   | Adam (lr=0.0015)        | Yes (Patience=15, monitor=val_loss)    | 0.2          | 0.7027   | 0.5255   | 0.4219 | 0.6968
7                     | Jolly Umilisa                    | L1 (0.005)                   | RMSprop (lr=0.002)      | Yes (Patience=6, monitor=val_loss)     | 0.4          |  0.6789       |  0.373 | 0.2541   |  0.7015
8                     | Mugisha Karekezi Joel            | L1 + L2 (1e-4, 1e-3)         | RMSprop (lr=0.0008)     | Yes (Patience=15, monitor=val_loss)    | 0.3, 0.3          | 0.7012   | 0.5172   | 0.4102 | 0.7000


##  Performance Analysis

###  Accuracy
**Kanisa** and **Loue** achieved the highest **accuracy** scores of **70.27%**, indicating strong model generalization.  
**Mugisha** followed closely at **70.12%**, suggesting reliable training and evaluation consistency.  
**Favour's model** recorded an **accuracy** of **66.06%**, while **Jolly's** reached **67.89%**, both still reflecting reasonable performance, though with room for improvement in overall consistency.

### F1 Score
**Favour** had the highest **F1 score (0.5751)**, demonstrating the most balanced trade-off between **precision** and **recall**.  
This was followed by **Loue (0.5255)**, **Kanisa (0.5185)**, and **Mugisha (0.5172)**, each delivering stable performance across both classes.  
**Jolly’s model**, with an **F1 score of 0.373**, showed the greatest difficulty in balancing predictions, likely due to low **recall**.

### Precision & Recall
**Kanisa**, **Loue**, **Mugisha**, and **Jolly** all demonstrated strong **precision** (ranging between **0.6968 – 0.7047**), meaning they were effective at correctly identifying positive predictions for the majority class.  
**Favour** had a slightly lower **precision (0.5381)** but made up for it with the highest **recall (0.6175)**, meaning it correctly identified more actual positives — especially in class 1.  
**Jolly** struggled with **recall (0.2541)**, leading to weaker performance in identifying minority class instances.

##  Model Insights

###  Favour Akinwande  
**Regularizer**: L1 (0.0001)  
**Optimizer**: SGD (learning rate = 0.001)  
**Early Stopping**: Patience = 15, monitor = val_loss  
**Dropout Rate**: 0.2 / 0.2  

**Performance:**  
- **Accuracy**: 66.06%  
- **F1 Score**: 0.5751  
- **Recall**: 0.6175  
- **Precision**: 0.5381  

This model achieved the highest F1 score despite having a lower accuracy than others. The high recall indicates that it was more successful at identifying the minority class (class 1), which is often harder to detect. This performance makes Favour’s model particularly suitable for imbalanced datasets where false negatives are more costly.

### Kanisa Rebecca Majok Thiak  
**Regularizer**: L2 (0.01)  
**Optimizer**: SGD (learning rate = 0.01)  
**Early Stopping**: Patience = 10, monitor = val_loss  
**Dropout Rate**: 0.3 / 0.2  

**Performance:**  
- **Accuracy**: 70.27%  
- **F1 Score**: 0.5185  
- **Recall**: 0.4102  
- **Precision**: 0.7047  

Kanisa’s model had the highest precision, meaning it excelled at avoiding false positives. However, the relatively low recall shows that it struggled with identifying class 1 cases. A more balanced trade-off could be achieved by tuning dropout or addressing class imbalance.

### Loue Sauveur Christian (lscblack)  
**Regularizer**: L2 (0.001)  
**Optimizer**: Adam (learning rate = 0.0015)  
**Early Stopping**: Patience = 15, monitor = val_loss  
**Dropout Rate**: 0.2  

**Performance:**  
- **Accuracy**: 70.27%  
- **F1 Score**: 0.5255  
- **Recall**: 0.4219  
- **Precision**: 0.6968  

Loue’s model demonstrated the most balanced and consistent performance. With both high precision and relatively good recall, the model generalizes well and maintains fairness across classes. The use of the Adam optimizer seems to have helped in achieving stable and adaptive training.

###  Jolly Umilisa  
**Regularizer**: L1 (0.005)  
**Optimizer**: RMSprop (learning rate = 0.002)  
**Early Stopping**: Patience = 6, monitor = val_loss  
**Dropout Rate**: 0.4  

**Performance:**  
- **Accuracy**: 67.89%  
- **F1 Score**: 0.373  
- **Recall**: 0.2541  
- **Precision**: 0.7015  

Jolly’s model had excellent precision, suggesting it made few false positives. However, the recall was very low, which means many class 1 instances were missed. The high dropout (0.4) may have caused underfitting, restricting the model's ability to capture complex patterns in the minority class.

### Mugisha Karekezi Joel  
**Regularizer**: L1 + L2 (1e-4, 1e-3)  
**Optimizer**: RMSprop (learning rate = 0.0008)  
**Early Stopping**: Patience = 15, monitor = val_loss  
**Dropout Rate**: 0.3 / 0.3  

**Performance:**  
- **Accuracy**: 70.12%  
- **F1 Score**: 0.5172  
- **Recall**: 0.4102  
- **Precision**: 0.7000  

Mugisha’s model balanced all metrics well. It showed strong precision and acceptable recall, with stable training attributed to dual regularization and appropriate dropout. This configuration appears robust for imbalanced datasets.

---

##  Key Takeaways  
- **Favour**: Best for imbalanced data — top F1 and recall  
- **Loue**: Most consistent across all metrics  
- **Jolly**: Underfitting due to high dropout  
- **Kanisa** and **Mugisha**: High precision but recall needs improvement

---

##  Suggested Improvements

### Handle Class Imbalance  
- Use `class_weight='balanced'` during training  
- Apply **SMOTE** (Synthetic Minority Oversampling Technique)  
- Consider **focal loss** to emphasize learning from harder-to-classify cases  

### Regularization & Dropout Tuning  
- Avoid combining high dropout (e.g., 0.4) with strong L1 — this may underfit the model  
- Prefer **moderate dropout (0.2–0.3)** and **mild L2** regularization for stability  

### Optimizers  
- **Adam** and **RMSprop** provided more stable convergence than SGD  
- For **SGD**, tune momentum and/or use **learning rate scheduling**  

### Threshold Calibration  
- Lowering the default classification threshold (e.g., from `0.5` to `0.45`) can improve recall  
- Use **ROC curves** or **precision-recall trade-offs** to find the best threshold  


## Best Performing Model Summary

After evaluating five models based on their accuracy, F1 score, recall, and precision, we assessed their suitability for real-world use—particularly under class imbalance, where detecting the minority class (class 1) is crucial.

### Best for Imbalanced Data & High Recall: Favour Akinwande
F1 Score: 0.5751 (Highest)  
Recall: 0.6175 (Highest)  
Precision: 0.5381  
Accuracy: 66.06%

**Why Favour’s model is best:**  
This model demonstrated the strongest ability to identify class 1 instances, making it the most effective when false negatives are costly (e.g., missing at-risk water samples). The slightly lower accuracy is acceptable given the significantly better recall and F1 performance.

### Most Balanced Overall: Loue Sauveur Christian
F1 Score: 0.5255  
Recall: 0.4219  
Precision: 0.6968  
Accuracy: 70.27%

**Why Loue’s model is strong:**  
Loue’s model offers a consistent balance between precision and recall, with a higher overall accuracy. It’s well-suited for scenarios where both false positives and false negatives carry risk, and a general-purpose, stable model is preferred.

### Models with Trade-Offs

**Kanisa Rebecca Majok Thiak**  
Precision: 0.7047 (Highest)  
Recall: 0.4102  
Summary: Excellent at avoiding false positives, but likely to miss many true class 1 instances.

**Mugisha Karekezi Joel**  
Precision: 0.7000  
Recall: 0.4102  
Summary: Solid and stable, but recall could be improved to better serve imbalanced data use cases.

**Jolly Umilisa**  
Recall: 0.2541 (Lowest)  
Precision: 0.7015  
Summary: High precision but poor class 1 detection. Likely affected by excessive dropout causing underfitting.

### Final Recommendation

| Use Case                              | Recommended Model         | Justification                                                      |
|--------------------------------------|---------------------------|--------------------------------------------------------------------|
| Critical recall / Minority detection | Favour Akinwande          | Best F1 and recall — ideal for imbalanced datasets                 |
| Balanced performance                 | Loue Sauveur Christian    | Strong precision + recall + accuracy                               |
| Avoiding false positives             | Kanisa or Jolly           | High precision, but may miss important class 1 cases (low recall)  |
```


