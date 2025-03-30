# Equitable AI for Dermatology - AJL Kaggle Competition

---

### **👥 Team Members**

| Name | GitHub Handle | Contribution |
| ----- | ----- | ----- |
| Noam Riner | @noamreiner17 | Team Captain. Managed team communication and progress tracking. Contributed to README updates, setting up the initial model and model accuracy improvements. |
| Adriana Rincon | @adririncon | Created group documentation, contributed to README updates, and model exploration/accuracy |
| Henok Misgina Fisseha | @Henok-Foslyk | Worked on model exploration and data preprocessing. Focused on improving model accuracy. |
| Mina Yang | @mintudse | Focused on data exploration and preprocessing; contributed to README updates and model accuracy improvements. |
| Tushar Koushik | @tusssars11 | Worked on model exploration, data preprocessing, and README documentation. Focused on improving model accuracy through various model trial and error processes to identify the most suitable architecture for the data. Additionally, applied techniques like data augmentation, class weighting, and hyperparameter tuning to enhance model performance and ensure fairness across skin tones.|

---

## **🎯 Project Highlights**

**Example:**

* Built a ResNet model using techniques such as data augmentation, class weighting, weighted random sampling, and gradient accumulation to solve the Equitable AI for Dermatology Kaggle Competition.
* Achieved an F1 score of .6875 and a ranking of 10th on the final Kaggle Leaderboard
* We utilized the classification_report from sklearn to provide detailed insights into the model’s performance. This report displays the precision, recall and F1-score for each class label, enabling us to understand how well the model performed in classifying different skin condition categories. This helped with the interpretation of model decisions and to identify potential areas for improvement.
* To optimize results within compute constraints we used gradient accumulation, updating model weights every 2 batches, to effectively increase batch size. We also used weighted random sampling to counter the issue of imbalance data. This helped ensure the model was not overtrained on larger classes within the dataset. 


