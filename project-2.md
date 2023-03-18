You and your team have a requirement by your company to make things more modern so the organization can not only succeed, but stay ahead of their competition. Management now understands the needs and complexity that comes with staying ahead of their competition and they know that they need to. Otherwise, the organization will fall… The solution therein is to containerize their application


## Task 1 In your Local Computer, in Vs-code, Create a New Branch, and Create a New file  “Dockerfile”  using Nano or vi  any editor of your choice.




- use `git checkout -b <new branch name>`




- create a docker file with nano text editor
`nano dockerfile`



## Task 2 Using the Docker Registry as guide for docker command for creating docker file, and depending on the requirement from your company, Create the Dockerfile with the instructions.

- visit https://hub.docker.com/_/microsoft-dotnet-sdk


- add this to the docker file

```sh
FROM mcr.microsoft.com/dotnet/sdk:7.0
WORKDIR /app
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/dotnet-webapp.dll"]

```

- save it ctrl + x and enter



## Task 3 Save and commit your work then push it  to the remote repository in Azure DevOps

- save and commit code
![Alt text](images/save%20and%20commit.png)

- create a new project in azure devops


- go to repo and paste the push an existing repo command to vscode cli
![Alt text](images/dotnet%20repo.png)

- check the project repo branch
![Alt text](images/dotnet%20docker%20branch.png)
![Alt text](images/dotnet%20docker%20branch1.png)

## Task 4 
Create a Pull Request to merge your branch and verify Sonar-cloud comment on your changes, and verify it merged successfully.

- Go to the project settings 
![Alt text](images/repo.png)
- click the repsitory>the dotnetweb app> the policy tab
![Alt text](images/repo%201.png)
- click on branch policy
![Alt text](images/repo%203.png)
- click on build validation
![Alt text](images/repo%204.png)

- add a build policy name, leave the rest on default  and save
![Alt text](images/repo%205.png)

- save and commit 
![Alt text](images/save%20and%20commit.png)

![Alt text](images/git%20merge%201.png)

- Click on repo > branch click on pull request

![Alt text](images/pull%20req.png)
![Alt text](images/pull%20req%201.png)
![Alt text](images/pull%20req%202.png)
![Alt text](images/pull%20req%203.png)



- go to pipelines the pull request would trigger a build 

![Alt text](images/pull%20req%20project%20settings.png)


- Check result in sonarcloud

![Alt text](images/sonar%20pull%20request.png)




## Task 5 

- Create a Build pipeline to Build the image and push to Container Registry

![Alt text](images/create%20build%20pipeline.png)
![Alt text](images/create%20build%20pipeline%201.png)
![Alt text](images/create%20build%20pipeline%202.png)
![Alt text](images/build%20successful.png)
![Alt text](images/check%20registry.png)
![Alt text](images/image%20in%20ACR.png)

- Create a Release Pipeline to Deploy in Azure web app for containers
![Alt text](images/release%20pipeline%20for%20container%20app.png)
![Alt text](images/sucess.png)
![Alt text](images/sucess1.png)
- Create a New Stage and Deploy into Azure Container Instance.

![Alt text](images/ACI.png)
![Alt text](images/ACI%201.png)
![Alt text](images/ACI%20result.png)
![Alt text](images/ACI%20result1.png)



## Task 6 Create a Build pipeline to Build the image and push to Container Registry and Deploy into Azure Kubernetes Service and then verify your app is up and running.

- build pipline and build image
 