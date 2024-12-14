<h1>Simple AWS CloudFormation Stack and Change Set</h1>
<h4>Description</h4>
 AWS CloudFormation simplifies the deployment of infrastructure and application stacks on Amazon Web Services (AWS) using a technique called Infrastructure as Code. By defining the desired resources in template files written in JSON or YAML, you can specify the architecture you want to build. AWS CloudFormation then automates the process, provisioning and managing the resources based on your templates, making deployment efficient and repeatable.

<h4>Sign into the AWS Console</h4>
-Create an account or sign in if you currently have an account. Use the N.Virginia region(us-east-1)

![us-east-1](https://github.com/user-attachments/assets/6c8540c8-1c03-48bd-be7f-8b9487ab2441)

-Search for cloudformation. click "create stack"
![create stack](https://github.com/user-attachments/assets/366f00a5-1ceb-4e0b-b3be-bfad6194b6c0)

-Select Choose existing template. We will upload a template file (EC2Instance YAML file). The instanceID will need to be changed to the current version, and then save the file. You can locate the current ImageID version on the console dashboard (EC2>launch instance> Amazon Linux 2>ami#)

![instanceID](https://github.com/user-attachments/assets/b760503d-6ed2-444f-869e-0ddb9d75964c)


![updated instanceID](https://github.com/user-attachments/assets/a37fcbf6-1918-4040-9397-86a00f6bd445)

![EC2 upload](https://github.com/user-attachments/assets/4b0f6a65-d97d-400f-903d-e76b8fff8ffa)

-Give stack a name (myInstancestack). click next. leave all the defaults. next. Scroll to the bottom. Click submit

![created stack](https://github.com/user-attachments/assets/91e895ec-f3e8-4a21-8364-632ba474c6e2)



