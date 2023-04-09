## CloudFormation Template: S3 Bucket and Lambda Function

This CloudFormation template creates an S3 bucket and a Lambda function that is triggered by S3 events (ObjectCreated, ObjectRemoved, ObjectRestore, ObjectUpdate). The Lambda function puts a new item in a DynamoDB table based on the type of S3 event. The template also creates an IAM role for the Lambda function with the necessary permissions, a CloudWatch Logs group, and an alarm that is triggered when the Lambda function logs an error.

### Resources
- `MyS3Bucket`: An S3 bucket that triggers the Lambda function on events.
- `MyLambdaFunction`: A Lambda function that is triggered by S3 events and writes to a DynamoDB table.
- `MyLambdaExecutionRole`: An IAM role for the Lambda function.
- `MyLambdaLogGroup`: A CloudWatch Logs group for the Lambda function logs.
- `MyLambdaMetricFilter`: A CloudWatch Logs metric filter that counts the number of Lambda errors.
- `MySnsTopic`: An SNS topic that is notified when the Lambda function logs an error.
- `MyLambdaErrorAlarm`: A CloudWatch alarm that is triggered when the Lambda function logs an error.

### Usage
1. Deploy the CloudFormation stack using the AWS CLI or AWS CloudFormation console.
2. Upload files to the S3 bucket to trigger the Lambda function and log events.
3. View the DynamoDB table and CloudWatch Logs to see the events and logs.
4. Monitor the CloudWatch alarm for Lambda errors.

### Parameters
None

### Outputs
- `MyS3BucketName`: The name of the S3 bucket created by the CloudFormation stack.
- `MyLambdaFunctionName`: The name of the Lambda function created by the CloudFormation stack.
- `MyLambdaExecutionRoleArn`: The ARN of the IAM role created by the CloudFormation stack for the Lambda function.
- `MyLambdaLogGroupName`: The name of the CloudWatch Logs group created by the CloudFormation stack for the Lambda function.
- `MySnsTopicArn`: The ARN of the SNS topic created by the CloudFormation stack.
- `MyLambdaErrorAlarmArn`: The ARN of the CloudWatch alarm created by the CloudFormation stack.
