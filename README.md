# ASP.NET-CORE-1.1-Development-with-SSL
Visual Studio 2017

### For debugging in IIS Express.
Create New ASP>NET Core Web Application(.NET Core).
Select Web Application and be sure that you have "ASP.NET Core 1.1" selected in the dropdown and Individual User Accounts.

<p align="center">
  <img src="/MD_Images/Capture%201.PNG" width="600"/>
</p>
https://github.com/petervanhemert/ASP.NET-CORE-1.1-Development-with-SSL/blob/master/MD_Images/Capture%201.PNG

......Capture 1......
Right click your project and select properties.
select Debug in the left menu.
Enable SSL. and save . Remember the URL in this case https://localhost:44336/
......Capture 2.......
See in your launchSettings.json that the sslPort is changed from 0 to 44336
.......Capture 3.......
et voila' 
.......Capture 4.......

### For debugging in Project(Kestrel).
Create certificate:
Right click your project and select properties.
.......Capture 7.......
select Signing in the left menu.
Select the box "Sign the assembly".
in the dropdown select new.
Give your key a name and password.
.......Capture 8. and 9......
In your solution you will see the certificate file pfx.
.......Capture 10.......
Open program.cs
before
.......Capture 5.......


####Add dependency in Nuget package Manager.
```
Microsoft.AspNetCore.Server.Kestrel.Https 
```

 dependency from Nuget package Manager.
.......Capture 11.......
back to Program.cs and ad the following code so that it looks like this:
after
.......Capture 6.......
I put the URL as: https://localhost:5011 you can choose whatever you like.
Now change your debug mode into the project. and F5 or ctrl F5.
.......Capture 12.......
Go to your browser and enter the URL https://localhost:5011.
.......Capture 13.......
select ADVANCED and then "Proceed to localhost (unsafe)".
And It's running in Https now.

