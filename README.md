<h1>Simple AWS CloudFormation Stack and Change Set</h1>
<h4>Description</h4>
 AWS CloudFormation simplifies the deployment of infrastructure and application stacks on Amazon Web Services (AWS) using a technique called Infrastructure as Code. By defining the desired resources in template files written in JSON or YAML, you can specify the architecture you want to build. AWS CloudFormation then automates the process, provisioning and managing the resources based on your templates, making deployment efficient and repeatable.

<h4>Sign into the AWS Console</h4>
-Create an account or sign in if you currently have an account. Use the N.Virginia region(us-east-1)

![us-east-1](https://github.com/user-attachments/assets/6c8540c8-1c03-48bd-be7f-8b9487ab2441)

-Search for cloudformation. click "create stack"
![create stack](https://github.com/user-attachments/assets/366f00a5-1ceb-4e0b-b3be-bfad6194b6c0)

-Select Choose existing template. We will upload a template file (EC2Instance YAML file [cloudformation-yml.zip](https://github.com/user-attachments/files/18191889/cloudformation-yml.zip)). The instanceID will need to be changed to the current version, and then save the file. You can locate the current ImageID version on the console dashboard (EC2>launch instance> Amazon Linux 2>ami#) 

![instanceID](https://github.com/user-attachments/assets/b760503d-6ed2-444f-869e-0ddb9d75964c)


![updated instanceID](https://github.com/user-attachments/assets/a37fcbf6-1918-4040-9397-86a00f6bd445)

-Now upload the EC2Instance file with the saved changes

![EC2 upload](https://github.com/user-attachments/assets/4b0f6a65-d97d-400f-903d-e76b8fff8ffa)

-Give stack a name (myInstancestack). click next. leave all the defaults. next. Scroll to the bottom. Click submit

![created stack](https://github.com/user-attachments/assets/91e895ec-f3e8-4a21-8364-632ba474c6e2)

-go to EC2 dashboard to see new instance and its public IP
![new instance](https://github.com/user-attachments/assets/ef5ff293-f9df-44b9-9490-6886d70c5dbb)

-set static IP on the instance using the EC2InstanceIP file![instanceIP](https://github.com/user-attachments/assets/4e7d24af-2f7e-41d8-8836-0a93d712072a)

<li>Type: AWS::EC2::EIP (the elastic IP/static IP)</li>
<li>InstanceId: !Ref MyInstance (connection between elastic IP and the instance)</li>

-now create a change set. go to stack actions> create change set for current stack>replace existing template> upload a template file

![upload new template](https://github.com/user-attachments/assets/f48e3abb-7989-4e4d-a645-74de094c4c55)

-Select next, next, next. submit. select Execute change set

![execute change set](https://github.com/user-attachments/assets/916cbcb5-571b-4fad-8de7-477279ab1d8f)

![execute change set2](https://github.com/user-attachments/assets/6d22e15f-68cd-41c8-a967-48e4176bcef5)

-Now to view the elastic IP. Dashboard> Network & Security> Elastic IPs

![new elastic IP](https://github.com/user-attachments/assets/6a4d2835-a569-4cc3-95d1-61a97eb280af)

-Next, we will create a stack using the EC2InstanceMappings file 

<li>InstanceMap (Regions) us-east-1, us-west-1</li>
<li>dev, and prod (the environments)</li>
<li>AMIMap (maps the AMI to the different Regions)</li>
<li>Resources: checks the existing Region. Then applies the ImageID and InstanceType based on that information</li>

![instance mapping](https://github.com/user-attachments/assets/8124b36a-5494-4222-a48b-884ed705b382)


-Create new stack in us-west-1 (N.California)

![us-west stack](https://github.com/user-attachments/assets/980af78a-258b-484a-afa9-cb80a8bddbc9)

-Select Choose an existing template, Upload a template file, choose file

![new stack2](https://github.com/user-attachments/assets/c57b8fd9-505d-4a35-8b8c-9658f52feb0f)

-View the new instance in us-west-1

![us-west instance](https://github.com/user-attachments/assets/1f69bb3f-8241-4aa8-83ac-59d694e1b4aa)

-now we can delete the stack, view and upload the EC2InstanceParameter file for a new stack

![delete stack](https://github.com/user-attachments/assets/75455c21-8af0-4d53-8692-aab42ee00cb1)

![instance parameters](https://github.com/user-attachments/assets/eee1d4d2-5e34-4bee-bd66-8bc7a51b4648)

![parameter stack](https://github.com/user-attachments/assets/fb979d4a-f82f-46e2-a58a-39c6aa8ba445)

-we can choose different options under Parameters

![parameter options](https://github.com/user-attachments/assets/00186414-0be7-42a2-ac4a-2c7dc7a9c171)

<li>now delete the last stack</li>

<h3>So this was just a simple walk-through for creating a CloudFormation stack and Change Set</h3>




