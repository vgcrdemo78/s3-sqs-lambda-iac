## S3 → SQS → Lambda (Async) – CloudFormation

### Architecture
S3 ObjectCreated → SQS → Lambda (with DLQ)

### Structure
- `main.yaml` – root stack
- `modules/` – reusable nested stacks
- `parameters/` – environment configs

### Deploy
```bash
aws cloudformation deploy \
  --template-file main.yaml \
  --stack-name s3-sqs-lambda-dev \
  --parameter-overrides file://parameters/dev.json \
  --capabilities CAPABILITY_NAMED_IAM
