# FAQ
## Deploying lists does not work
Some users reported that they had problems deploying list by the PowerAutomate Flow. Please check the site you entered in the variable varSitePrefix. Just enter the site url without any trailing slash or html page.
## App cannot be edited in PowerApp Studio due to version conflict
The app was exportet with the PowerApp Studio Version 3.20051.16 - some environments are still on an older version. Currently this PowerApp version is not availible in all regions and not all existing environments are updated to this version. Try to deploy a new sandbox environment and check the version. If this does not help, try to deploy a new environment in another region. 