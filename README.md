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

- **We go to the market place and install the sonar cloud extention**
![Alt text](images/let's%20go%20to%20market.png)
![Alt text](images/Sonar%20cloud%20extention.png)
![Alt text](images/install%20sonar%20cloud.png)

- **Let's get our PAT(Personal Access Token)**
![Alt text](images/get%20PAT%20step%201.png)

![Alt text](images/get%20PAT%20step%202.png)
- we can actualy define the permission in the custom option but for this project we will go with full access
![Alt text](images/get%20PAT%20step%203.png)

- Vist https://sonarcloud.io/signin and sigin in with your Azure devops account

- Analyse a new project
![Alt text](images/sonar%20cloud%20analyse%20new%20project.png)
- import the project you want by filling up the below:

![Alt text](images/Sonario%20Import%20project.png)

- **We are to fill the name of our oganisation and the previously copied PAT and proceed to next page**
![Alt text](images/sonar%20cloud%20org%20and%20pat%20input.png)
![Alt text](images/soanar%20tocken.png)
- **Go to the pipeline a build a new one with classic editor**
![Alt text](images/Sonar%20cloud%20pipline%20build.png)
![Alt text](images/build%20pipline%20setup.png)
![Alt text](images/use%20classic%20editor.png)
![Alt text](images/classic%20editor.png)
- **Scroll and pick the NetCore sonar cloud**
![Alt text](images/scroll%20pick%20NETCORE%20with%20sinarcoud.png)
- **Now we set it up, pick the Azure pool and Agent specification you want the code to run there's Mac,Linux and Windows with various Specifications. I am using Windows Latest**
![Alt text](images/pipline%20build.png)
- **here i define the parameter where it should restore and build `csporj`**
![Alt text](images/poshem%20pipe%20csporj.png)



- **We shall be creating sonarcloud service connection here**
![Alt text](images/to%20project%20settings.png)
![Alt text](images/get%20PAT%20step%204.png)
![Alt text](images/get%20PAT%20step%205.png)
![Alt text](images/get%20PAT%20step%206.png)
- **Here we will be  add the token given from sonarcloud.io here and give our connection on a name**
![Alt text](images/soanar%20tocken.png)
![Alt text](images/Connection%20Sonar%20cloud.png)

- **We'll set the Prepare analysis on the cloud job and  fill the highlited boxes with the data given from the sonarcloud.io**
![Alt text](images/fill%20sonar%20pipeline%20info.png)
![Alt text](images/save%20and%20queue.png)
**Incase your build fails try rearrangeing the agent order like this :**
![Alt text](images/incase.png)
- Our build is succesful now let's return to sonarcloud.io and refresh
![Alt text](images/success%20ful%20build.png)
- **Resfresh the webpage**
![Alt text](images/sonarcloud%20refresh.png)
- **Steps to take to setup Build validation**

![Alt text](images/to%20project%20settings.png)
![Alt text](images/pull%20request%20repo.png)
![Alt text](images/pull%20request%20policy.png)
![Alt text](images/pull%20request%20bracnch%20policy.png)
![Alt text](images/pull%20request%20branch%20protection.png)
![Alt text](images/build%20validation.png)
![Alt text](images/final.png)

- **We going to set up pull request in the sonar cloud setting**
**Administration > General settings > Pull request**

![Alt text](images/sonar%20io%20pullrequest.png)
![Alt text](images/sonar%20io%20pullrequest%202.png)
![Alt text](images/sonar%20io%20pullrequest%20PAT.png)

we are gonna see the pull request scan in out sonarcloud
- Now we create a branch
![Alt text](images/New%20branch.png)
![Alt text](images/workitem.png)
![Alt text](images/enter%20the%20branch.png)

- make an edit in the C file
![Alt text](images/make%20a%20comment%20in%20C.png)
![Alt text](images/make%20a%20commit%202.png)
![Alt text](images/make%20a%20comment%20in%20C%20(3).png)


- create a pull request  
![Alt text](images/create%20pull%20request.png)
![Alt text](images/create%20pull%20request%201.png)

- Wait for the build to complete
![Alt text](images/wait%20a%20bit.png)
![Alt text](images/wait%20a%20bit%20the%20pull%20request%20triggeed%20a%20build.png)

