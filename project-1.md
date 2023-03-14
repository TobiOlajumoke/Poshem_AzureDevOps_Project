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

- merge it to the master branch
![Alt text](images/complete%20the%20pull%20request%20after%20successful%20build.png)
![Alt text](images/complete%20merge.png)
- check sonarcloud webpage 
 ![Alt text](images/sonario%20pullrequest%20refresh.png)


- we'll see we have fully integrated sonarcloud it into the pull request process
![Alt text](images/pull%20request%20with%20sonar%20cloud%20complete.png)


## Task 4 - Integrate Mend (Formerly White-source) for code quality and vulnerabilities issues with your code.

- **We go to the Market place and install MEND formerly know as white source bolt**
![Alt text](images/market%20place.png)
- **Select the free version and install inside your organisation**
![Alt text](images/free%20mendbolt.png)
- Go to organisation settings and under extention see MEND
![Alt text](images/orgnaisation%20level%20MEND.png) 

- Set it up
![Alt text](images/fill%20it%20up.png)

- Go to pipeline and edit pipeline
![Alt text](images/edit%20pipline%20and%20add%20mend.png)

- add mend bolt to agent job 
![Alt text](images/add%20men%20to%20agent%20job.png)

- search and add mend bolt
![Alt text](images/mend%20bolt.png)

- save and queue
![Alt text](images/mendbolt%20complete%20build.png)

- after a successful build check:
![Alt text](images/mend%20bolt%201%20&%202.png)
![Alt text](images/mend%20bolt%203.png)
![Alt text](images/mend%20bolt%204.png)


- Mend results
![Alt text](images/mend%20bolt%20result.png)


## **Task 5 Create a basic build pipeline from a template and set the trigger settings to invoke a continuous integration build and verify the build completed successfully along with the code quality result from sonar-cloud and mend-bolt **

- From the previous task we have built a dotnet pipeline an have intergrated sonarcloud and Mend bolt. 
 
 
Now to set a trigger to invole a continuous intergration build 

- Firstly go to pipeline
![Alt text](images/ci%20trigger%201.png)

- edit the existing pipline 

![Alt text](images/dotnet%20webapp%20template.png)

- go to the triger tab and enable continous intergration
![Alt text](images/go%20to%20the%20trigger%20tab.png)
![Alt text](images/save%20and%20queue%20ci%20trigger.png)

- add a commit message and click run
![Alt text](images/comment%20save%20and%20run.png)

- after a successful build let's check out Mend bolt and sonarcloud

- Mend Bolt result:
![Alt text](images/mendbolt%20no%20risk.png)

- Sonarcloud result:
![Alt text](images/sonarcloud%20result.png)
![Alt text](images/sonarcloud%20result2.png)


## **Task 6 Install Terraform on your Local computer on Google or using Chocolatey**

I'll be installing terraform using chocolatey from my terminal

