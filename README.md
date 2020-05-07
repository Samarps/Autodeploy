# Autodeploy

The Project consists of three jobs:

Job1: This is triggered by git hooks. When it gets triggered, firstly it goes to the remote location i.e., Github & then downloads the new code on its workspace. After this it copies the code in rhel8 in the folder “/root/website/dev1”. It installs a new httpd OS with already configured webserver using docker image & then links the document root of this OS with the folder “/root/website/dev1”. Hence, the webpage gets deployed on the testing system.

Job2: This is triggered by git hooks as well as by build trigger with upstream project as “Job3”. When it gets triggered, firstly goes to the remote location i.e., Github & then downloads the new code on its workspace. After this it copies the code in rhel8 in the folder “/root/website/master”. It installs a new httpd OS with already configured webserver using docker image & then links the document root of this OS with the folder “/root/website/master”. Hence, the webpage gets deployed on the testing system. This job is much similar to job1.

Job3: This is triggered by remote trigger. It merges the “dev1” branch to the “master” branch. But it requires git credentials to merge.  The URL for remote trigger of this job is set on the “Deploy” button on the webpage deployed on testing system. To run this project QAT needs to click the “deploy” button once they webpage deployed on the testing system.
