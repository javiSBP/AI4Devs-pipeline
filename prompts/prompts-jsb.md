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
# Error: npm and pm2 Not Found on EC2 During Deploy

now I get this error for "Restart backend service on EC2"

2s
Run appleboy/ssh-action@v1.0.3
  with:
    host: ***
    username: ***
    key: ***
    script: cd ***
  sudo npm install -g pm2
  npm install --production
  pm2 restart all || pm2 start dist/index.js --name backend
  
    port: 22
    timeout: 30s
    command_timeout: 10m
    proxy_port: 22
    proxy_timeout: 30s
/usr/bin/docker run --name e0ec7e4488a0d1fc5b48489a631b3cc9a886ae_fe82d6 --label e0ec7e --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SCRIPT" -e "INPUT_PORT" -e "INPUT_PASSPHRASE" -e "INPUT_PASSWORD" -e "INPUT_SYNC" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_CIPHER" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_FINGERPRINT" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_CIPHER" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "INPUT_SCRIPT_STOP" -e "INPUT_ENVS" -e "INPUT_ENVS_FORMAT" -e "INPUT_DEBUG" -e "INPUT_ALLENVS" -e "INPUT_REQUEST_PTY" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GITHUB_RUN_ATTEMPT" -e "GITHUB_ACTOR_ID" -e "GITHUB_ACTOR" -e "GITHUB_WORKFLOW" -e "GITHUB_HEAD_REF" -e "GITHUB_BASE_REF" -e "GITHUB_EVENT_NAME" -e "GITHUB_SERVER_URL" -e "GITHUB_API_URL" -e "GITHUB_GRAPHQL_URL" -e "GITHUB_REF_NAME" -e "GITHUB_REF_PROTECTED" -e "GITHUB_REF_TYPE" -e "GITHUB_WORKFLOW_REF" -e "GITHUB_WORKFLOW_SHA" -e "GITHUB_REPOSITORY_ID" -e "GITHUB_TRIGGERING_ACTOR" -e "GITHUB_WORKSPACE" -e "GITHUB_ACTION" -e "GITHUB_EVENT_PATH" -e "GITHUB_ACTION_REPOSITORY" -e "GITHUB_ACTION_REF" -e "GITHUB_PATH" -e "GITHUB_ENV" -e "GITHUB_STEP_SUMMARY" -e "GITHUB_STATE" -e "GITHUB_OUTPUT" -e "RUNNER_OS" -e "RUNNER_ARCH" -e "RUNNER_NAME" -e "RUNNER_ENVIRONMENT" -e "RUNNER_TOOL_CACHE" -e "RUNNER_TEMP" -e "RUNNER_WORKSPACE" e0ec7e:4488a0d1fc5b48489a631b3cc9a886ae
======CMD======
cd ***
sudo npm install -g pm2
npm install --production
pm2 restart all || pm2 start dist/index.js --name backend

======END======
err: sudo: npm: command not found
err: bash: line 3: npm: command not found
err: bash: line 4: pm2: command not found
err: bash: line 4: pm2: command not found
2025/05/15 22:58:36 Process exited with status 127 

---
# Still Having npm and pm2 Not Found Error on EC2

still having the issue:

