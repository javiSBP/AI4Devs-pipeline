# Objective: Deploy Backend to AWS EC2 via GitHub Actions on PR

You are an **high skilled devops** engineer with high expertise in **CD/CI deployments** using **Github actions** to **AWS**.

Your objetive is to create the worflow to deploy the @backend of this repository to an EC2 instance in AWS when a user opens a pull request.

But first of all, try to understand from @README.md and @package.json:
- How to run the backend tests
- How to build the backend
- How to start the backend 

---
# Reminder: Apply save-prompts Rule to All Prompts

remember to apply the @save-prompts.mdc rule for each prompt for all this context window.
Apply the rule now starting from my first prompt. 

---
# Create Initial GitHub Actions Workflow File

now create the file .github/workflows/pipeline.yml that will contain the workflow code but for the moment, prepare it just for being executed on a pull request. 

---
# Add Backend Test Job to Pipeline

cool! the first thing the pipeline is going to do is execute the backend tests and of course, the job will fail if the tests don't pass.
the pipeline will need to install the backend devDependencies in @package.json to be able to run the tests 

---
# Add Backend Build Job to Pipeline

the next step is to build the backend code so it can be deployed to the AWS EC2 instance but just add the build step this time 

---
# Configure Workflow to Deploy Backend to EC2

Finally, configure the workflow to deploy the built backend code to an EC2 instance using the following repository secrets:
- EC2_SSH_KEY: the pem certificate for the instance
- HOST_DNS: public host of the instance
- USERNAME: the username of the EC2 instance
- TARGET_DIR: the deployment directory 

---
# Reuse Build Artifact in Deploy Job

Reuse the built code from "build-backend" job in the "deploy-backend" one 

---
# Output Public URL After Deployment

Output the public URL once the code has been deployed

---
# Configure Nginx Reverse Proxy for HTTPS

I have only enabled HTTPS port on my EC2 instance, can you configure an nginx reverse proxy to properly map the ports?

---
# Can Nginx Be Configured in Workflow?

I mean if it can be configured inside the workflow

---
# Can Workflow Create SSL Certificates?

can the workflow create the certificates if they are not already there? 

---
# Use HOST_DNS for Certbot and Set Email

your_domain.com is in the secret HOST_DNS since I do not expect a domain different from the AWS EC2 DNS. For email, you can use javier.sanz@cose.seat

---
# Is Output Public URL Still Correct?

Is this output still correct? have ports been mapped?

---
# Confirm Update Output Public URL

yes 

---
# Reminder: Always Save Prompts to prompts-jsb.md

always remember to add the prompts to @prompts-jsb.md using @save-prompts.mdc . It's important! do not forget about it! 

---
# Analyze Workflow Failure Risks

do you think the workflow is going to work? analyze the failure risks

---
# Test Workflow on Commit Instead of PR

let's test the workflow, change the condition to a commit instead of a pull request 

---
# Reminder: Remember the Prompts

remember the prompts please 

---
# Save the Prompt Instruction

save the prompt 

---
# Still Having YAML Syntax Issue

still having the issue:

Invalid workflow file: .github/workflows/pipeline.yml#L97
You have an error in your yaml syntax on line 97

remember to save the prompt 

---
# Build Backend Errors: Prisma and TypeScript

now I have errors when building the backend:

Build Backend
Process completed with exit code 2.
Build Backend
Property 'PrismaClientInitializationError' does not exist on type 'typeof Prisma'.
Build Backend
Property 'PrismaClientInitializationError' does not exist on type 'typeof Prisma'.
Build Backend
Parameter 'step' implicitly has an 'any' type.
Build Backend
Parameter 'app' implicitly has an 'any' type.

remember the @save-prompts.mdc 

---
# How to Ensure Prompts Are Always Saved

include the lates prompt, how can I do it so you don't forget everytime? 

---
# 15 errors in the pipeline after

I have this error: copying the error from github actions, bla bla bla

---
# SSH Connection Timeout Error During File Copy

now there is a timeout error copying the files to EC2:

Run appleboy/scp-action@v0.1.7
/usr/bin/docker run --name e2e915dc9c3a5da4d0a96e9ea4493ed1484_aa577a --label 196e2e --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SOURCE" -e "INPUT_TARGET" -e "INPUT_PORT" -e "INPUT_PASSWORD" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_PASSPHRASE" -e "INPUT_FINGERPRINT" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_RM" -e "INPUT_DEBUG" -e "INPUT_STRIP_COMPONENTS" -e "INPUT_OVERWRITE" -e "INPUT_TAR_DEREFERENCE" -e "INPUT_TAR_TMP_PATH" -e "INPUT_TAR_EXEC" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_TIMEOUT" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GI
drone-scp version: v1.6.14
tar all files into /tmp/SPQUBRgBJX.tar.gz
remote server os type is unix
scp file to server.
2025/05/16 13:53:52 error copy file to dest: ***, error message: dial tcp 16.170.220.200:22: i/o timeout
drone-scp error: error copy file to dest: ***, error message: dial tcp 16.170.220.200:22: i/o timeout

---