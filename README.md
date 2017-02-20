# ASP.NET-CORE-1.1-Development-with-SSL-Visual Studio 2017

- [Debugging in IIS Express](#debugging-in-iis-express)
- [Debugging in IIS Project(Kestrel)](#debugging-in-project)

## Debugging in IIS Express
Create New ASP>NET Core Web Application(.NET Core).
Select Web Application and be sure that you have "ASP.NET Core 1.1" selected in the dropdown and Individual User Accounts.

<p align="center">
  <img src="/MD_Images/Capture%201.PNG" width="600"/>
</p>

Right click your project and select properties.
select Debug in the left menu.

Enable SSL and save. 

Remember the URL, in this case:
```
https://localhost:44336/
```

<p align="center">
  <img src="/MD_Images/Capture%202.PNG" width="600"/>
</p>
See in your launchSettings.json that the sslPort is changed from 0 to 44336
<p align="center">
  <img src="/MD_Images/Capture%203.PNG" width="600"/>
</p>
Et voilà....You're Done.
<p align="center">
  <img src="/MD_Images/Capture%204.PNG" width="600"/>
</p>

## Debugging in Project
Create certificate:
Right click your project and select properties.
<p align="center">
  <img src="/MD_Images/image_thumb_4.png" width="600"/>
</p>
select Signing in the left menu.
Select the box "Sign the assembly".
in the dropdown select new.
Give your key a name and password.
<p align="center">
  <img src="/MD_Images/Capture%208.PNG" width="350"/>
  <img src="/MD_Images/Capture%209.PNG" width="350"/>
</p>
In your solution you will see the certificate file pfx.
<p align="center">
  <img src="/MD_Images/Capture 10.PNG" width="350"/>
</p>
####Add dependency in Nuget package Manager.
```
Microsoft.AspNetCore.Server.Kestrel.Https 
```
<p align="center">
  <img src="/MD_Images/Capture 11.PNG" width="600"/>
</p>

Open program.cs and ad the following code so that it looks like this:

Before and After
<p align="center">
  <img src="/MD_Images/Capture%205.PNG" width="250"/>
  <img src="/MD_Images/Capture%206.PNG" width="450"/>
</p>

I put the URL as: https://localhost:5011 you can choose whatever you like.
Now change your debug mode into the project. and F5 or ctrl F5.
<p align="center">
  <img src="/MD_Images/Capture 12.2.PNG" width="600"/>
</p>
Go to your browser and enter the URL:
```
https://localhost:5011
```
<p align="center">
  <img src="/MD_Images/Capture 13.PNG" width="600"/>
</p>
select ADVANCED and then "Proceed to localhost (unsafe)".
<p align="center">
  <img src="/MD_Images/Capture 13.PNG" width="600"/>
</p>
And It's running in Https now.

