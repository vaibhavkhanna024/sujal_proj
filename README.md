# CI-CDUsingJenkinsForMuleApplication


# Project Description

It is a simple Project Of Getting Flights Data and inerting into salesforce Flights Custom object.It contains a simple Munit suite too.
I have created this project to Build CI/CD Pipeline using Jenkins. There is a Jenkins File Attached into the project.
Which is used to build the CI/CD Pipeline. This Project is based on mule 4.3.0

# Features Of The CI/CD

It will never disclose your personal data like salesforce creds, Key used to Encrypt or decrypt.Even when you are using Jenkins .It will be
safe.

I have also implemented Continious Testing. So when the code coverage is less than 75 % then the build will automatically fails.

Build and Test are included on the same.You don't need to explicitly test it. It will automatically test when you will be building the project.

This CI/CD Pipeline will automatically Hit the API also. You don't need to go to the Postman and hit it.

# Challenges Faced

Major Challenge was how to manage Environment variables in Jenkins.

Run and test Environment both require the environment variable to build.

I have added Environment Variables to both the plugin(Test and Run).

By Default mule4 uses version 1 of object store, But this is not allowed in mule4, 
so i need to add one objectStorev2 tag inside the cloudHubDeployment tag.


