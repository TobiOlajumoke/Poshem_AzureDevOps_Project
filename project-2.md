You and your team have a requirement by your company to make things more modern so the organization can not only succeed, but stay ahead of their competition. Management now understands the needs and complexity that comes with staying ahead of their competition and they know that they need to. Otherwise, the organization will fall… The solution therein is to containerize their application

## Task 1 In your Local Computer, in Vs-code, Create a New Branch, and Create a New file  “Dockerfile”  using Nano or vi  any editor of your choice.




- use `git checkout -b <new branch name>`
![Alt text](images/git%20branch.png)


- create a docker file with nano text editor
`nano dockerfile`




## Task 2 Using the Docker Registry as guide for docker command for creating docker file, and depending on the requirement from your company, Create the Dockerfile with the instructions.

- visit https://hub.docker.com/_/python

use any image of your choice


```sh
FROM python:alpine3.16
WORKDIR /app
COPY ./APP
COPY requirements.txt .
RUN pip install -r requirements.txt
CMD "python", "app.py"
```
![Alt text](images/docker%20file.png)
- save it ctrl + x and enter





## Task 3 Save and commit your work then push it  to the remote repository in Azure DevOps


- create a new project in azure devops
![Alt text](images/pythonapp%201.png)

- go to repo and paste the push an existing repo command to vscode cli


- check the project repo branch







Task 4 
Create a Pull Request to merge your branch and verify Sonar-cloud comment on your changes, and verify it merged successfully.

Task 5 
Create a Build pipeline to Build the image and push to Container Registry and
Create a Release Pipeline to Deploy in Azure web app for containers, 
Create a New Stage and Deploy into Azure Container Instance.

Task 6 
Create a Build pipeline to Build the image and push to Container Registry and Deploy into Azure Kubernetes Service and then verify your app is up and running.
