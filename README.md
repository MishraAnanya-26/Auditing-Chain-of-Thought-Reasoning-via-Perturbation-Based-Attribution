# Auditing-Chain-of-Thought-Reasoning-via-Perturbation-Based-Attribution
While CoT prompting exposes intermediate reasoning steps, it fails to reveal whether these steps are logically grounded or not. We have built a novel perturbation-based attribution framework for auditing CoT reasoning. Our method identifies when models rely on spurious correlations or ignore critical input components.

## Starting Instructions
### 1. Use a GPU for attribution score generation as shown in the image before starting
2. <img src="attachment:2849edfa-2573-4158-971e-3893e18f7d41.png" width="500"/>
### 2. The first cell will clean Up the cache left from any previous runs
3. <img src="attachment:e46aa8b9-950d-4a25-943f-d0864085b2c2.png" width="500"/>
### 3. click OK and proceed

## Please ensure you have setup a huggingface token. The steps to set it up are shown below:
### 1. Sign in to Hugging Face and goto profile
1. <img src="attachment:bb449825-818e-4b32-866c-be69c8b5b5b3.png" width="800"/>
### 2. Next goto settings
2. <img src="attachment:e4d209cc-4092-421b-8008-4bb51c1520f0.png" width="500"/>
### 3. Now create a new token as shown
3. <img src="attachment:36e018ee-2ecf-4276-911f-266f68481b1b.png" width="600"/>
### 4. Add the token to secrets section in this notebook as shown below
4. <img src="attachment:029e56af-37c8-460c-bfb4-cacc2e5003ab.png" width="700"/>
### We need it for access to the Deepseek Math Model and GSM8K dataset

## Saving the intermediate results
1. `output_csv_path = '/kaggle/working/pre_ground_truth_46to50.csv'`: This step will trigger save the intermediate results in the form of a csv
2. You can find the saved file by following the instructions below:
3. Click the leftward arrow at the bottom right to open the side bar
4. <img src="attachment:06d43548-29f7-4d77-8d95-863bc3dc8cdd.png" />
5. Hit the refresh to load the latest updates
6. <img src="attachment:64e48aad-c71e-48e3-b10d-03c4ad0b2926.png"  width="500"/>

## Ground Truth Needs to be Supplied Externally
### 1. Download the pre_ground_truth_46to50.csv file
### 2. Use it to create the human annotated ground truth from it by matching every step with top three relevant phrases
### 3. The column headings for it are: Step, Matched Phrases, Question (please refer sample files in the exp_data to understand better)
### 4. Then upload the file named as per the following naming convention: ground_truth_46to50.csv as a dataset as follows:
 5. <img src="attachment:14622f73-05af-4504-9c0d-d20dc4572e01.png" width="500"/>
### 5. Drag and drop the ground truth file and name the dataset same as the file for simplicity
6. <img src="attachment:97abf09e-3b2d-4dc9-8e01-7d6c7736ecdf.png" width="500"/>
### 6. Interpretting Results
The resultant vector has number of steps per question marked as unfaithful

## Visualization of Results
1. Results_of_ignored_steps.csv is populated manually after each 5 question run
2. Sample file for the same is present in the exp_data folder
3. The results are to be uploaded as another dataset called "results-for-graph" with filename "results_of_ignored_steps.csv"
