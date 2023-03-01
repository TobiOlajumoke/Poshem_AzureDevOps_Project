# Poshem Azure DevOps Project

## Project Requirements

- Set up an Azure DevOps organization and create new project: If you don't already have an Azure DevOps organization that you can use for this project or use an existing organization and new project
- Git for Windows
- Visual Studio Code
- Install Terraform 


## Task 1
Generate a Sample dotnetCore Project and fork a Python Sample app from a git repository
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
## Task 2 
Create a New Azure Repo in Azure DevOps and clone your existing .Net Core App source code
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
git commit -m <commit message>
```

- now paste the previously copied code from the project repo to the Terminal
code looks like this:
```sh

```
