![Nursing Icon](/images/aws-nursing-icon.png "Nursery Icon")
# AWS Alexa Nursing Skill Workshop

A set of e-health workshops to apply AWS technologies for health improving. During this workshop we will show how to develop a Nursing Skill for Alexa to ask about your health data and store into DynamoDB tables.

## Introduction
You will learn how to build your own Alexa Skills that can be applied for e-health proposal by taking your health data. As example we provide a complete interaction to ask your name and also your blood pressure. But you will learn how to extend and create your own input interactions for:
- Glucose
- Emotional State
- Weight
- Blood Exam

# ![Nursing Icon](/images/aws_new_logo.png "AWS Logo") 

## Links

### 1. Create Alexa "Nursing Skill" using pre-configured Lambda
### 2. Create your own DynamoDB database
### 3. Create your own Lambda Function for Nursing Skill
### 4. Extending Nursing Skill

## 1.Create Alexa "Nursing Skill" using pre-configured Lambda / DynamoDB

This first part you will learn how to create, configure and test a new Alexa Skill using a pre-existing Lambda function as back-end. After this step you will have your first Healthcare Skill working and then you can create your own Lambda function to customize or extend this skill to store different types of biometric data.

<<add an architecture overview>>

### Step #1: Navigate to Alexa Developer Website
# ![Nursing Icon](/images/alexa-skill/01.png "instructions") 

### Step #2: Enter the provided workshop credentials
# ![Nursing Icon](/images/alexa-skill/02.png "instructions") 

### Step #3: Click on "Alexa Skills Kit"
# ![Nursing Icon](/images/alexa-skill/03.png "instructions") 

### Step #4: Click on "Start a Skill" 
# ![Nursing Icon](/images/alexa-skill/04.png "instructions") 

### Step #5: Configure Skill Information
# ![Nursing Icon](/images/alexa-skill/05.png "instructions") 

### Step #6: Click on "Launch Skill Builder" 
# ![Nursing Icon](/images/alexa-skill/06.png "instructions") 

### Step #7: Copy ![this json](/src/nursing-skill-conversation.json "json") configuration file and paste into code editor 

# ![Nursing Icon](/images/alexa-skill/07.png "instructions") 

### Step #8: Click "Save Model" and then "Build Model"
# ![Nursing Icon](/images/alexa-skill/08.png "instructions") 

### Step #9: Wait until finish..
# ![Nursing Icon](/images/alexa-skill/09.png "instructions") 

### Step #10: Click "Configuration" to setup the Lambda Function
# ![Nursing Icon](/images/alexa-skill/10.png "instructions") 

### Step #11: We need to provide the Lambda Function ARN in Global Fields
# ![Nursing Icon](/images/alexa-skill/11.png "instructions") 

### Step #12: Let's use our existing Lambda Function with this ARN
# ![Nursing Icon](/images/alexa-skill/12.png "instructions") 

### Step #13: Your skill configuration should be like this:
# ![Nursing Icon](/images/alexa-skill/13.png "instructions")

### Step #14: Time to test! Click "Go to Test Simulator"
# ![Nursing Icon](/images/alexa-skill/14.png "instructions")

### Step #15: Enable test for this skill
# ![Nursing Icon](/images/alexa-skill/15.png "instructions")

### Step #16: Click in the Mic icon and start the conversation
# ![Nursing Icon](/images/alexa-skill/16.png "instructions")




