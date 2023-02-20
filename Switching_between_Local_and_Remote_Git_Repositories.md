# Switching between Local and Remote Git Repositories

If your Git server becomes temporarily unavailable for any reason then a
simple 30-second configuration change in Workbench is all that it takes
to be able to continue running Compliance until your Git server becomes
available once more.

To set MettleCI to use a local Compliance repository for your DataStage
project you just need to point Workbench to the appropriate repository.
Under your user icon (top right) in Workbench select **Manage Projects**
and under **Compliance Repository** set the **URL** field to an
appropriate value following the examples below.

`file://C:\MettleCI\compliance\.git` WINDOWS

`file:///opt/dm/mci/compliance/.git` UNIX

In all cases leave the **Branch** field as `master` and the **Path**
field empty.

To swap back to a remote repository just set the URL to your remote
Git’s path, for example:

`ssh://my_username@my_company.com:7999/mettleci/compliance.git` ALL
PLATFORMS

Note that if you use this technique to point to a local you’ll be
running Compliance against the version of your Compliance repository
stored locally on your DataStage Engine tier. If you’ve committed
changes to the ‘real’ (remote) Compliance repository then these will
only be reflected in the local repository if they've been explicitly
fetched with a `git pull` command.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200605-035808.png](attachments/791314480/791314486.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200605-035520.png](attachments/791314480/791314489.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Remote
Git Repository.png](attachments/791314480/791314492.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Remote
Git Repository](attachments/791314480/791314495)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Git
Repository Integration Options](attachments/791314480/791314498)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Git
Repository Integration Options.png](attachments/791314480/791314501.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200317-233118.png](attachments/791314480/791314504.png)
(image/png)  