- go to the official [chocolatey website](https://chocolatey.org/install)

- using the powershell with administrative access paste:

```sh
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

- after chocolatey is installed use te below command to install Terraform on windows

To install it
```sh
choco install terraform
```

![Alt text](images/terraform%20installed.png)

To update it
```sh
choco upgrade terraform
```

To uninstall it
```sh
choco uninstall terraform
```


## Task 7 
Set the Terraform Backends and Provider and Provision :
- An Azure App Service Plan and an Azure App Service 
- An Azure App Service for container, 
- Azure Container Registry, 
- Azure Container instance
- Azure Kubernetes Service



### Firstly we need a resource group
refrence: https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/resource_group
![Alt text](images/terra%201.png)
- After setting up the main.tf and variable.tf 

- run a `terraform build` if there is no error

- run a `terraform apply`

- type yes 

![Alt text](../../Pictures/terra%203.png)

![Alt text](images/Terrabuild.png)

![Alt text](images/Terraapply.png)

- check the azure portal for the new created resource
![Alt text](images/poshemRG.png)

- ### Azure App Service Plan and An Azure App Service 


>refrence: https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service

![Alt text](images/serviceplan%20&%20webappplan%20code.png)
- After setting up the main.tf and variable.tf 

- run a `terraform plan` if there is no error

- run a `terraform apply`

- type yes 
![Alt text](images/serviceplan%20&%20webappplan.png)

- check the azure portal for the new created resource
![Alt text](images/serviceplan%20&%20webappplan%20portal.png)


### An Azure App Service for container

>refrence: https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/container_app


- After setting up the main.tf and variable.tf 
![Alt text](images/conatinerapp%201.png)
- run a `terraform plan` if there is no error
![Alt text](images/conatinerapp%202.png)
- run a `terraform apply`

- type yes 
![Alt text](images/conatinerapp%203.png)

- check the azure portal for the new created resource
![Alt text](images/conatinerapp%204.png)



### Azure Container Registry

>refrence: https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/container_registry


- After setting up the main.tf and variable.tf 
![Alt text](images/container%20registry%201.png)
- run a `terraform plan` if there is no error
![Alt text](images/container%20registry%202.png)
- run a `terraform apply`

- type yes 
![Alt text](images/container%20registry%203.png)

- check the azure portal for the new created resource
![Alt text](images/container%20registry%204.png)



### Azure Container instance
>refrence: 

- After setting up the main.tf and variable.tf 

- run a `terraform plan` if there is no error

- run a `terraform apply`

- type yes 


- check the azure portal for the new created resource

### Azure Kubernetes Service
>refrence: 



- After setting up the main.tf and variable.tf 

- run a `terraform plan` if there is no error

- run a `terraform apply`

- type yes 


- check the azure portal for the new created resource

## Task 8 Create a Release Pipeline and create Three different stage for DEV, QA & Production

DEV
![Alt text](images/dev%20env.png)

QA
![Alt text](images/QA%20env.png)

PRODUCTION
![Alt text](images/Prod%20env.png)
All environment:
![Alt text](images/all%20env.png)




## Task 9 
## To implement the code quality restriction on the release pipeline, 



- From our previoulsy created repo, let's add a text in the index.cshtml file:
![Alt text](images/index%20cshtml%20edit.png)

- Go to pipeline and classic editor

![Alt text](images/dqp%20step%201.png)

- click on continue
![Alt text](images/dqp%20step%202.png)

- select empty job
![Alt text](images/dqp%20step%2033.png)

- agent job and select dotnet build,restore and publish
![Alt text](images/dqp%20step%204.png)

- add dotnet core agent job 3 times, edit it add restore and publish 
![Alt text](images/dqp%20step%205%20three%20times.png)
- add use dotnet core to the agent job
![Alt text](images/dqp%20step%207%20dotnet%20core.png)
![Alt text](images/dqp%20step%208%20add%20dotnet%20core.png)
- add publish build artifact to agent job
![Alt text](images/dqp%20step%209%20add%20publish%20build.png)
- set dotnet build and restore agent jobs path to `**/*.csproj`
![Alt text](images/dqp%20step%2010%20coonfig%20retore%20path.png)
![Alt text](images/dqp%20step%2011%20coonfig%20build%20path.png)

- set version of use dotnet job to `7.0x`
![Alt text](images/dqp%20step%2012%20usedotnet%20version%207.png)
- paste this in the argument: 
```sh
--configuration $(BuildConfiguration) --output
 $(Build.ArtifactStagingDirectory)
 ```
![Alt text](images/dqp%20step%2013%20pulish%20arguments.png)
![Alt text](images/dqp%20step%2014%20release%20variable.png)
![Alt text](images/dqp%20step%2015%20trgger%20CI.png)
![Alt text](images/dqp%20step%2016%20save%20and%20queue.png)
![Alt text](images/dqp%20step%2017%20commit,save%20and%20run.png)

- create a service plan in the pipeline settings:
![Alt text](images/service%20connection%201.png)
![Alt text](images/service%20connection%202.png)
![Alt text](images/service%20connection%203.png)
![Alt text](images/service%20connection%204.png)

- Create a release pipeline with the below steps:
![Alt text](images/dqp%20step%2018%20create%20release%20pipeline.png)

![Alt text](images/release%20pipline%201.png)

![Alt text](images/release%20pipline%202.png)

![Alt text](images/release%20pipline%203.png)

![Alt text](images/release%20pipline%204.png)

![Alt text](images/release%20pipline%205.png)

![Alt text](images/release%20pipline%206.png)

![Alt text](images/release%20pipline%207.png)

![Alt text](images/release%20pipline%208.png)

**After a succesful Dev environment deployment**

- check the app service for the dev environment and check the domain site
![Alt text](images/dev%20domain%202.png)
![Alt text](images/dev%20domain%203.png)





**Set  a pre-deployment approval in the QA stage.**



- Fristly set up QA app service
![Alt text](images/qa%20app%20service%20created.png)
- go to azure devops/project/to the release pipeline and  enable continous deployment trigger
![Alt text](images/QA%20release%20setup%20continous%20deployment%20trigger.png)

- set a pre-deployement method
![Alt text](images/QA%20release%20setup%201.png)
![Alt text](images/QA%20release%20setup%201.1.png)
![Alt text](images/QA%20release%20setup%202.png)
![Alt text](images/QA%20release%20setup%203.png)

- set QA predeployment
![Alt text](images/predeployment%20qa%201.png)

![Alt text](images/predeployment%20qa%202.png)

![Alt text](images/predeployment%20qa%203.png)

![Alt text](images/predeployment%20qa%204%20after%20push%20new%20commit.png)

- edit the repo index.cshtml
![Alt text](images/edit%20repo%20index.png)
![Alt text](images/commit%20and%20save.png)


- back to the release pipeline
![Alt text](images/check%20in%20release%20pipeline.png)
![Alt text](images/predeployment%20qa%205%20approve.png)

![Alt text](images/predeployment%20qa%206.png)

![Alt text](images/qa%20success.png)
![Alt text](images/check%20qa%20domain.png)
![Alt text](images/poshem%20qa%20result.png)




## create a deployment slot (staging slot)  in the Production stage 

- we create production app service plan
![Alt text](images/prod%20deployment%20slot%201.png)
- go to deployment slot
![Alt text](images/prod%20deployment%20slot%202.png)
- upgrade the spec to an higher service plan, after the project enusre to terminate all provisoned resources to avoid billings
![Alt text](images/prod%20deployment%20slot%203.png)
- add slot 
![Alt text](images/prod%20deployment%20slot%204%20add%20slot.png)
- choose a name and add
![Alt text](images/prod%20deployment%20slot%205%20name%20and%20add.png)
![Alt text](images/prod%20deployment%20slot%206.png)




- go to the project azure devops release pipeline
![Alt text](images/prod%20stage%201.png)
- edit and add production stage 
![Alt text](images/prod%20stage%202.png)
- configure job task and add deployment slot to job tasks
![Alt text](images/prod%20stage%203%20deploy%20to%20slot.png)

- go to the repo and make a new commit in the index.cshtml file
![Alt text](images/edit%20repo%20to%20see%20prod.png)
- wait for the build to complete
![Alt text](images/build%20complete.png)
- go check the release pipeline if it completed
![Alt text](images/prod%20complete.png)
- go to azureportal, to the production app service and under deployment slot, click swap
![Alt text](images/prod%20swap%201.png)

- swap from target = Staging env to target poshemprod
![Alt text](images/source%20ro%20target.png)
- after a success message
![Alt text](images/source%20ro%20target.png%20success.png)
- check the default domain in the over view section
![Alt text](images/check%20prod%20domain.png)
- result
![Alt text](images/prod%20final%20result.png)


## Task 10 Integrate Azure pipeline with Slack

- Navigate to Organization Settings > Security > Policies, and turn on the Third-party application access via OAuth

![Alt text](images/activate%20thirdparty.png)
![Alt text](images/activate%20thirdparty%202%20.png)

- open a slack account and sign in using the app or your web browser


- create a new workspace or use an existing one, i'm creating a new one

- go to the settings and add azure pipelines to any channel of choice using these steps:
![Alt text](images/azure%20pipline%20connect%201.png)
![Alt text](images/azure%20pipline%20connect%202.png)
![Alt text](images/azure%20pipline%20connect%203.png)
![Alt text](images/azure%20pipline%20connect%204.png)
![Alt text](images/release%20pipline%205.png)
![Alt text](images/azure%20pipline%20connect%206.png)
![Alt text](images/azure%20pipline%20connect%207.png)

- sign in to azure pipeline from the channel
![Alt text](images/azure%20pipline%20connect%208.png)
![Alt text](images/azure%20pipline%20connect%209.png)
![Alt text](images/azure%20pipline%20connect%20copy%20%20code%2011.png)
![Alt text](images/azure%20pipline%20connect%20enter%20%20code11.png)

![Alt text](images/azure%20pipline%20connect10.png)
![Alt text](images/azure%20piplin%20succeessfully%20connected.png)

- connect and specify what results you want to see build pipelines or release pipelines and can even specify the exvcat build form the numerous ones you have
![Alt text](images/my%20build%20url.png)

```sh
/azpipelines subscribe <build or release url>
```


- now let's trigger a build in our pipeline and see the result reflect in our slack app
![Alt text](images/after%20a%20succeful%20build%20%20check%20slack.png)
![Alt text](images/after%20a%20succeful%20build%20%20check%20slack%20result%20.png)


