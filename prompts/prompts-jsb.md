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

---
# Nginx and Certbot Install Error on Non-Debian System

now the error is about installing nginx and the certificate:

Run appleboy/ssh-action@v1.0.3
  with:
    host: ***
    username: ***
    key: ***
    script: sudo apt-get update
  sudo apt-get install -y nginx certbot python3-certbot-nginx
  sudo systemctl enable nginx
  sudo systemctl start nginx
  sudo certbot --nginx --non-interactive --agree-tos --redirect -m javier.sanz@cose.seat -d ***
    port: 22
    timeout: 30s
    command_timeout: 10m
    proxy_port: 22
    proxy_timeout: 30s
/usr/bin/docker run --name a5c4ee4997d25860da44f182f9378bba3c19e4_9d3cc6 --label a5c4ee --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SCRIPT" -e "INPUT_PORT" -e "INPUT_PASSPHRASE" -e "INPUT_PASSWORD" -e "INPUT_SYNC" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_CIPHER" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_FINGERPRINT" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_TIMEOUT" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_CIPHER" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "INPUT_SCRIPT_STOP" -e "INPUT_ENVS" -e "INPUT_ENVS_FORMAT" -e "INPUT_DEBUG" -e "INPUT_ALLENVS" -e "INPUT_REQUEST_PTY" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GITHUB_RUN_ATTEMPT" -e "GITHUB_ACTOR_ID" -e "GITHUB_ACTOR" -e "GITHUB_WORKFLOW" -e "GITHUB_HEAD_REF" -e "GITHUB_BASE_REF" -e "GITHUB_EVENT_NAME" -e "GITHUB_SERVER_URL" -e "GITHUB_API_URL" -e "GITHUB_GRAPHQL_URL" -e "GITHUB_REF_NAME" -e "GITHUB_REF_PROTECTED" -e "GITHUB_REF_TYPE" -e "GITHUB_WORKFLOW_REF" -e "GITHUB_WORKFLOW_SHA" -e "GITHUB_REPOSITORY_ID" -e "GITHUB_TRIGGERING_ACTOR" -e "GITHUB_WORKSPACE" -e "GITHUB_ACTION" -e "GITHUB_EVENT_PATH" -e "GITHUB_ACTION_REPOSITORY" -e "GITHUB_ACTION_REF" -e "GITHUB_PATH" -e "GITHUB_ENV" -e "GITHUB_STEP_SUMMARY" -e "GITHUB_STATE" -e "GITHUB_OUTPUT" -e "RUNNER_OS" -e "RUNNER_ARCH" -e "RUNNER_NAME" -e "RUNNER_ENVIRONMENT" -e "RUNNER_TOOL_CACHE" -e "RUNNER_TEMP" -e "RUNNER_WORKSPACE" -e "ACTIONS_RUNTIME_URL" -e "ACTIONS_RUNTIME_TOKEN" -e "ACTIONS_CACHE_URL" -e "ACTIONS_RESULTS_URL" -e GITHUB_ACTIONS=true -e CI=true -v "/var/run/docker.sock":"/var/run/docker.sock" -v "/home/runner/work/_temp/_github_home":"/github/home" -v "/home/runner/work/_temp/_github_workflow":"/github/workflow" -v "/home/runner/work/_temp/_runner_file_commands":"/github/file_commands" -v "/home/runner/work/AI4Devs-pipeline/AI4Devs-pipeline":"/github/workspace" a5c4ee:4997d25860da44f182f9378bba3c19e4
======CMD======
sudo apt-get update
sudo apt-get install -y nginx certbot python3-certbot-nginx
sudo systemctl enable nginx
sudo systemctl start nginx
sudo certbot --nginx --non-interactive --agree-tos --redirect -m javier.sanz@cose.seat -d ***
======END======
err: sudo: apt-get: command not found
err: sudo: apt-get: command not found
err: Failed to enable unit: Unit file nginx.service does not exist.
err: Failed to start nginx.service: Unit nginx.service not found.
err: sudo: certbot: command not found
2025/05/15 23:27:06 Process exited with status 1

---
# Let's Encrypt Certificate Policy Error

the last error is:

