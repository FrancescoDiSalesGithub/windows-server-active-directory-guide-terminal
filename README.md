# windows-server-active-directory-guide-terminal (Windows Server 2019 version)

Installing active directory services on a windows server using terminal session


# Setting up windows server 2019

Run windows powershell if after logged in you have a cmd instance:
`powershell`

Then start to install the Active Directory Domain Services:
`Install-WindowsFeature AD-Domain_Services -IncludemanagementTools`

Import the following  windows feature and the following module:
```

Install-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory

```

Then run the following code:

```

Import-Module ServerManager
Add-WindowsFeature Web-Server, Web-WebServer, Web-Common-Http, Web-Static-Content, Web-Default-Doc, Web-Dir-Browsing, Web-Http-Errors, Web-App-Dev, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Health, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Security, Web-Basic-Auth, Web-Windows-Auth, Web-Filtering, Web-Digest-Auth, Web-Performance, Web-Stat-Compression, Web-Dyn-Compression, Web-Mgmt-Console, NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, RPC-Over-HTTP-Proxy -IncludeAllSubFeature

```


Restart the server by typing:
`Restart-Computer`

After restart wait some minutes and then type:

```

Import-Module ServerManager
Import-Module ActiveDirectory

```

If the second command fails try to run it again two-three times if no error happens, then the module has started correctly.

Start to install an Active Directory Forest:

`Install-ADDSForest -DomainName "yourdomain.com" -DomainNetbiosName "YOURDOMAIN" `


It will ask you for the safe password (usually it must be a complex one with an Uppercase letter a lowercase letter a number and a symbol). After typing the password wait until the install operation is done.





  




