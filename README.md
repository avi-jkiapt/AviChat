# Socket_Chat_App
##[Link to Website ](https://avichat.azurewebsites.net/)
A Chat App using Socket.io

Socket.IO is composed of two parts:
A server that integrates with (or mounts on) the Node.JS HTTP Server: socket.io
A client library that loads on the browser side: socket.io-client

Clone or Download the app and from command line go to app folder and start server using node index.js

I have modified this app to use Azure DevOps and Azure App Service.

Steps to Create Azure Pipeline:
- Go to  https://dev.azure.com/{your_username}
- Create a new Project (AviChat)
- Create Azure Repository/Github Repository and push your code from local system
- Create Pipeline. Select Azure Repo or Github Repo where your code exist.It will create a YAML file.Click on Save and Run.Here if you get any build error then check logs and fix the issue. Eg. If Node.js app then mostly you will add build script in package.json.
- Create Release Pipeline. Select template Deploy Node.js app on Web Server.Here you will have Stage. Give Development/Production as your wish.
- Next you have to create an artifact.Choose source type Azure repo or Github repo.Give default branch as master.And source alias to '.'. This will be the folder from where the code run.
- Next click on flash to provide continuous deployment trigger. Provide master branch as default branch.
- Next Click on Task.Provide stage as you have created.Select Azure subscription and app type.
- This app should be Azure app service web app. You have to go to https://portal.azure.com/ to create azure app service web app. And then select the app name in task.
- Next click on create a release by selecting stage and artifact as you have created in last step.
- Now Deploy the release.Now you will get an artifact path issue. Copy the path directory from logs.And go to pipeline setting. Click on task and go to package/folder and provide the copied path.
- Now again create a new release and deploy the change.

- For Debugging go to azure portal and go to Azure app service setting and start the log to get log error.

- Diagnose: https://{app_service_name}.scm.azurewebsites.net/DebugConsole/?shell=powershell
- https://{app_service_name}.scm.azurewebsites.net/dev/wwwroot/:vs.output

- You can have a look of ChatApp here.

- Website: https://avichat.azurewebsites.net/

Image of App:
![first](https://github.com/avi-jkiapt/Socket_Chat_App/blob/master/first.png)
![second](https://github.com/avi-jkiapt/Socket_Chat_App/blob/master/second.png)

Image of Issue/Path:
![third](https://github.com/avi-jkiapt/AviChat/blob/master/Azure_repos.PNG)
![four](https://github.com/avi-jkiapt/AviChat/blob/master/Pipeline.PNG)
![five](https://github.com/avi-jkiapt/AviChat/blob/master/artifact_path_issue.PNG)
![six](https://github.com/avi-jkiapt/AviChat/blob/master/azure_logs_on.PNG)
![seven](https://github.com/avi-jkiapt/AviChat/blob/master/azure_node_version_setting.PNG)