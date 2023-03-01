# Poshem Azure DevOps Project

## Project Requirements

- Set up an Azure DevOps organization and create new project: If you don't already have an Azure DevOps organization that you can use for this project or use an existing organization and new project
- Git for Windows
- Visual Studio Code
- Install Terraform 


## Task 1 Generate a Sample dotnetCore Project and fork a Python Sample app from a git repository
- make a new directory and cd into it
use the command below to generate a sample dotnet template
```sh
dotnet new webapp
```
![Alt text](images/dotnet%20webapp%20template.png)


### fork a Python Sample app from a git repository
From here 
![Alt text](images/fork%20python%20code.png)
>Link to repo: https://github.com/RussMaxwell/PythonWebApp
## Task 2 Create a New Azure Repo in Azure DevOps and clone your existing .Net Core App source code
- Create a microsoft account 
- Create a new AzureDevops account
- create an organisation
- create a project
I'll be naming mine POSHEM
![Alt text](images/POSHEM%20project.png)

- click on repo
![Alt text](images/POSHEM%20Repo.png)

- copy the push an existing repository from command line

![Alt text](images/POSHEM%20Repo%20push.png)

- on the termnal initialize the repo
```sh
git init
```
Then stage all the changes by using:
```sh
git add .
```
commit those changes:
```sh
git commit -m "commit message"
```

- now paste the previously copied code from the project repo to the Terminal
- it should bring a git credential page login, input your details
- refresh the web browser, you should see the files 
![Alt text](images/after%20refreshing.png)

## Task 3 Integrate SonarCloud into your Azure Devops and integrate it into the pull request process

- We go to the market place and install the sonar cloud extention
![Alt text](images/let's%20go%20to%20market.png)
![Alt text](images/Sonar%20cloud%20extention.png)
- let's 
![Alt text](images/install%20sonar%20cloud.png)

- Let's get our PAT(Personal Access Token)
![Alt text](images/get%20PAT%20step%201.png)
- we can acuatll define the permission in the custom option beut for this project we will go with full access
![Alt text](images/get%20PAT%20step%202.png)
![Alt text](images/get%20PAT%20step%203.png)
![Alt text](images/get%20PAT%20step%204.png)
![Alt text](images/get%20PAT%20step%205.png)
![Alt text](images/get%20PAT%20step%206.png)