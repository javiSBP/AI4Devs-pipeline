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