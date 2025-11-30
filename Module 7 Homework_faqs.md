# FAQs for Module 7 Homework

## Q1. What is the main objective of the homework assignment?

The main objective is to build custom Vertex AI training and prediction
pipelines to predict the likelihood of patients developing breast cancer.

## Q2. What datasets are used in the training and prediction pipelines?

The training pipeline uses the file breast_cancer_train.csv and the prediction
pipeline uses breast_cancer_test.csv.

## Q3. What steps are involved in the training pipeline?

The training pipeline involves loading the dataset, splitting it into training
and validation partitions, normalizing the dataset, training a Logistic
regression model, and assessing the model's performance using accuracy and F1
score.

## Q4. What should be included in the submission for Gradescope?

The submission should include screenshots of the results pasted back into the
provided file, which should be uploaded as a PDF.

## Q5. What is required in Step 1 of the assignment?

In Step 1, you need to draw the directed acyclic graph (DAG) for your pipeline
design and label every arc while avoiding model leakage.

## Q6. What is the purpose of Step 5 in the assignment?

Step 5 involves creating a simple test pipeline to verify the overall pipeline
setup by defining a pipeline function and corresponding job with the same inputs
and outputs as the project.

## Q7. What should be done in Step 3 regarding Google Cloud Storage (GCS)?

In Step 3, you need to create a new bucket in GCS for the homework assignment
and load your training and validation datasets into this bucket.
