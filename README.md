## GTEx-Nextflow-RNASeq-Pipeline


#### Step 1: Configuring the AWS-CLI
&ensp; 1. Login to your AWS Account.  \
&ensp; 2. Go to AWS IAM (Identity and Access Management) Service. \
&ensp; 3. Security Credentials > Create access key > Use Case - Command Line Interface CLI \
&ensp; 4. Select the Next Option and Type a Description for your Key. For Example: gtex_pipeline \
&ensp; 5. You Now Have an Access Key ID and a Secret Access key that we will use to configure AWS. Download .csv file. \
&ensp; 6. Open Ubuntu Terminal and run the following commands: \
&emsp; &ensp; 	**sudo apt-get update**        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; # update packages \
&emsp; &ensp;   **sudo apt install awscli**    &nbsp;&nbsp;&nbsp;&nbsp; # install aws command line interface \
&emsp; &ensp;   **aws configure**              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; # configure settings that aws-cli will use to interact with aws  \
&emsp; &ensp;  Type in your Access Key ID, Secret Access Key, Default Region Name (us-east-1), Default output format (json, text or table) \
&ensp; 7. You have successfully configured your AWS-CLI to AWS. To verify your configuration run: \
&emsp; &ensp;   **aws configure list** \
&ensp; 8. To test the configuration you can run a simple commnd to list your S3 Buckets: \
&emsp; &ensp;   **aws s3 ls**

#### Step 2: Incorporating Docker File to AWS Batch 
&ensp; 1. Open Ubuntu and run the following commands: \
&emsp; &ensp; **docker image build -t gtex_pipeline/primary:1.0 .**    &emsp; # building an image. { docker image build -t <\ tag-name>\ . } \
&emsp; &ensp; The last period (.) means the Dockerfile is present in the current directory. \
&emsp; &ensp; Message: -- Successfully built db7d00a0bbea. This baseID can be used to access the Docker image instead of using its name tag. \
&emsp; &ensp; **docker image ls**    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; # verify your image \
&ensp; 2. Try running your docker image in your local system \
&emsp; &ensp; **docker run -p 8000:8000 gtex_pipeline/primary:1.0** \
&ensp; 3. Push this image to a container resgistry. Here we use Amazon Elastic Container Service (ECS)\


