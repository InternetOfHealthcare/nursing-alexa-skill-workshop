![Nursing Icon](/images/aws-nursing-icon.png "Nursery Icon")
# AWS Alexa Nursing Skill Workshop

A set of e-health workshops to apply AWS technologies for health improving. During this workshop we will show how to develop a Nursing Skill for Alexa to ask about your health data and store into DynamoDB tables.

The conversation will be like this:

* You>> Open nursing skill
* Alexa>> Welcome to Alexa Nursing Skill, please tell me your name
* You>> My name is <<Your Name>>
* Alexa>> Welcome <<Your Name>>, you can ask me about your health
* You>> Blood Pressure Input
* Alexa>> What is your sistolic pressure <<Your Name>>
* My sistolic pressure is 115
* Alexa>> What is your diastolic pressure <<Your Name>>
* You>> My diastolic poressure is 75
* Alexa>> Thanks <<Your name>> 

![logo](/images/aws_new_logo.png)

## Introduction


You will learn how to build your own Alexa Skills that can be applied for e-health proposal by taking your health data. As example we provide a complete interaction to ask your name and also your blood pressure. But you will learn how to extend and create your own input interactions for:
- Glucose
- Emotional State
- Weight
- Blood Exam


## Table of Content

* [1. Create Alexa "Nursing Skill" using pre-configured Lambda](#1create-alexa-nursing-skill)
* [2. Create your own Lambda Function for Nursing Skill](#2create-your-own-lambda-function-to-your-alexa-skill)
* [3. Create your own DynamoDB table](#3create-your-own-dynamodb-table)
* [4. Customizing Nursing Skill](#4customizing-nursing-skill)



## 1.Create Alexa Nursing Skill

This first part you will learn how to create, configure and test a new Alexa Skill using a pre-existing Lambda function as back-end. After this step you will have your first Healthcare Skill working and then you can create your own Lambda function to customize or extend this skill to store different types of biometric data.

![logo](/images/alexa_skill.png)

### Step #1: Navigate to Alexa Developer Website: https://developer.amazon.com/alexa
![Nursing Icon](/images/alexa-skill/01.png) 

### Step 2: Click "Create your developer account" and fill the basic form
![Nursing Icon](/images/alexa-skill/02.png) 

### Step #2.1: Log using your created account 
![Nursing Icon](/images/alexa-skill/02.1.png) 

### Step #2.2: After login, click in "Your Alexa Consoles -> Skill" 
![Nursing Icon](/images/alexa-skill/02.2.png) 

### Step #2.3: You will be redirected to complete your account at developer.amazon.com
![Nursing Icon](/images/alexa-skill/02.3.png) 

### Step #2.4: Create your Alexa user at developer.amazon.com
![Nursing Icon](/images/alexa-skill/02.4.png) 

### Step #2.5: Accept the license
![Nursing Icon](/images/alexa-skill/02.5.png) 

### Step #2.6: Click "Save and continue"
![Nursing Icon](/images/alexa-skill/02.6.png) 

### Step #2.7: Click "Alexa" menu
![Nursing Icon](/images/alexa-skill/02.7.png) 

### Step #3: Navigate back to the Alexa Developer Webiste: https://developer.amazon.com/alexa and click in "Your Consoles Skills"
![Nursing Icon](/images/alexa-skill/03.png) 

### Step #4: Click "Add a new Skill" 
![Nursing Icon](/images/alexa-skill/04.png) 

### Step #5: Configure Skill Name with "Nursing Skill" and choose "Custom"
![Nursing Icon](/images/alexa-skill/05.png "instructions") 

### Step #6: Select "Start from the scratch" and click "Choose" 
![Nursing Icon](/images/alexa-skill/06.png "instructions") 

### Step #7: Now we need to complete some tasks to finish our skill as we can see on the right side "Skill Builder CheckList". The invocation name is the one used to open the Alexa Skill, ex. "Alexa Open nursing skill". By default, the invocation name is the Skill name but you can change it.
![Nursing Icon](/images/alexa-skill/07.png "instructions") 

### Step #8: The invocation name is the one used to open the Alexa Skill, ex. "Alexa Open nursing skill". By default, the invocation name is the Skill name but you can change it.
![Nursing Icon](/images/alexa-skill/08.png "instructions") 

### Step #9: Copy ![this json](/src/nursing-skill-conversation.json "json") configuration file and paste into code editor 
![Nursing Icon](/images/alexa-skill/09.png "instructions") 

### Step #9.1: Click "Save" & "Build Model"
![Nursing Icon](/images/alexa-skill/09.1.png "instructions") 


### Step #10: Click "EWndpoint" and choose "AWS Lambda ARN"
![Nursing Icon](/images/alexa-skill/10.png "instructions") 

### Step #11: Let's use our existing Lambda Function with this ARN. This ARN points to our Lambda in our account.
* Copy and paste this ARN-> arn:aws:lambda:us-east-1:977842192436:function:Nursing
![Nursing Icon](/images/alexa-skill/11.png "instructions") 

### Step #12: Time to test! Click "Go to Test Simulator"
![Nursing Icon](/images/alexa-skill/14.png "instructions")

### Step #15: Enable test for this skill
![Nursing Icon](/images/alexa-skill/15.png "instructions")

### Step #16: Click and hold the Mic icon to start a conversation

* You>> Open nursing skill
* Alexa>> Welcome to Alexa Nursing Skill, please tell me your name
* You>> My name is <<Your Name>>
* Alexa>> Welcome <<Your Name>>, you can ask me about your health
* You>> Blood Pressure Input
* Alexa>> What is your sistolic pressure <<Your Name>>
* My sistolic pressure is 115
* Alexa>> What is your diastolic pressure <<Your Name>>
* You>> My diastolic poressure is 75
* Alexa>> Thanks <<Your name>> 
# ![Nursing Icon](/images/alexa-skill/16.png "instructions")



### Step #8: Click "Save Model" and then "Build Model"
![Nursing Icon](/images/alexa-skill/08.png "instructions") 

### Step #9: Wait until finish..
![Nursing Icon](/images/alexa-skill/09.png "instructions") 



## 2.Create your own Lambda Function to your Alexa Skill

Now that we have our own skill using a pre-existing Lambda function that allows any skill to use it, you will learn how to create
your own lambda function copying our code and then replace the Lambda ARN in your Alexa Nursing Skill.

### Step #1: Create a new Lambda Function, click "Create Function"
![Nursing Icon](/images/alexa-lambda/01.png "instructions") 

### Step #2: Choose "Author from scratch"

* Name: NursingSkill
* Runtime: NodeJS 6.10
* Role: Custom Role
* It will open IAM console to create the role
# ![Nursing Icon](/images/alexa-lambda/02.png "instructions") 

### Step #3: Configure IAM role:

* IAM Role: lambda_basic_execution
* Policy Name: Create new Role Policy
* Click Allow

![Nursing Icon](/images/alexa-lambda/03.png "instructions") 

### Step #4: Configure the role in your function
![Nursing Icon](/images/alexa-lambda/04.png "instructions") 

### Step #5: Add Alexa Skill Kit trigger
![Nursing Icon](/images/alexa-lambda/05.png "instructions") 

### Step #6: Disable Skill ID verification

* This way any skill can use trigger this Lambda. If you want to restrict you can pick you Alexa Nursing Skill ID and limit the execution for only one skill. 

![Nursing Icon](/images/alexa-lambda/06.png "instructions") 

### Step #7: Copy ![this NodeJS code](/src/nursing-skill.js "js code") and paste into code editor 

![Nursing Icon](/images/alexa-lambda/07.png "instructions") 

### Step #8: Click "Save"
![Nursing Icon](/images/alexa-lambda/08.png "instructions") 

### Step #9: Now you can copy your own Lambda ARN to the clipboard
![Nursing Icon](/images/alexa-lambda/09.png "instructions") 

### Step #10: Open your Alexa Developer Console and click "Configuration"
![Nursing Icon](/images/alexa-lambda/10.png "instructions") 

### Step #11: Paste the new Lambda ARN
![Nursing Icon](/images/alexa-lambda/09.png "instructions") 

### Step #12: Before testing, we need to create your DynamoDB table!


## 3.Create your own DynamoDB table

To finish your Nursing Skill using youtr own Lambda Function you must create a DynamoDB table and 
make sure that Lambda Function has the right permissions.

### Step #1: Open DynamoDB Console
![Nursing Icon](/images/alexa-dynamo/01.png "instructions") 

### Step #2: Create healthdata Table

* Table Name: healthdata
* Primary key: id String
# ![Nursing Icon](/images/alexa-dynamo/02.png "instructions") 

### Step #3: Done!

![Nursing Icon](/images/alexa-dynamo/03.png "instructions") 

### Step #4: Open IAM console to allow your Lambda to access DynamoDB, click Roles and select lambda_basic_execution
![Nursing Icon](/images/alexa-dynamo/04.png "instructions") 

### Step #5: Select Policy and Click "Attach"
![Nursing Icon](/images/alexa-dynamo/05.png "instructions") 

### Step #6: Select AmazonDynamoDBFullAccess
![Nursing Icon](/images/alexa-dynamo/06.png "instructions") 

## 4.Customizing Nursing Skill

You can also create your own Alexa commands by adding new Intents and Utterances:

### An Intent is a set of utterances
![screenshot](/images/alexa-custom/01.png "instructions") 

### Utterances may have slots where you can use as variables...
![screenshot](/images/alexa-custom/01_.png "instructions") 

### A Lambda function will be called for each intent..
![screenshot](/images/alexa-custom/02.png "instructions") 

### For each intent we have a different call-back function...
![screenshot](/images/alexa-custom/03.png "instructions") 

### We can read the slot data this way:
![screenshot](/images/alexa-custom/04.png "instructions") 

### 
![screenshot](/images/alexa-custom/05.png "instructions") 

## You can try to extend you Alexa Nursing Skill by creating a new Intent and call-back function!
