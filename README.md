[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/_IojtdoU)
# StackIt Hiring Assignment

### Welcome to StackIt's hiring assignment! 🚀

**If you didn't get here through github classroom, are you sure you're supposed to be here? 🤨**


We are glad to have you here, but before you read what you're going to beat your head over for the next few hours (maybe days?), let's get a few things straight:
- We really appreciate honesty. Don't copy anyone else's assignment, it'll only sabotage your chances :P
- You're free to use any stack, and library of your choice. Use whatever you can get your hands on, on the internet!
- We love out of the box solutions. We prefer to call it *Jugaad* 
- This might be just the first round, but carries the most importance of all. Give your best, and we hope you have a fun time solving this problem.

## ✨ **Problem Statement: Crafting a CSV Importer for Google Sheets** ✨

**Context**:
Data analysts around the world 🌍, handle massive amounts of data to derive meaningful insights for their organization 📊. Among the tools they use, Google Sheets 📈 stands out due to its ease of use, accessibility, and collaborative features. However, many analysts have identified a recurring pain point: the cumbersome process of importing CSV files into Google Sheets repeatedly.

A typical week of an analyst in an e-commerce company 🛒 involves receiving multiple CSV files 📁 containing sales, inventory, customer feedback, and more. The data from these files needs to be meticulously analyzed and presented in the company’s weekly meetings. However, instead of diving directly into analysis, most analysts need to spend an inordinate amount of time just importing and structuring these CSV files into Google Sheets ⏳. This repetitive, time-consuming task reduces the efficiency of these professionals and delays the extraction of crucial insights 😫.

**Today, you are going to make their lives better.**

**Problem Statement**:
Make a CSV Importer for Google Sheets that lets users drag and drop CSV files onto the Google Sheet. The moment they drop the CSV file, allow them to select which columns to import 🗂️.

You get brownie points 🍪 if you can make it even easier by allowing them to filter the data as well before importing it into Google Sheets 🔍.

**Other pointers**:
- Import to Sheet – After validation and mapping, devise a method to populate the data into a chosen Google Sheet, either appending to existing data or creating a new sheet 📥📋.
- Optimize for Large Files – Large datasets are common in analytics. Your solution should effectively handle large CSV files (~15MB CSV file) without causing performance issues or prolonged waiting times 📈📦.

## Submission ⏰
The timeline for this submission is: **9AM, 30th Sept, 2023 - 12PM, 2nd Oct, 2023**

Some things you might want to take care of:
- Make use of git and commit your steps!
- Use good coding practices.
- Write beautiful and readable code. Well-written code is nothing less than a work of art.
- Use semantic variable naming.
- Your code should be organized well in files and folders which is easy to figure out.
- If there is something happening in your code that is not very intuitive, add some comments.
- Add to this README at the bottom explaining your approach (brownie points 😋)

Make sure you finish the assignment a little earlier than this so you have time to make any final changes.

Once you're done, make sure you **record a video** showing your project working. The video should **NOT** be longer than 120 seconds. While you record the video, tell us about your biggest blocker, and how you overcame it! Don't be shy, talk us through, we'd love that.

We have a checklist at the bottom of this README file, which you should update as your progress with your assignment. It will help us evaluate your project.

- [ ] My code's working just fine! 🥳
- [ ] I have recorded a video showing it working and embedded it in the README ▶️
- [ ] I have tested all the normal working cases 😎
- [ ] I have even solved some edge cases (brownie points) 💪
- [ ] I added my very planned-out approach to the problem at the end of this README 📜

## Got Questions❓
Feel free to check the discussions tab, you might get something of help there. Check out that tab before reaching out to us. Also, did you know, the internet is a great place to explore 😛

## Developer's Section
### Demo video drive link
- Link : https://drive.google.com/file/d/1Q2ghdXd6lCMHKFXaLhjZT4ofsEv0JFid/view?usp=sharing
## CSV File Preprocessor and Uploader

This Python script provides a web-based interface for uploading CSV files, performing data preprocessing, and updating a Google Sheet with the preprocessed data. It utilizes the Streamlit library for creating the web app and various data preprocessing techniques from scikit-learn.

### Libraries Used

- `sys`: Access system-specific parameters and functions.
- `streamlit`: Create the web application.
- `os`: Interact with the operating system.
- `sklearn.preprocessing`: Perform data preprocessing tasks.
- `google.auth.transport.requests`: Handle authentication requests.
- `google.oauth2.credentials.Credentials`: Manage Google OAuth2 credentials.
- `google_auth_oauthlib.flow.InstalledAppFlow`: Perform OAuth2 flow for installed applications.
- `googleapiclient.discovery.build`: Create a Google Sheets service client.
- `googleapiclient.errors.HttpError`: Handle HTTP errors.
- `pandas`: Manipulate and read CSV data.
- `numpy`: Perform numerical operations.

### `preprocess_data` Function

This function takes an input DataFrame, processes it based on user-defined parameters, and returns a preprocessed DataFrame. Key steps:

- Drop specified columns from the DataFrame.
- Remove duplicate rows.
- Split the DataFrame into two parts: columns not to be transformed and columns to be transformed.
- Fill missing values in numerical columns based on the chosen strategy.
- Scale numerical columns based on the selected scaling method.
- Encode categorical columns based on the chosen encoding method.
- Re-add the columns that were not transformed back into the preprocessed DataFrame.

### `main` Function
This function sets up the Streamlit web application and handles the main workflow:
  - We first create a file uploader widget in the web app, allowing the user to upload a CSV file.
  - Then we  create a text input field for the user to enter a Google Sheet ID  
  - Then the next few lines create interactive widgets for the user to select columns to drop, columns to not transform, fillna strategy, scaler choice, and encoder choice
- The next section handles Google Sheets authentication. It checks if there's a token file and if not, it initiates the OAuth2 flow to obtain credentials. The credentials are stored in a token file for future use.  
- The next lines build a Google Sheets API service client and attempt to fetch values from the specified Google Sheet.
- Then we clear the existing data to upload the new data
- Then we update the Google Sheet with the preprocessed data and display a success message.
### How to Use

1. Run the script using the cmd by typing streamlit run name_of_file.py.
2. Upload a CSV file.
3. Select preprocessing options.
4. View the preprocessed data in the web app.
5. Enter the Google Sheet ID and update the Google Sheet with the processed data.
6. Finally after this you can see your preprocessed file uploaded to the Google sheet

This script provides an efficient way to preprocess and upload CSV data to Google Sheets for further analysis.

