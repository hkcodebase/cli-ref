# CloudFormation CLI Commands

[Commands Reference 1](https://docs.aws.amazon.com/cli/latest/reference/cloudformation/)
[Commands Reference 2](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-using-cli.html)

[Login to AWS CLI - AWS Ref](https://docs.aws.amazon.com/signin/latest/userguide/command-line-sign-in.html)
[Login to AWS CLI Hands on](https://hkcodeblogs.medium.com/aws-cli-connect-to-aws-using-command-line-41925af062bd)

## CLI Commands
 - List stacks - The aws cloudformation list-stacks command enables you to get a list of any of the stacks you have created (even those which have been deleted up to 90 days)
    ```aws cloudformation list-stacks --stack-status-filter CREATE_COMPLETE```
 - Describe a list from above list 
    ```aws cloudformation describe-stacks --stack-name myteststack```
         ** check output and tags