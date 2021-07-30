# Eventlab v2 AWS CloudFormation templates

### Before deploy

- **Integrate AWS with GitHub**: Both frontend and backend pipelines use GitHub as a code source and require a CodeStar Connection with GitHub. [This guide](https://docs.aws.amazon.com/codepipeline/latest/userguide/connections-github.html) goes over the steps needed to authorize this;
- **Create the destination VPC and at least 1 subnet**: A few resources require use to specify a VPC;
- **Create CodePipeline artifact S3 bucket**: CodePipeline will automatically create a bucket for you when creating a pipeline. If you haven't created a pipeline yet, you need to create a S3 Bucket manually;


### Deploying

Deploy `backend.yml` first and wait for `LBDNSName` output to be generated. Since this projects does not use Route53, we need to manually specify what is the backend endpoint to out frontend stack.

The endpoint will be prompted in the parameters when deploying `frontend.yml`.