Run appleboy/ssh-action@v1.0.3
/usr/bin/docker run --name ad0c89268824ff1b40cedf00b2cba03_3739e4 --label 000356 --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SCRIPT" -e "INPUT_PORT" -e "INPUT_PASSPHRASE" -e "INPUT_PASSWORD" -e "INPUT_SYNC" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_CIPHER" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_FINGERPRINT" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_TIMEOUT" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_CIPHER" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "INPUT_SCRIPT_STOP" -e "INPUT_ENVS" -e "INPUT_ENVS_FORMAT" -e "INPUT_DEBUG" -e "INPUT_ALLENVS" -e "INPUT_REQUEST_PTY" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GITHUB_RUN_ATTEMPT" -e "GITHUB_ACTOR_ID" -e "GITHUB_ACTOR" -e "GITHUB_WORKFLOW" -e "GITHUB_HEAD_REF" -e "GITHUB_BASE_REF" -e "GITHUB_EVENT_NAME" -e "GITHUB_SERVER_URL" -e "GITHUB_API_URL" -e "GITHUB_GRAPHQL_URL" -e "GITHUB_REF_NAME" -e "GITHUB_REF_PROTECTED" -e "GITHUB_REF_TYPE" -e "GITHUB_WORKFLOW_REF" -e "GITHUB_WORKFLOW_SHA" -e "GITHUB_REPOSITORY_ID" -e "GITHUB_TRIGGERING_ACTOR" -e "GITHUB_WORKSPACE" -e "GITHUB_ACTION" -e "GITHUB_EVENT_PATH" -e "GITHUB_ACTION_REPOSITORY" -e "GITHUB_ACTION_REF" -e "GITHUB_PATH" -e "GITHUB_ENV" -e "GITHUB_STEP_SUMMARY" -e "GITHUB_STATE" -e "GITHUB_OUTPUT" -e "RUNNER_OS" -e "RUNNER_ARCH" -e "RUNNER_NAME" -e "RUNNER_ENVIRONMENT" -e "RUNNER_TOOL_CACHE" -e "RUNNER_TEMP" -e "RUNNER_WORKSPACE" 000356:8ad0c89268824ff1b40cedf00b2cba03
======CMD======
export PATH=$PATH:/usr/local/bin:/usr/bin:/bin
cd ***
sudo npm install -g pm2
npm install --production
pm2 restart all || pm2 start dist/index.js --name backend

======END======
err: sudo: npm: command not found
err: bash: line 4: npm: command not found
err: bash: line 5: pm2: command not found
err: bash: line 5: pm2: command not found
2025/05/15 23:02:27 Process exited with status 127 

---
# Still Failing: apt-get Not Found, NodeSource Script Error

it keeps failing at the same point:

Run appleboy/ssh-action@v1.0.3
/usr/bin/docker run --name ccde7586d2a26deacd48438e6934c7127db984_dec06a --label ccde75 --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SCRIPT" -e "INPUT_PORT" -e "INPUT_PASSPHRASE" -e "INPUT_PASSWORD" -e "INPUT_SYNC" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_CIPHER" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_FINGERPRINT" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_TIMEOUT" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_CIPHER" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "INPUT_SCRIPT_STOP" -e "INPUT_ENVS" -e "INPUT_ENVS_FORMAT" -e "INPUT_DEBUG" -e "INPUT_ALLENVS" -e "INPUT_REQUEST_PTY" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GITHUB_RUN_ATTEMPT" -e "GITHUB_ACTOR_ID" -e "GITHUB_ACTOR" -e "GITHUB_WORKFLOW" -e "GITHUB_HEAD_REF" -e "GITHUB_BASE_REF" -e "GITHUB_EVENT_NAME" -e "GITHUB_SERVER_URL" -e "GITHUB_API_URL" -e "GITHUB_GRAPHQL_URL" -e "GITHUB_REF_NAME" -e "GITHUB_REF_PROTECTED" -e "GITHUB_REF_TYPE" -e "GITHUB_WORKFLOW_REF" -e "GITHUB_WORKFLOW_SHA" -e "GITHUB_REPOSITORY_ID" -e "GITHUB_TRIGGERING_ACTOR" -e "GITHUB_WORKSPACE" -e "GITHUB_ACTION" -e "GITHUB_EVENT_PATH" -e "GITHUB_ACTION_REPOSITORY" -e "GITHUB_ACTION_REF" -e "GITHUB_PATH" -e "GITHUB_ENV" -e "GITHUB_STEP_SUMMARY" -e "GITHUB_STATE" -e "GITHUB_OUTPUT" -e "RUNNER_OS" -e "RUNNER_ARCH" -e "RUNNER_NAME" -e "RUNNER_ENVIRONMENT" -e "RUNNER_TOOL_CACHE" -e "RUNNER_TEMP" -e "RUNNER_WORKSPACE" ccde75:86d2a26deacd48438e6934c7127db984
======CMD======
export PATH=$PATH:/usr/local/bin:/usr/bin:/bin
if ! command -v npm &> /dev/null; then
  curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
  sudo apt-get install -y nodejs
