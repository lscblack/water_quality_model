# Water Quality Analysis 
This is a project our group, Peer Learning Group 6 worked on which focuses on using an AI model with TensorFlow/Keras for analyzing water quality data and predicting water quality. We predict the quality of water samples as either "Safe" or "Unsafe." Our model can generalize well on unseen data, thereby assisting in identifying potentially unsafe water samples.


## Group Structure and Task Allocation

This project was completed as part of a collaborative effort among five members of a peer learning group. The responsibilities were divided as follows:

### Team Members and Roles
1. **Loue Sauveur Christian**  
   - **Email**: [I.christian@alustudent.com]
   - **Role**: Model Building & Implementation (L2 Regularization and Adam Optimizer)

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


### Final Recommendation
Based on the evaluation, the **L1 Regularization with SGD Optimizer** is recommended for deployment due to its superior performance in detecting unsafe water samples and overall model stability.
