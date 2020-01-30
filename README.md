![MIKES DATA WORK GIT REPO](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_01.png "Mikes Data Work")        

# Prestage Cluster Configuration – Find The OU
**Post Date: July 6, 2016**        



## Contents    
- [About Process](##About-Process)  
- [Author](#Author)    

## About-Process

<p>Whenever you're setting up a Failover Cluster Configuration in a post Server 2012 world… You'll need to prestage the cluster objects in Active Directory. Microsoft offers some good documentation on the steps to carry out creating the Failover Cluster using the a checklist found here: https://technet.microsoft.com/en-us/library/dn505754(v=ws.11).aspx and also the actual prestaging process found here: https://technet.microsoft.com/en-us/library/dn466519(v=ws.11).aspx
Unfortunately; there aren't a great deal of short cut tips on how to get some of the information you need. For example; finding the OU's a Computer resides in. The good news is you can do this with a quick one-liner in powershell. Get-ADComputer.
Using a standard 2 Node Example for Failover Cluster implementation:</p>

#THIS WORKS
get-adcomputer MyClusterName
get-adcomputer Server01
get-adcomputer Server02
#THIS ALSO WORKS
"MyClusterName", "Server01", "Server02" | get-adcomputer

![Find OU To PreStaging Clusters]( https://mikesdatawork.files.wordpress.com/2016/07/image002.png "Find OU")
 
Alternatively there is also a quick one-liner you can do in Command Prompt if you want to get the OU where the server resides and that's the following
dsquery computer –samid MyServerName$
Notice the dollar sign $ at the end of the Server Name. This is required in the script. In the results you'll see the OU's where the Server resides.

![Get OUs]( https://mikesdatawork.files.wordpress.com/2016/07/image0011.png "Get OUs")
 


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

[![Gist](https://img.shields.io/badge/Gist-MikesDataWork-<COLOR>.svg)](https://gist.github.com/mikesdatawork)
[![Twitter](https://img.shields.io/badge/Twitter-MikesDataWork-<COLOR>.svg)](https://twitter.com/mikesdatawork)
[![Wordpress](https://img.shields.io/badge/Wordpress-MikesDataWork-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

  
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Mikes Data Work](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_02.png "Mikes Data Work")

