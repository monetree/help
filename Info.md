**Cloud Defense User Onboarding Cloudformation Stack:**

As part of Cloud Defense user onboarding AWS Cloudformation templates are executed on users aws account to create the below aws resources


- AWS VPC
    - Public Subnet 
    - Private Subnet
- AWS IAM Roles
    - CDCrossAccountRole
    - InternalRole
    - CDSCannerEnableInternalRole
- AWS Ec2 Server
- AWS Lambda Functions 
    - EnableCDAWSScanners
    - CDScannerLambda
    - CDScannerV2Lambda
    - CDDataProfilerLambda
- AWS Step Functions
    - CDStateMachine
- AWS KMS Key
- AWS SQS Queue
    - CDExportToS3Queue
    - CDDBSnapshotQueue
- AWS SNS Topic 
    - CDDBSnapshotSNSTopic
    - CDExportFileToS3SNSTopic 
    - CDAggregatorSNSTopic
    - CDRunDataProfilerSNSTopic
- AWS S3 Bucket

**AWS VPC**

VPC is used for provisining the CD scanner EC2 instance. This vpc includes the public and private subnets - CD Scanner Ec2 server downloads the libs/packages from internet for this purpose it needs public subnet. CD services uses the AWS SSM service to run command  on Scanner Ec2 remotely. 


**AWS IAM Roles**

CDCrossAccountRole
- This cross account role is assume by cloud defense side to access the cloudwatch logs and s3 lists etc. This role only having the read permission access for users resources.

InternalRole
- This role is internal to user aws account and not used outside. This role is attached to Scanner Lambda functions. These scanner lambda functions scans the resources in aws account and send the findings to event bus. This role having  readonly access to RDS, DynamoDB and redshift services and readwrire access to EC2, S3, SQS and cloudwatch. 
 
CDSCannerEnableInternalRole
- This role used by custom resource which enables the security hub, inspector2 and gaurdduty services on users account. To enable this it needs the access to users security hub, inspector2 and gaurdduty. This role is also limited to user aws account and not used outside it.

**AWS Ec2 Server**
- CD Scanner EC2 server used to scan the ebs volumes in users aws account. It takes the snapshot of exisitng ebs volume and create the new volumes to attach it to EC2 server. 

**AWS Lambda Functions** 

- EnableCDAWSScanners

This lambda functions enables the security hub, inspector2 and gaurdduty services for users account on all region as part of launch stack. It skips the already enabled services. On delete stack operation this lambda function rollback the services state. During rollback it skips those services which were already enabled before launch stack. 

- CDScannerLambda

This lambda function does the data discovery and classification for self managed datastore like - MySQL, MongoDB running on ec2. 

- CDScannerV2Lambda

This lambda function does the data discovery and classification for managed datastore like - RDS, DocumentDB etc. 

- CDDataProfilerLambda

This lambda function handels the managed data store classification

**AWS Step Functions**

- CDStateMachine

Starting point for managed and selfmanaged data store discovery and classifications. This defines the workflow for lambda function execution.

**AWS KMS Key**

This is used while exporting the RDS to S3 bucket.

**AWS SQS Queue**

- CDExportToS3Queue

This Queue is used for managed data store AWS RDS DB snapshot export 

- CDDBSnapshotQueue

This Queue is used for managed data store AWS RDS DB snapshot 

**AWS SNS Topic**

- CDDBSnapshotSNSTopic

AWS RDS DB Snapshot completion notification send to this Topic

- CDExportFileToS3SNSTopic 

AWS RDS DB Snapshot export completion notification send to this Topic

- CDAggregatorSNSTopic

CD Datascanner lambda function uses this for classification purpose.

- CDRunDataProfilerSNSTopic

Used for Cloud Defense data discovery and classifications

**AWS S3 Bucket**

AWS S3 bucket is used to store the RDS DB snapshot export and other classification results.

