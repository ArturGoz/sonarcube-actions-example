﻿# Sonarcube actions example 

## Prerequisites

- **Java Development Kit (JDK) 17**
- **Maven**
- **Git**

## Setup Instructions

### Set up github actions
1. add file with following path /github/workflows/ci.yml tu your project
2. configure file with code https://github.com/ArturGoz/sonarcube-actions-example/blob/main/.github/workflows/ci.yml#L1-L30
3. go to "Settings" in your github repository and choose "Branches"
4. add rule : paste develop branch for "Branch name pattern" and toggle buttons as in screenshot
<img width="1280" height="632" alt="зображення" src="https://github.com/user-attachments/assets/b431ec95-2a00-4bfc-8ee5-7724345d2919" />

5. Add check with name "Build and run tests + SonarCloud"(will be appeared when file will be merged or in MR)

### Set up Sonarcube
1. register sonar cloud account with github. Link: https://sonarcloud.io/login
2. create your organization with your github
3. analyze your new project
<img width="482" height="338" alt="зображення" src="https://github.com/user-attachments/assets/c8cc2879-d372-494d-91e3-829496667eed" />

4. go to your project in sonar cloud click "Adminisration" and choose "Analysis Method" and turn off Automtic Analysis
5. go to "My Account" and choose "Security" 
6. give any name to your token and generate it
7. after generation copy hashed token and save somewhere
8. go to "Settings" in your github repository and choose "Secrets and variables" -> Actions
9. create new secret
10. type SONAR_TOKEN for name and type hashed token from sonar in secret which we get from step 6
11. build plugins https://github.com/ArturGoz/sonarcube-actions-example/blob/main/pom.xml#L66-L94
12. add your properties https://github.com/ArturGoz/sonarcube-actions-example/blob/main/pom.xml#L17-L19
13. add config https://github.com/ArturGoz/sonarcube-actions-example/blob/main/.github/workflows/ci.yml#L31-L39
14. push changes to github and check if check actions started with all needs