Run appleboy/ssh-action@v1.0.3
  with:
    host: ***
    username: ***
    key: ***
    script: if [ -f /etc/debian_version ]; then
    # Debian/Ubuntu
    sudo apt-get update
    sudo apt-get install -y nginx certbot python3-certbot-nginx
    sudo systemctl enable nginx
    sudo systemctl start nginx
    sudo certbot --nginx --non-interactive --agree-tos --redirect -m javier.sanz@cose.seat -d ***
  elif [ -f /etc/redhat-release ] || [ -f /etc/system-release ]; then
    # Amazon Linux/RedHat/CentOS
    sudo yum update -y
    sudo yum install -y nginx
  
    # EPEL repository for Certbot
    sudo yum install -y epel-release
    sudo yum -y install certbot python3-certbot-nginx
  
    sudo systemctl enable nginx
    sudo systemctl start nginx
    sudo certbot --nginx --non-interactive --agree-tos --redirect -m javier.sanz@cose.seat -d ***
  else
    echo "Unsupported OS. Please install Nginx and Certbot manually."
    exit 1
  fi
    port: 22
    timeout: 30s
    command_timeout: 10m
    proxy_port: 22
    proxy_timeout: 30s
/usr/bin/docker run --name e6814adeb5b1324478f96604ebcefb8eff1_b40047 --label 918e68 --workdir /github/workspace --rm -e "INPUT_HOST" -e "INPUT_USERNAME" -e "INPUT_KEY" -e "INPUT_SCRIPT" -e "INPUT_PORT" -e "INPUT_PASSPHRASE" -e "INPUT_PASSWORD" -e "INPUT_SYNC" -e "INPUT_USE_INSECURE_CIPHER" -e "INPUT_CIPHER" -e "INPUT_TIMEOUT" -e "INPUT_COMMAND_TIMEOUT" -e "INPUT_KEY_PATH" -e "INPUT_FINGERPRINT" -e "INPUT_PROXY_HOST" -e "INPUT_PROXY_PORT" -e "INPUT_PROXY_USERNAME" -e "INPUT_PROXY_PASSWORD" -e "INPUT_PROXY_PASSPHRASE" -e "INPUT_PROXY_TIMEOUT" -e "INPUT_PROXY_KEY" -e "INPUT_PROXY_KEY_PATH" -e "INPUT_PROXY_FINGERPRINT" -e "INPUT_PROXY_CIPHER" -e "INPUT_PROXY_USE_INSECURE_CIPHER" -e "INPUT_SCRIPT_STOP" -e "INPUT_ENVS" -e "INPUT_ENVS_FORMAT" -e "INPUT_DEBUG" -e "INPUT_ALLENVS" -e "INPUT_REQUEST_PTY" -e "HOME" -e "GITHUB_JOB" -e "GITHUB_REF" -e "GITHUB_SHA" -e "GITHUB_REPOSITORY" -e "GITHUB_REPOSITORY_OWNER" -e "GITHUB_REPOSITORY_OWNER_ID" -e "GITHUB_RUN_ID" -e "GITHUB_RUN_NUMBER" -e "GITHUB_RETENTION_DAYS" -e "GITHUB_RUN_ATTEMPT" -e "GITHUB_ACTOR_ID" -e "GITHUB_ACTOR" -e "GITHUB_WORKFLOW" -e "GITHUB_HEAD_REF" -e "GITHUB_BASE_REF" -e "GITHUB_EVENT_NAME" -e "GITHUB_SERVER_URL" -e "GITHUB_API_URL" -e "GITHUB_GRAPHQL_URL" -e "GITHUB_REF_NAME" -e "GITHUB_REF_PROTECTED" -e "GITHUB_REF_TYPE" -e "GITHUB_WORKFLOW_REF" -e "GITHUB_WORKFLOW_SHA" -e "GITHUB_REPOSITORY_ID" -e "GITHUB_TRIGGERING_ACTOR" -e "GITHUB_WORKSPACE" -e "GITHUB_ACTION" -e "GITHUB_EVENT_PATH" -e "GITHUB_ACTION_REPOSITORY" -e "GITHUB_ACTION_REF" -e "GITHUB_PATH" -e "GITHUB_ENV" -e "GITHUB_STEP_SUMMARY" -e "GITHUB_STATE" -e "GITHUB_OUTPUT" -e "RUNNER_OS" -e "RUNNER_ARCH" -e "RUNNER_NAME" -e "RUNNER_ENVIRONMENT" -e "RUNNER_TOOL_CACHE" -e "RUNNER_TEMP" -e "RUNNER_WORKSPACE" -e "ACTIONS_RUNTIME_URL" -e "ACTIONS_RUNTIME_TOKEN" -e "ACTIONS_CACHE_URL" -e "ACTIONS_RESULTS_URL" -e GITHUB_ACTIONS=true -e CI=true -v "/var/run/docker.sock":"/var/run/docker.sock" -v "/home/runner/work/_temp/_github_home":"/github/home" -v "/home/runner/work/_temp/_github_workflow":"/github/workflow" -v "/home/runner/work/_temp/_runner_file_commands":"/github/file_commands" -v "/home/runner/work/AI4Devs-pipeline/AI4Devs-pipeline":"/github/workspace" 918e68:14adeb5b1324478f96604ebcefb8eff1
======CMD======
if [ -f /etc/debian_version ]; then
  # Debian/Ubuntu
  sudo apt-get update
  sudo apt-get install -y nginx certbot python3-certbot-nginx
  sudo systemctl enable nginx
  sudo systemctl start nginx
  sudo certbot --nginx --non-interactive --agree-tos --redirect -m javier.sanz@cose.seat -d ***
