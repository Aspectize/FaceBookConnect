# FaceBookConnect
Aspectize Extension to manage FaceBook Connect in your Aspectize App.

You will need to create a FaceBook Application in your FB account.

## 1 - Download

Download extension package from aspectize.com:
- in the portal, goto extension section
- browse extension, and find FaceBookConnect
- download package and unzip it into your local WebHost Applications directory; you should have a FaceBookConnect directory next to your app directory.

## 2 - Configuration

a/ Add FaceBookConnect as Shared Application in your application configuration file.
In your Visual Studio Project, find the file Application.js in the Configuration folder.

Add FaceBookConnect in the Directories list :
```javascript
app.Directories = "FaceBookConnect";
```

b/ Add a new Configured service.
In your Visual Studio Project, find the file Service.js in the Configuration/Services folder.
Add a new service definition, filed with your own API Key and Secret provided by your FB App.
DataService is any DataBaseService used by the extention to store data.

```javascript
var fbConnectService = Aspectize.ConfigureNewService('MyFBConnectService', aas.ConfigurableServices.FacebookConnect);
fbConnectService.DataBaseServiceName = "DataService";
fbConnectService.OAuthClientApplictionApiKey = "XXXX";
fbConnectService.OAuthClientApplictionApiSecret = "XXXX";
```

##3 - Implementation

In your Authenticate command
