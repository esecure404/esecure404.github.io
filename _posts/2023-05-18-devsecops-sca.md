---
title: Software Component Analysis using Safety
date: 2023-05-18 03:37:00 +500
categories: [devsecops]
tags: [devsecops, security]     # TAG names should always be lowercase
---

Software Component Analysis using Safety:

sca is one of the early stages of the pipeline which detects third party vulnerable components/libraries like pip packagaes, mvn packages
npm packages, libraries etc., we can also say it's a static analaysis since the scan running before the execution of code.

Safety is one of the open source tools to detect vulnerable components present in the python code. 

For more info pls check: https://github.com/pyupio/safety


Let's download, install and run the tool locally on simple python django webapp.


git clone https://github.com/esecure404/django.nv.git webapp

![In a single picture] (https://github.com/esecure404/esecure404.github.io/blob/main/assets/webapp.png)

cd webapp

ss

install safety using pip3

pip3 install safety==2.3.5

ss

let's check the safety options by using --help

safety check --help

ss

We are using the tee command to show the output and store it in a file simultaneously.

safety check -r requirements.txt --json | tee safety-output.json

**-r** flag used to specify the input file.
**--json** flag tells that output should be in the JSON format.

ss

we found multiple vulnerable third party components. 