🔗 [Equitable AI for Dermatology | Kaggle Competition Page](https://www.kaggle.com/competitions/bttai-ajl-2025/overview)

---

## **👩🏽‍💻 Setup & Execution**

**Provide step-by-step instructions so someone else can run your code and reproduce your results. Depending on your setup, include:**

* How to clone the repository

```bash
git clone <repository-url>
cd <repository-name>
```

* How to install dependencies

Ensure you have Python installed (preferably version 3.x).

* How to set up the environment

Make sure you have Jupyter Notebook installed:

```bash
pip install notebook
```

Then, launch Jupyter Notebook:

```bash
jupyter notebook
```

* How to access the dataset(s)
Download the dataset from the following link:
[Google Drive Dataset](https://drive.google.com/drive/folders/15nmm2SjiTsMzqnO-gXLttlXaFniwxxil?usp=drive_link)

Save the dataset files to the appropriate location within the project directory. Update the notebook/script with the correct file path if necessary.

* How to run the notebook or scripts

Ensure both the Jupyter Notebook and dataset are in the correct directory. Open the notebook and adjust the dataset path if needed. Then, run the notebook step by step to reproduce the results.




---

## **🏗️ Project Overview**

Equitable AI for Dermatology

 We now live in a world where AI governs access to information, opportunity and freedom. However, AI systems can perpetuate racism, sexism, ableism, and other harmful forms of discrimination, therefore, presenting significant threats to our society - from healthcare, to economic opportunity, to our criminal justice system.

The Algorithmic Justice League is an organization that combines art and research to illuminate the social implications and harms of artificial intelligence.

AJL’s mission is to raise public awareness about the impacts of AI, equip advocates with resources to bolster campaigns, build the voice and choice of the most impacted communities, and galvanize researchers, policymakers, and industry practitioners to prevent AI harms.

AI is transforming healthcare, yet dermatology AI tools often underperform for people with darker skin tones due to a lack of diverse training data. This can lead to diagnostic errors, delayed treatments, and health disparities for underserved communities.

This challenge from Break Through Tech and the Algorithmic Justice League invites you to help address this issue by building an inclusive machine learning model for dermatology.

---

## **📊 Data Exploration**
Dataset

* This dataset is a 4,500-image subset of FitzPatrick17k, which labels dermatological conditions across skin tones using the FitzPatrick Skin Type (FST) scale. It includes 21 conditions from the full set of 100+, balancing a manageable classification task with key representation challenges.

Data exploration and preprocessing approaches

* We explored the data by visualizing any class imbalances and missing values, which informed our data preprocessing approach. There were no missing values except in the ‘qc’ column (around 97% were null values), which was handled by removing the column. In terms of class distribution, squamous cell carcinoma was the most represented in our dataset, while basal cell carcinoma morpheiform was the least common. Overall, there is a class imbalance in our distribution, which could cause bias in our model training. Some approaches to tackle this issue are sampling more of the minority classes, or adding weights to them during training.

Challenges and assumptions when working with the dataset

* One challenge was that it was the first time working with image classification for many of us, so understanding image data was one of the first steps we had to take. Another challenge was addressing class imbalance within the data, which would affect our model training and results. During this process, another one of our goals was to be able to train a model that could predict well on varying skin types. This proved to be a challenge as we evaluated our model, so we had to tune our model for accuracy and bias.

Here is a visualization of the class distribution of the dataset:
![classdistribution](https://github.com/user-attachments/assets/fed61f33-096e-4a2c-96fe-d2107b277de6)

---

## **🧠 Model Development**

**Describe (as applicable):**

* Model(s) used: ResNet 50 (CNN) with transfer learning to leverage pre-trained weights for improved performance. 
* Feature selection and Hyperparameter tuning strategies: Used images provided and pre-processed them (resized, normalization, and data augmentation). Implemented a learning rate scheduler to adapt during training. Also used the AdamW optimizer for better regularization. 
* Training setup (e.g., % of data for training/validation, evaluation metric, baseline performance): Used provided training data sets to train the model with a batch size of 32. Utilized 50 epochs. 


---

## **📈 Results & Key Findings**

**Describe (as applicable):**

* Performance metrics (e.g., Kaggle Leaderboard score, F1-score): 20th on leaderboard. Received a score of  0.47753 on the leaderboard
* How your model performed overall: Our overall model accuracy was 92.24%, with an average precision score of .93, recall score of .97, and f1 score of .92 across the different skin conditions.
* Currently working on improving our preformance. 

**NEED TO FILL**
* How your model performed across different skin tones (AJL)
* Our model performed well on lighter skin tones (FST 1-3) with higher accuracy, precision, and recall. However, for darker skin tones (FST 4-6), we observed a drop in accuracy and precision, leading to more false positives. This disparity highlights the need for additional data augmentation and class balancing to improve equitable performance.


* Insights from evaluating model fairness (AJL)
* 
* The confusion matrix showed higher misclassification rates for darker skin tones, especially for less common conditions. Precision-recall curves indicated that the model often overpredicted certain conditions for darker skin tones. Applying fairness-aware metrics and explainability tools suggested the need for further bias mitigation strategies to ensure equitable predictions.
* 
---

## **🖼️ Impact Narrative**

**Answer the relevant questions below based on your competition:**

**AJL challenge:**

As Dr. Randi mentioned in her challenge overview, “Through poetry, art, and storytelling, you can reach others who might not know enough to understand what’s happening with the machine learning model or data visualizations, but might still be heavily impacted by this kind of work.”
As you answer the questions below, consider using not only text, but also illustrations, annotated visualizations, poetry, or other creative techniques to make your work accessible to a wider audience.
Check out [this guide](https://drive.google.com/file/d/1kYKaVNR\_l7Abx2kebs3AdDi6TlPviC3q/view) from the Algorithmic Justice League for inspiration!

1. What steps did you take to address [model fairness](https://haas.berkeley.edu/wp-content/uploads/What-is-fairness_-EGAL2.pdf)? (e.g., leveraging data augmentation techniques to account for training dataset imbalances; using a validation set to assess model performance across different skin tones)

   To address model fairness, we applied weighted random sampling to ensure balanced representation across skin tones during training. Data augmentation techniques such as flipping,
   rotation, and brightness adjustments were used to improve the model’s robustness and reduce bias. Additionally, we used class weighting to minimize the impact of underrepresented
   skin tones, and evaluated model performance using fairness metrics across different Fitzpatrick Skin Types (FST).


2. What broader impact could your work have?
   Our work contributes to reducing diagnostic biases in dermatology AI systems, potentially leading to more equitable healthcare outcomes. By improving model performance for darker 
   skin tones, we help mitigate the risk of misdiagnosis and delayed treatments for underrepresented populations. Additionally, this project can serve as a framework for develop in 
   fair AI models in other medical fields, promoting responsible AI use in healthcare.

   

---

## **🚀 Next Steps & Future Improvements**

**Address the following:**

* What are some of the limitations of your model?
Limitations could include the reliance of the single pre-trained model used. Also, even using class weights, the model’s performance is heavily dependent on the quality and diversity of the training data we were provided. 

* What would you do differently with more time/resources?
If we had better processes, we would adjust the model parameters (such as increasing the number of epochs) and/or increase the amount of data processed to improve predictions. We would like to explore more model options in order to improve prediction. Have a better understanding of how different skin types affect the prediction. 



* What additional datasets or techniques would you explore? 

Conduct a more detailed analysis of fairness.

Experiment with additional data augmentation techniques. Train on a super computer with different techniques.

Collaborate with dermatologists for expert validation.



## **📄 References & Additional Resources**

Algorithmic Justice League

FitzPatrick17k Dataset

ResNet-50

---

