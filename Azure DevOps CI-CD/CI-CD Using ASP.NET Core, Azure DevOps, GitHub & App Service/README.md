## <p align=left>ASP.NET Core Project CI/CD Using Azure DevOps, GitHub & Azure App Service<br> <br> </p>
| **SL** | **Topic** |
| --- | --- |
| 01 | [Introduction](#01) |
| 02 | [Create Azure DevOps Project](#02) |
| 03 | [Clone Repository & Create .Net Project](#03) |
| 04 | [Create Build Pipeline](#04) |
| 05 | [Create Azure App Service](#05) |
| 06 | [Create a Service Connection](#06) |
| 07 | [Create Release Pipeline](#07) |
| 08 | [Deployment Verification](#08) |

### <a name="01">:diamond_shape_with_a_dot_inside: &nbsp;Introduction</a> 
We will create a CI/CD of an ASP.NET Core Project Using Azure DevOps, GitHub & Azure App Service. So we need:

1. Azure DevOps Account
2. GitHub Account
3. Azure Subscription

Let's start...

### <a name="02">:diamond_shape_with_a_dot_inside: &nbsp;Create Azure DevOps Project</a>
- Go to [Azure DevOps Portal](https://dev.azure.com/). Click the organization name and go inside your desired organization page. 
If you don't have any organization then you can create a new organization by clicking the **New Organization** option.

   <img src= "https://github.com/Shadikul-Islam/Microsoft-Based-Work/blob/master/Azure%20DevOps-Create%20and%20Configure%20Self%20Hosted%20Agent/Images/Image-1.png" alt="Organization Image"> 

- I am going to my existing organization named **MyOrganization01.** Now we need to go inside to a project page. If you don't have any projects create a new project by clicking the **New Project** option.

   <img src= "https://github.com/Shadikul-Islam/Microsoft-Based-Work/blob/master/Azure%20DevOps-Create%20and%20Configure%20Self%20Hosted%20Agent/Images/Image-2.png" alt="Project Image">
   
- I am going to my existing project named **MyProject01**.

### <a name="03">:diamond_shape_with_a_dot_inside: &nbsp;Clone Repository & Create .Net Project</a>
I have already created a project which is pushed on GitHub. If you don't have any project then you can clone/create a new project and then push the source code to GitHub. My project is here: ````https://github.com/Projects-of-Shadikul/CI-CD-Project-20````. We will create CI/CD for this project.

### <a name="04">:diamond_shape_with_a_dot_inside: &nbsp;Create Build Pipeline</a>
- Go to [Azure DevOps Portal](https://dev.azure.com/). In the first step, we already discussed how to [Create Azure DevOps Project](#02), We created an Azure DevOps Project. Go inside that project. You will see like below page:
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-1.png" alt="Project Page"> <br><br>
- Click the **Pipelines**. A pipeline page will appear. Click **New Pipeline**. You will see a page like below.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-2.png" alt="Pipeline Page"> <br><br>
- **Connect Page:** Our code is in **GitHub**. So we will select GitHub. For the first time, It will ask for authentication between Azure DevOps and your GitHub account. Give proper permission to access your GitHub repository from Azur DevOps
- **Select Page:** It's time to select the Project repository. My project repository name is **CI-CD-Project-20**. I will select that. You have to select your repository.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-3.png" alt="Pipeline Page"> <br><br>
- Now an Azure Pipeline approval page will appear. Click on Approve and Install.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-4.png" alt="Pipeline Permission"> <br><br>
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-5.png" alt="Pipeline Permission"> <br><br>
  If it asks for login again in Azure DevOps then login. Also, select the organization and project of the Azure DevOps that you already selected before.
- **Configure Page:** Now it's time to configure our pipeline. Select the **Starter Pipeline** option.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-6.png" alt="Configuration"> <br><br>
- **Review Page:** A YAML file will be created automatically by Azure DevOps. The name of the YAML file is **azure-pipelines.yml**. Just click on the **Save and Run** button. 
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-7.png" alt="Review page"> <br><br>
  It will run a build on your GitHub Project. You can check the build result from **Jobs**. Click on the **Jobs** button and on the next page you will see the details.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-8.png" alt="Job page"> <br><br>
- Go to the pipeline page. Just one step back from your job details page. Click on the right upper side 3 dots. Click **Edit Pipeline**. 
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-9.png" alt="Pipeline Edit Page"> <br><br>
  You will see the **azure-pipelines.yml** file. We have to change the file configuration. First, let's remove the sample task under the steps that were on the file. Now your **azure-pipelines.yml** file will be like this:
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-10.png" alt="YAML Edit Page"> <br><br>
  On the right side **Search bar**, search **.NET Core** and select that.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-11.png" alt="YAML Edit Page"> <br><br>
  A new interface will appear. 
  
  **Command:** _build_
  
  **Path to project(s):**  _**/*.csproj_
  
  **Arguments:** _-c Release_
  
  After providing those values click **Add.**
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-12.png" alt="YAML Edit Page"> <br><br>
  You can notice that YAML Configuration has been added on the YAML file.
  
  Again select the **.NET Core** task. Now set the interface like below:
  
  **Command:** _Publish_
  
  **Arguments:** _-o $(Build.ArtifactStagingDirectory)/web_
  
  After providing those values click **Add.**
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-13.png" alt="YAML Edit Page"> <br><br>
  You can again notice that YAML Configuration has been added to the YAML file.
  
  Now again search for **Publish build artifacts** on the **Search bar**.
  
  **Path to publish:** _$(Build.ArtifactStagingDirectory)_
  
  **Artifact name:** _drop_
  
  **Artifact publish location:** _Azure Pipelines_
  
  After providing those values click **Add.**
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-14.png" alt="YAML Edit Page"> <br><br>
  You can again notice that YAML Configuration has been added to the YAML file. Now remove this last line from the YAML file ````publishLocation: 'Container'````. Click the **Save** button which will commit to our project repository. You can see the updated **azure-pipelines.yml** file that we have added. Also, it will automatically build in Azure DevOps and publish our artifacts.
  
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

### <a name="05">:diamond_shape_with_a_dot_inside: &nbsp;Create Azure App Service</a> 
- Go to [Azure Portal](https://portal.azure.com/#home) and Search **App Service** on the search bar. Go to the App Service. Click Create and a page will appear. Provide the necessary information on that page. I have given the web app name is **sadik-ci-cd**. Select the **Runtime** option. Our project is asp.net core so I have selected **.NET Core 3.1 (LTS)**.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-17.png" alt="App Service"> <br><br>
  Click Next: **Deployment>**.
  
- On the Deployment page, you have to enable the **GitHub Continuous Deployment** Options and connect to the **GitHub account**, and select the proper **repository**.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-18.png" alt="App Service"> <br><br>
  Now click **Review and Create** then click **Create**. It will create the app service. You can see the overview from the Azure portal. Our application URL is https://sadik-ci-cd.azurewebsites.net.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-19.png" alt="App Service"> <br><br>
- Let's browse our app service page https://sadik-ci-cd.azurewebsites.net. We can see the Azure default page.

### <a name="06">:diamond_shape_with_a_dot_inside: &nbsp;Create a Service Connection</a>
- Go to the [Azure DevOps Portal](https://dev.azure.com/). Now go inside the project and from the left bottom click **Project Settings**. Scroll down settings and select **Service Connection**.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-21.png" alt="Service Connection"> <br><br>
- Click **Create New Service Connection**. Search **Azure Resource Manager** and select it and click Next.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-22.png" alt="Service Connection"> <br>
- Then select Authentication method: **Service principal (automatic)** and click Next.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-23.png" alt="Service Connection"> <br>
- Provide necessary information about subscription and other information then Save it.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-24.png" alt="Service Connection"> <br><br>
- On the Service Connection page, you will see the name **AzureSubscription** that we configured.
 <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-25.png" alt="Service Connection"> <br><br>
 Our service connection is now completed.
- As we integrated it on the GitHub project repository and that repository we already build from Azure DevOps Build Pipeline so we should see our sample application page. If you can not see your application then don't worry you need to release it. We will do it next step on the Release pipeline.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-20.png" alt="App Service"> <br><br>
  This is our application sample page.
  
- You can notice that our CI means Continuous Integration has been completed. Now It's time to setup CD means Continuous Deployment.
 
### <a name="07">:diamond_shape_with_a_dot_inside: &nbsp;Create Release Pipeline</a>
- Go to the Azure DevOps portal again. Click Pipelines and now click **Release**. Click **New** then click **New Release Pipeline**. 
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-26.png" alt="Release Pipeline"> <br><br>
- Click the **Empty Job** option. 
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-27.png" alt="Release Pipeline"> <br><br>
  Provide a Stage Name. I provided **Deployment**. then Click the **X** sign on the right top side.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-28.png" alt="Release Pipeline"> <br>
- Click **Add an Artifcat** option.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-29.png" alt="Release Pipeline"> <br><br>
  **Select Source Type:** Build, Project: Your project, Source: Your build package, and click Add.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-30.png" alt="Release Pipeline"> <br><br>
- Click the Deployment **Job and Task** option.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-31.png" alt="Release Pipeline"> <br><br>
  Click the Agent job **+** icon. Search **Azure App Service Deploy** from Search Bar and select **Azure App Service Deploy** and click Add.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-32.png" alt="Release Pipeline"> <br><br>
  Now we have to configure the Deployment into Azure App Service. Provide the necessary information.
  
  **Display Name:** Give as your wish
  
  **Connection Type:** Azure Resource Manager
  
  **Azure Subscription:** AzureSubscription (We created this on previous step)
  
  **App Service:** Web App Windows. We created this type App Service on previous step.
  
  **App Service Name:** sadik-ci-cd
  
  **Package or folder:** Select the build package that we created from the build pipeline and stored it in the **drop/web** folder.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-33.png" alt="Release Pipeline"> <br>
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-34.png" alt="Release Pipeline"> <br>
- Now click Save and then **Create Release** then click **Create**.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-35.png" alt="Release Pipeline"> <br>
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-36.png" alt="Release Pipeline"> <br><br>
- It will show **Release-1 has been created**. Click on Release-1 you can see the details stage.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-37.png" alt="Release Pipeline"> <br><br>
- In release-1 Page click **Edit** and Select **Edit Pipeline** option.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-38.png" alt="Release Pipeline"> <br><br>
- Click Artifacts Icon then Enable the **Continuous deployment trigger** and Save it.
 <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-39.png" alt="Release Pipeline"> <br><br>
- Now Run Create Release again. It will create Release-2. 
- You can now visit the App Service URL. You will see our sample page.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-20.png" alt="App Service"> <br><br>

### <a name="08">:diamond_shape_with_a_dot_inside: &nbsp;Deployment Verification</a>
- Now all things have been setup. Let's change our code and commit it. It will automatically be deployed into our Azure App Service. Go to your project and change something. In my case, I am going to my project from my local PC. Going to **Pages** folder then Opening **LogIn.cshtml**. Adding this line ````<div><br> CI/CD Testing By Sadik <br> </div>````.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-40.png" alt="Validation"> <br><br>
- Committed it in Git then pushed it into GitHub. After push Azure DevOps build pipeline will automatically build the code then release the pipeline deploy it into Azure App Service. Once it is deployed then go to the browser and hit the app service URL. You will see the updated application after some moments cause it will run the build and release pipeline.
  <br><br> <img src= "https://github.com/Shadikul-Islam/CI-CD-Projects/blob/master/Azure%20DevOps%20CI-CD/CI-CD%20Using%20ASP.NET%20Core%2C%20Azure%20DevOps%2C%20GitHub%20%26%20App%20Service/Images/Image-41.png" alt="Validation"> <br><br>
- Yes! We can see it's showing our updated application using CD/CD.


#### :diamond_shape_with_a_dot_inside: &nbsp;That’s it. We have learned ASP.NET Core Project CI/CD Using Azure DevOps, GitHub & Azure App Service. :diamond_shape_with_a_dot_inside: &nbsp;Happy Learning. :diamond_shape_with_a_dot_inside: &nbsp;
