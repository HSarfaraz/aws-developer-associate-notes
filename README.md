## AWS Developer Associate Notes


<br/>
<hr/>
<br/>

### Day 1:
-  Sign using specific id
-  For document ➜ click on 'Student guide' tab button
-  Now click to python ➜ click launch
-  Go to 'Vital source' ➜ enter spcific id ➜ continue without an account link ➜ we will get the ebook format

#### Start Lab
-  Go to 0 ➜ go to cloud9 console
-  Go to 1 ➜ In cloud9 ➜ click on green plus icon (+)
-  It will open the terminal window, type the following command
    ```python
      python --version
      //To check AWS is installed or not
      aws --version
    ```  
-  Go to preference: AWS Setting ➜ credentails ➜ disable the button ➜ close the tab
-  Step 9: to configure the I am credentials
    ```python    
      aws configure
      //➜ enter ➜ enter ➜ paste the region code here 'eu-east-2' in AWS console ➜ type 'yaml' ➜ enter
    ```  
-  Now we are runnning CLI Command for making API Call
      
    ```python      
      //Telling what identity I am using
      aws sts get-caller-identity
    ```  
  -  AWS tool kit will help to access it.
  -  Go to AWS tool kit ➜ connect to AWS ➜ profile ➜ see 'US EAST ..' ➜ We can see S3 bucket
  -  Task 2: Basically to review the tool kit.
  -  Task 3: We will run the commands ➜ see that happens
  ```python
    aws s3 ls: To show s3 bucket
    bucketToDelete= $(aws s3api list-buckets --output text --query 'Buckets[?contains(Name,`deletemebucket`) == `true`] | [0].Name')
    //Task 3.2: Remove the bucket
    aws rb s3://$bucketToDelete
    aws rb s3://$bucketToDelete --debug
  ```
  -  We will get the error saying developer role can have access to delete the bucket, so get the access
  -  Step 18: use arn command to see the policy, what is the policy we are using as a developer, This is a policy documnet, which allow s3 to delete bucket.
  -  Step 20: need to attach the policy, here choice 'a' is the right
  ```python
    aws iam attach-role-policy --policy-arn $policyArn --role-name notes-application-role
    //Now we can remove the bucket
    aws rb s3://$bucketToDelete
  ```  
  -  End the lab ➜ signout from AWS console.

<br/>
<hr/>
<br/>
