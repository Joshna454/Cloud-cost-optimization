# Cloud-cost-optimization

Cloud computing offers tremendous flexibility, scalability, and the ability to innovate quickly. However, as organizations migrate more workloads to the cloud, costs can spiral out of control if not managed effectively. Cloud cost optimization involves implementing strategies to reduce unnecessary spending while ensuring performance and reliability are maintained.

# Snapshots

A snapshot in the context of cloud computing, particularly AWS (Amazon Web Services), is a point-in-time backup of a storage volume, such as an EBS (Elastic Block Store) volume. 

In this example,we'll create a Lambda function that identifies EBS (Elastic Block Store) snapshots no longer associated with any active EC2 instance and deletes them to save on storage costs. This Lambda function can be scheduled to run at regular intervals using Amazon EventBridge.

first we create an ec2 inastance by default, EC2 will have a root volume attached.In the EC2 Dashboard, click on Snapshots under the Elastic Block Store (EBS) section on the left panel.Create a Snapshots and attach the volume to it.Now we create Lambda function with an IAM role attached to it.THe IAM role should have the following permissions.EC2: DescribeInstances, DescribeVolumes EBS: DescribeSnapshots, DeleteSnapshot,AWSLambdaBasicExecutionRole.
     Then we run the program(lanbda_test.py) in the Lambda function.After a successfull execution the program the lambda function will  automatically identify and delete orphaned EBS snapshots, reducing storage costs.If the instance is delted the lambda function will also delete the attached snapshots to reduce costs.


# LAMBDA 
AWS Lambda is a serverless computing service that allows you to run code in response to events without provisioning or managing servers.With AWS Lambda, you only pay for the compute time used when your code is executed. If your function doesn’t run, you don’t incur any charges. Lambda supports several programming languages, including:Python,Node.js (JavaScript),Java,Go,Ruby.Lambda integrates with AWS IAM (Identity and Access Management), which lets you control what actions a function is allowed to take (e.g., permissions to delete EBS snapshots or describe EC2 instances).
