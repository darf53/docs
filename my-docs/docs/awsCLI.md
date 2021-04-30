# Tips and tricks for using the AWS cli

## Environment

- `export AWS_PROFILE` to avoid having to add --profile to every command

## Query and parse the output from aws

Examples:

- List stacks with a specific status:

```
aws cloudformation list-stacks --query "StackSummaries[?StackStatus!='DELETE_COMPLETE'].[StackName,StackId,StackStatus]" --region eu-central-1
```

- List policies with a specific tag

```
aws organizations list-policies --filter TAG_POLICY --query "Policies[?Name='A-mandatory-tags'].[Id]"
```

- Query a stack for a specific output value

```
aws cloudformation describe-stacks --stack-name shared-devenvironment-vpc-stack --query "Stacks[].Outputs[?OutputKey=='PrivateSubnet1'].[OutputValue]" --output text
```

- Query organization to get specific some values

```
aws organizations list-accounts --query "Accounts[].[Name,Id,Email]" --output table
```

## Create and deploy using cloudformation

Examples:

```
aws cloudformation update-stack --stack-name ITU-CTSetup-shared-VPC-qa --template-body file://vpctemplate.yml --parameters file://ITU-lz-vpc-qa-eu-central-1.json --region eu-central-1
aws cloudformation create-stack-set \
	--stack-set-name ITU-CTSetup-guarddutyNotifications \
	--template-body file://guardduty-notifications.yml \
	--region eu-west-1 \
	--execution-role-name AWSControlTowerExecution
	--administration-role-arn "arn:aws:iam::185563819092:role/service-role/AWSControlTowerStackSetRole"
```