elif [ -f /etc/redhat-release ] || [ -f /etc/system-release ]; then
  # Amazon Linux/RedHat/CentOS
  sudo yum update -y
  sudo yum install -y nginx

  # EPEL repository for Certbot
  sudo yum install -y epel-release
  sudo yum -y install certbot python3-certbot-nginx

  sudo systemctl enable nginx
  sudo systemctl start nginx
  sudo certbot --nginx --non-interactive --agree-tos --redirect -m javier.sanz@cose.seat -d ***
else
  echo "Unsupported OS. Please install Nginx and Certbot manually."
  exit 1
fi
======END======
out: Last metadata expiration check: 0:19:07 ago on Thu May 15 23:15:58 2025.
out: Dependencies resolved.
out: Nothing to do.
out: Complete!
out: Last metadata expiration check: 0:19:09 ago on Thu May 15 23:15:58 2025.
out: Dependencies resolved.
out: ================================================================================
out:  Package               Arch     Version                     Repository     Size
out: ================================================================================
out: Installing:
out:  nginx                 x86_64   1:1.26.3-1.amzn2023.0.1     amazonlinux    33 k
out: Installing dependencies:
out:  generic-logos-httpd   noarch   18.0.0-12.amzn2023.0.3      amazonlinux    19 k
out:  gperftools-libs       x86_64   2.9.1-1.amzn2023.0.3        amazonlinux   308 k
out:  libunwind             x86_64   1.4.0-5.amzn2023.0.2        amazonlinux    66 k
out:  nginx-core            x86_64   1:1.26.3-1.amzn2023.0.1     amazonlinux   670 k
out:  nginx-filesystem      noarch   1:1.26.3-1.amzn2023.0.1     amazonlinux   9.6 k
out:  nginx-mimetypes       noarch   2.1.49-3.amzn2023.0.3       amazonlinux    21 k
out: Transaction Summary
out: ================================================================================
out: Install  7 Packages
out: Total download size: 1.1 M
out: Installed size: 3.6 M
out: Downloading Packages:
out: (1/7): generic-logos-httpd-18.0.0-12.amzn2023.0 568 kB/s |  19 kB     00:00    
out: (2/7): libunwind-1.4.0-5.amzn2023.0.2.x86_64.rp 1.7 MB/s |  66 kB     00:00    
out: (3/7): nginx-1.26.3-1.amzn2023.0.1.x86_64.rpm   1.5 MB/s |  33 kB     00:00    
out: (4/7): gperftools-libs-2.9.1-1.amzn2023.0.3.x86 5.0 MB/s | 308 kB     00:00    
out: (5/7): nginx-mimetypes-2.1.49-3.amzn2023.0.3.no 1.2 MB/s |  21 kB     00:00    
out: (6/7): nginx-filesystem-1.26.3-1.amzn2023.0.1.n 376 kB/s | 9.6 kB     00:00    
out: (7/7): nginx-core-1.26.3-1.amzn2023.0.1.x86_64.  12 MB/s | 670 kB     00:00    
out: --------------------------------------------------------------------------------
out: Total                                           8.2 MB/s | 1.1 MB     00:00     
out: Running transaction check
out: Transaction check succeeded.
out: Running transaction test
out: Transaction test succeeded.
out: Running transaction
out:   Preparing        :                                                        1/1 
out:   Running scriptlet: nginx-filesystem-1:1.26.3-1.amzn2023.0.1.noarch        1/7 
out:   Installing       : nginx-filesystem-1:1.26.3-1.amzn2023.0.1.noarch        1/7 
out:   Installing       : nginx-mimetypes-2.1.49-3.amzn2023.0.3.noarch           2/7 
out:   Installing       : libunwind-1.4.0-5.amzn2023.0.2.x86_64                  3/7 
out:   Installing       : gperftools-libs-2.9.1-1.amzn2023.0.3.x86_64            4/7 
out:   Installing       : nginx-core-1:1.26.3-1.amzn2023.0.1.x86_64              5/7 
out:   Installing       : generic-logos-httpd-18.0.0-12.amzn2023.0.3.noarch      6/7 
out:   Installing       : nginx-1:1.26.3-1.amzn2023.0.1.x86_64                   7/7 
out:   Running scriptlet: nginx-1:1.26.3-1.amzn2023.0.1.x86_64                   7/7 
out:   Verifying        : generic-logos-httpd-18.0.0-12.amzn2023.0.3.noarch      1/7 
out:   Verifying        : gperftools-libs-2.9.1-1.amzn2023.0.3.x86_64            2/7 
out:   Verifying        : libunwind-1.4.0-5.amzn2023.0.2.x86_64                  3/7 
out:   Verifying        : nginx-1:1.26.3-1.amzn2023.0.1.x86_64                   4/7 
out:   Verifying        : nginx-core-1:1.26.3-1.amzn2023.0.1.x86_64              5/7 
out:   Verifying        : nginx-filesystem-1:1.26.3-1.amzn2023.0.1.noarch        6/7 
out:   Verifying        : nginx-mimetypes-2.1.49-3.amzn2023.0.3.noarch           7/7 
out: Installed:
out:   generic-logos-httpd-18.0.0-12.amzn2023.0.3.noarch                             
out:   gperftools-libs-2.9.1-1.amzn2023.0.3.x86_64                                   
out:   libunwind-1.4.0-5.amzn2023.0.2.x86_64                                         
out:   nginx-1:1.26.3-1.amzn2023.0.1.x86_64                                          
out:   nginx-core-1:1.26.3-1.amzn2023.0.1.x86_64                                     
out:   nginx-filesystem-1:1.26.3-1.amzn2023.0.1.noarch                               
out:   nginx-mimetypes-2.1.49-3.amzn2023.0.3.noarch                                  
out: Complete!
out: Last metadata expiration check: 0:19:12 ago on Thu May 15 23:15:58 2025.
out: No match for argument: epel-release
err: Error: Unable to find a match: epel-release
out: Last metadata expiration check: 0:19:13 ago on Thu May 15 23:15:58 2025.
out: Dependencies resolved.
out: ================================================================================
out:  Package                 Arch    Version                     Repository    Size
out: ================================================================================
out: Installing:
out:  certbot                 noarch  2.6.0-4.amzn2023.0.1        amazonlinux   49 k
out:  python3-certbot-nginx   noarch  2.6.0-4.amzn2023.0.1        amazonlinux  158 k
out: Installing dependencies:
out:  fontawesome-fonts       noarch  1:4.7.0-11.amzn2023.0.2     amazonlinux  205 k
out:  fonts-filesystem        noarch  1:2.0.5-12.amzn2023.0.2     amazonlinux  9.5 k
out:  python3-acme            noarch  2.6.0-4.amzn2023.0.1        amazonlinux  161 k
out:  python3-certbot         noarch  2.6.0-4.amzn2023.0.1        amazonlinux  677 k
out:  python3-configargparse  noarch  1.7-1.amzn2023              amazonlinux   45 k
out:  python3-josepy          noarch  1.13.0-6.amzn2023           amazonlinux   61 k
out:  python3-parsedatetime   noarch  2.6-10.amzn2023             amazonlinux   80 k
out:  python3-pyOpenSSL       noarch  21.0.0-1.amzn2023.0.2       amazonlinux   92 k
out:  python3-pyparsing       noarch  2.4.7-6.amzn2023.0.2        amazonlinux  152 k
out:  python3-pyrfc3339       noarch  1.1-16.amzn2023             amazonlinux   19 k
out: Installing weak dependencies:
out:  python-josepy-doc       noarch  1.13.0-6.amzn2023           amazonlinux   20 k
out: Transaction Summary
out: ================================================================================
out: Install  13 Packages
out: Total download size: 1.7 M
out: Installed size: 7.8 M
out: Downloading Packages:
out: (1/13): fonts-filesystem-2.0.5-12.amzn2023.0.2. 271 kB/s | 9.5 kB     00:00    
out: (2/13): certbot-2.6.0-4.amzn2023.0.1.noarch.rpm 1.1 MB/s |  49 kB     00:00    
out: (3/13): python-josepy-doc-1.13.0-6.amzn2023.noa 806 kB/s |  20 kB     00:00    
out: (4/13): fontawesome-fonts-4.7.0-11.amzn2023.0.2 2.3 MB/s | 205 kB     00:00    
out: (5/13): python3-acme-2.6.0-4.amzn2023.0.1.noarc 2.2 MB/s | 161 kB     00:00    
out: (6/13): python3-certbot-2.6.0-4.amzn2023.0.1.no 9.2 MB/s | 677 kB     00:00    
out: (7/13): python3-configargparse-1.7-1.amzn2023.n 1.4 MB/s |  45 kB     00:00    
out: (8/13): python3-josepy-1.13.0-6.amzn2023.noarch 1.6 MB/s |  61 kB     00:00    
out: (9/13): python3-certbot-nginx-2.6.0-4.amzn2023. 1.8 MB/s | 158 kB     00:00    
out: (10/13): python3-pyparsing-2.4.7-6.amzn2023.0.2 4.8 MB/s | 152 kB     00:00    
out: (11/13): python3-parsedatetime-2.6-10.amzn2023. 1.0 MB/s |  80 kB     00:00    
out: (12/13): python3-pyrfc3339-1.1-16.amzn2023.noar 709 kB/s |  19 kB     00:00    
out: (13/13): python3-pyOpenSSL-21.0.0-1.amzn2023.0. 1.3 MB/s |  92 kB     00:00    
out: --------------------------------------------------------------------------------
out: Total                                           6.0 MB/s | 1.7 MB     00:00     
out: Running transaction check
out: Transaction check succeeded.
out: Running transaction test
out: Transaction test succeeded.
out: Running transaction
out:   Preparing        :                                                        1/1 
out:   Installing       : python3-pyOpenSSL-21.0.0-1.amzn2023.0.2.noarch        1/13 
out:   Installing       : python3-pyrfc3339-1.1-16.amzn2023.noarch              2/13 
out:   Installing       : python3-pyparsing-2.4.7-6.amzn2023.0.2.noarch         3/13 
out:   Installing       : python3-parsedatetime-2.6-10.amzn2023.noarch          4/13 
out:   Installing       : python3-configargparse-1.7-1.amzn2023.noarch          5/13 
out:   Installing       : python-josepy-doc-1.13.0-6.amzn2023.noarch            6/13 
out:   Installing       : python3-josepy-1.13.0-6.amzn2023.noarch               7/13 
out:   Installing       : python3-acme-2.6.0-4.amzn2023.0.1.noarch              8/13 
out:   Installing       : python3-certbot-2.6.0-4.amzn2023.0.1.noarch           9/13 
out:   Installing       : fonts-filesystem-1:2.0.5-12.amzn2023.0.2.noarch      10/13 
out:   Installing       : fontawesome-fonts-1:4.7.0-11.amzn2023.0.2.noarch     11/13 
out:   Installing       : certbot-2.6.0-4.amzn2023.0.1.noarch                  12/13 
out:   Running scriptlet: certbot-2.6.0-4.amzn2023.0.1.noarch                  12/13 
out: Certbot auto renewal timer is not started by default.
out: Run 'systemctl start certbot-renew.timer' to enable automatic renewals.
out:   Installing       : python3-certbot-nginx-2.6.0-4.amzn2023.0.1.noarch    13/13 
out:   Running scriptlet: python3-certbot-nginx-2.6.0-4.amzn2023.0.1.noarch    13/13 
out:   Verifying        : certbot-2.6.0-4.amzn2023.0.1.noarch                   1/13 
out:   Verifying        : fontawesome-fonts-1:4.7.0-11.amzn2023.0.2.noarch      2/13 
out:   Verifying        : fonts-filesystem-1:2.0.5-12.amzn2023.0.2.noarch       3/13 
out:   Verifying        : python-josepy-doc-1.13.0-6.amzn2023.noarch            4/13 
out:   Verifying        : python3-acme-2.6.0-4.amzn2023.0.1.noarch              5/13 
out:   Verifying        : python3-certbot-2.6.0-4.amzn2023.0.1.noarch           6/13 
out:   Verifying        : python3-certbot-nginx-2.6.0-4.amzn2023.0.1.noarch     7/13 
out:   Verifying        : python3-configargparse-1.7-1.amzn2023.noarch          8/13 
out:   Verifying        : python3-josepy-1.13.0-6.amzn2023.noarch               9/13 
out:   Verifying        : python3-parsedatetime-2.6-10.amzn2023.noarch         10/13 
out:   Verifying        : python3-pyOpenSSL-21.0.0-1.amzn2023.0.2.noarch       11/13 
out:   Verifying        : python3-pyparsing-2.4.7-6.amzn2023.0.2.noarch        12/13 
out:   Verifying        : python3-pyrfc3339-1.1-16.amzn2023.noarch             13/13 
out: Installed:
out:   certbot-2.6.0-4.amzn2023.0.1.noarch                                           
out:   fontawesome-fonts-1:4.7.0-11.amzn2023.0.2.noarch                              
out:   fonts-filesystem-1:2.0.5-12.amzn2023.0.2.noarch                               
out:   python-josepy-doc-1.13.0-6.amzn2023.noarch                                    
out:   python3-acme-2.6.0-4.amzn2023.0.1.noarch                                      
out:   python3-certbot-2.6.0-4.amzn2023.0.1.noarch                                   
out:   python3-certbot-nginx-2.6.0-4.amzn2023.0.1.noarch                             
out:   python3-configargparse-1.7-1.amzn2023.noarch                                  
out:   python3-josepy-1.13.0-6.amzn2023.noarch                                       
out:   python3-parsedatetime-2.6-10.amzn2023.noarch                                  
out:   python3-pyOpenSSL-21.0.0-1.amzn2023.0.2.noarch                                
out:   python3-pyparsing-2.4.7-6.amzn2023.0.2.noarch                                 
out:   python3-pyrfc3339-1.1-16.amzn2023.noarch                                      
out: Complete!
err: Created symlink /etc/systemd/system/multi-user.target.wants/nginx.service → /usr/lib/systemd/system/nginx.service.
err: Saving debug log to /var/log/letsencrypt/letsencrypt.log
out: Account registered.
out: Requesting a certificate for ***
err: An unexpected error occurred:
err: Error creating new order :: Cannot issue for "***": The ACME server refuses to issue a certificate for this domain name, because it is forbidden by policy
err: Ask for help or search for solutions at https://community.letsencrypt.org. See the logfile /var/log/letsencrypt/letsencrypt.log or re-run Certbot with -v for more details.
2025/05/15 23:35:17 Process exited with status 1

---
# Configure Nginx for HTTP Without HTTPS

ok lets configure nginx without https and I will open the 80 port in EC2 for HTTP