## <p align=left>ASP.NET Core Project CI/CD Using Azure DevOps, GitHub & Azure App Service<br> <br> </p>
| **SL** | **Topic** |
| --- | --- |
| 01 | [Introduction](#01) |
| 02 | [Create Azure DevOps Project](#02) |
| 03 | [Clone Repository & Create .Net Project](#03) |
| 04 | [Create Build Pipeline](#04) |
| 05 | [Create a Service connection](#05) |
| 06 | [Create Release Pipeline](#06) |
| 07 | [Deployment Verification](#07) |

### <a name="01">:diamond_shape_with_a_dot_inside: &nbsp;Introduction</a> 
We will create a CI/CD of a ASP.NET Core Project Using Azure DevOps, GitHub & Azure App Service. So we need:

1. Azure DevOps Account
2. GitHub Account
3. Azure Subscription

Let's start...

### <a name="02">:diamond_shape_with_a_dot_inside: &nbsp;Create Azure DevOps Project</a>
- Go to [Azure DevOps Portal](https://dev.azure.com/). Click the organization name and go inside of your desired organization page. 
If you don't have any organization then you can create a new organization by clicking **New Organization** option.

   <img src= "https://github.com/Shadikul-Islam/Microsoft-Based-Work/blob/master/Azure%20DevOps-Create%20and%20Configure%20Self%20Hosted%20Agent/Images/Image-1.png" alt="Organization Image"> 

- I am going to my existing organization named **MyOrganization01.** Now we need to go inside to a project page. If you don't have any projects create a new project by clicking **New Project** option.

   <img src= "https://github.com/Shadikul-Islam/Microsoft-Based-Work/blob/master/Azure%20DevOps-Create%20and%20Configure%20Self%20Hosted%20Agent/Images/Image-2.png" alt="Project Image">
   
- I am going to my existing project named **MyProject01**.

### <a name="03">:diamond_shape_with_a_dot_inside: &nbsp;Clone Repository & Create .Net Project</a>
I have already created a project which is pushed in github. If you don't have any project then you can clone/create a new project then push the source code in github. My project is here: https://github.com/Projects-of-Shadikul/CI-CD-Project-20. We will create CI/CD for this project.

### <a name="04">:diamond_shape_with_a_dot_inside: &nbsp;Create Build Pipeline</a>
- Go to [Azure DevOps Portal](https://dev.azure.com/). In the first step ### <a name="02">:diamond_shape_with_a_dot_inside: &nbsp;Create Azure DevOps Project</a>,     We created a Azure DevOps Project. Go inside to that project. You will see like bleow page:
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-1.png" alt="Project Page"> <br><br>
- Click the **Pipelines**. Pipeline page will be appeared. Click **New Pipeline**. You will see a page like below.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-2.png" alt="Pipeline Page"> <br><br>
- **Connect Page:** Our code is in **GitHub**. So we will select GitHub. For the first time, It will ask for authentication between Azure DevOps and your GitHub account. Give proper permission to access your GItHub repository from Azur DevOps
- **Select Page:** It's time to select the Project repository. My project repository name is: **CI-CD-Project-20**. I will select that. You have to select your repository.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-3.png" alt="Pipeline Page"> <br><br>
- Now an Azure Pipeline approval page will be appeared. Click on Approve and Install.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-4.png" alt="Pipeline Permission"> <br><br>
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-5.png" alt="Pipeline Permission"> <br><br>
  If it ask for login again in Azure DevOps the login. Also select the organization and project of the Azure DevOps that you already selected before.
- **Configure Page:** Now it's time to configure our pipeline. Select the **Starter Pipeline** option.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-6.png" alt="Configuration"> <br><br>
- **Review Page:** A YAML file will be created automatically by Azure DevOps. Name of the YAML file is **azure-pipelines.yml**. Just click on **Save and Run** button. 
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-7.png" alt="Review page"> <br><br>
  It will run a build on your GitHub Project. You can check the build result from **Jobs**. Click on the **Jobs** button and on the next page you will see the details.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-8.png" alt="Job page"> <br><br>
- Go to the pipline page. Just one step back from your job details page. Click on the right upper side 3 dots. Click **Edit Pipeline**. 
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-9.png" alt="Pipeline Edit Page"> <br><br>
  You will see the **azure-pipelines.yml** file. We have to change the file configuration. First let's remvoe the sample task under the steps that was on the file. Now your **azure-pipelines.yml** file will be like this:
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-10.png" alt="YAML Edit Page"> <br><br>
  On the right side **Search bar**, search **.NET Core** and select that.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-11.png" alt="YAML Edit Page"> <br><br>
  A new interface will be appeared. 
  
  **Command:** build
  
  **Path to project(s):**  **/*.csproj
  
  **Arguments:** -c Release
  
  After providing those values click **Add.**
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-12.png" alt="YAML Edit Page"> <br><br>
  You can notice that YAML Configuration has been added on the YAML file.
  
  Again select the **.NET Core** task. Now set the interface like below:
  **Command:** Publish
  
  **Arguments:** -o $(Build.ArtifactStagingDirectory)/web
  
  After providing those values click **Add.**
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-13.png" alt="YAML Edit Page"> <br><br>
  You can again notice that YAML Configuration has been added on the YAML file.
  
  Now again search for **Publish build artifacts** on the **Search bar**.
  
  **Path to publish:** $(Build.ArtifactStagingDirectory)
  
  **Artifact name:** drop
  
  **Artifact publish location:** Azure Pipelines
  
  After providing those values click **Add.**
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-14.png" alt="YAML Edit Page"> <br><br>
  You can again notice that YAML Configuration has been added on the YAML file. Now remove this last line from the YAML file ````publishLocation: 'Container' ````
  Click **Save** button which will commit to our project repository. You can see the updated **azure-pipelines.yml** updated file that we have added. Also it will autmatically build in Azure DevOps and pubilsh our artifacts.
  
- Now our final **azure-pipelines.yml** will be:
  ````
  # Starter pipeline
  # Start with a minimal pipeline that you can customize to build and deploy your code.
  # Add steps that build, run tests, deploy, and more:
  # https://aka.ms/yaml

  trigger:
  - master

  pool:
    vmImage: ubuntu-latest

  steps:

  - task: DotNetCoreCLI@2
    inputs:
      command: 'build'
      projects: '**/*.csproj'
      arguments: '-c Release'

  - task: DotNetCoreCLI@2
    inputs:
      command: 'publish'
      publishWebProjects: true
      arguments: '-o $(Build.ArtifactStagingDirectory)/web'

  - task: PublishBuildArtifacts@1
    inputs:
      PathtoPublish: '$(Build.ArtifactStagingDirectory)'
      ArtifactName: 'drop'
  ````
  
- Go to our pipeline and click our last build project. You will see the **Publish** Button where our artifacts are stored.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-15.png" alt="Artifacts"> <br><br>
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-16.png" alt="Artifacts"> <br><br>
  
