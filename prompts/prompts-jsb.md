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