fi
sudo npm install -g pm2
cd ***
npm install --production
pm2 restart all || pm2 start dist/index.js --name backend

======END======
out: Error: This script is only supported on Debian-based systems.
err: sudo: apt-get: command not found
err: sudo: npm: command not found
err: bash: line 8: npm: command not found
err: bash: line 9: pm2: command not found
err: bash: line 9: pm2: command not found
2025/05/15 23:04:49 Process exited with status 127

---
# Update Workflow to Copy All Backend Files to EC2

yes, uodate the workflow and the prompts

---
# Add Debug Step to List Files on EC2

go

---
# Debug Output Shows Files in Wrong Location

this is the list files output:

Run appleboy/ssh-action@v1.0.3
  with:
    host: ***
    username: ***
    key: ***
    script: ls -l ***
  ls -l ***/dist
  
    port: 22
    timeout: 30s
    command_timeout: 10m
    proxy_port: 22
    proxy_timeout: 30s
/usr/bin/docker run --name fa018db6e1b35bba3c49c0a31f88e516ac7325_8ed073 --label fa018d --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SCRIPT" -e "INPUT_PORT" -e "INPUT_PASSPHRASE" -e "INPUT_PASSWORD" -e "INPUT_SYNC" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_CIPHER" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_FINGERPRINT" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_TIMEOUT" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_CIPHER" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "INPUT_SCRIPT_STOP" -e "INPUT_ENVS" -e "INPUT_ENVS_FORMAT" -e "INPUT_DEBUG" -e "INPUT_ALLENVS" -e "INPUT_REQUEST_PTY" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GITHUB_RUN_ATTEMPT" -e "GITHUB_ACTOR_ID" -e "GITHUB_ACTOR" -e "GITHUB_WORKFLOW" -e "GITHUB_HEAD_REF" -e "GITHUB_BASE_REF" -e "GITHUB_EVENT_NAME" -e "GITHUB_SERVER_URL" -e "GITHUB_API_URL" -e "GITHUB_GRAPHQL_URL" -e "GITHUB_REF_NAME" -e "GITHUB_REF_PROTECTED" -e "GITHUB_REF_TYPE" -e "GITHUB_WORKFLOW_REF" -e "GITHUB_WORKFLOW_SHA" -e "GITHUB_REPOSITORY_ID" -e "GITHUB_TRIGGERING_ACTOR" -e "GITHUB_WORKSPACE" -e "GITHUB_ACTION" -e "GITHUB_EVENT_PATH" -e "GITHUB_ACTION_REPOSITORY" -e "GITHUB_ACTION_REF" -e "GITHUB_PATH" -e "GITHUB_ENV" -e "GITHUB_STEP_SUMMARY" -e "GITHUB_STATE" -e "GITHUB_OUTPUT" -e "RUNNER_OS" -e "RUNNER_ARCH" -e "RUNNER_NAME" -e "RUNNER_ENVIRONMENT" -e "RUNNER_TOOL_CACHE" -e "RUNNER_TEMP" -e "RUNNER_WORKSPACE" -e "ACTIONS_RUNTIME_URL" -e "ACTIONS_RUNTIME_TOKEN" -e "ACTIONS_CACHE_URL" -e "ACTIONS_RESULTS_URL" -e GITHUB_ACTIONS=true -e CI=true -v "/var/run/docker.sock":"/var/run/docker.sock" -v "/home/runner/work/_temp/_github_home":"/github/home" -v "/home/runner/work/_temp/_github_workflow":"/github/workflow" -v "/home/runner/work/_temp/_runner_file_commands":"/github/file_commands" -v "/home/runner/work/AI4Devs-pipeline/AI4Devs-pipeline":"/github/workspace" fa018d:b6e1b35bba3c49c0a31f88e516ac7325
======CMD======
ls -l ***
ls -l ***/dist

======END======
out: total 4
out: drwxrwxr-x. 3 *** *** 18 May 15 22:58 backend
out: drwxrwxr-x. 3 *** *** 63 May 15 23:23 backend-artifact
out: -rw-rw-r--. 1 *** *** 86 May 15 23:21 package-lock.json
err: ls: cannot access '***/dist': No such file or directory
2025/05/15 23:23:23 Process exited with status 2