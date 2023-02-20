# Installing or Upgrading Workbench on Windows

-   [Manual
    Installation](#InstallingorUpgradingWorkbenchonWindows-ManualInstallation)
-   [Automated
    Installation](#InstallingorUpgradingWorkbenchonWindows-AutomatedInstallation)
-   [Post-installation](#InstallingorUpgradingWorkbenchonWindows-Post-installation)
-   [Uninstall
    Workbench](#InstallingorUpgradingWorkbenchonWindows-UninstallWorkbench)
-   [Upgrading or Downgrading
    Workbench](#InstallingorUpgradingWorkbenchonWindows-UpgradingorDowngradingWorkbench)

The MettleCI Workbench is browser-based application which is served from
a lightweight agent typically (but not necessarily) residing on your
Development environment’s DataStage Engine tier.

Before installing MettleCI Workbench you will need to perform a
<a href="Prerequisite_Java_Installation"
data-linked-resource-id="488800406" data-linked-resource-version="24"
data-linked-resource-type="page">pre-installation Java update</a> to
make sure you Java environment is compatible with MettleCI.

## Manual Installation

1.  Download the latest MettleCI Workbench zip distributable from the
    <a href="http://software.mettleci.io/" rel="nofollow">MettleCI software
    website</a>.

2.  Start the Windows installer and click **Next \>**

    <img src="attachments/455770155/2238480482.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770155/2238480482.png"
    data-height="384" data-width="495" data-unresolved-comment-count="0"
    data-linked-resource-id="2238480482" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Workbench Install - Welcome.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770155"
    data-linked-resource-container-version="20"
    data-media-id="a1d0e18b-25b8-4e33-91df-21b2ba8acff2"
    data-media-type="file" />

3.  Specify the location where Workbench should be installed (we
    recommend leaving this as the supplied default) and click **Next
    \>**

    <img src="attachments/455770155/2239397891.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770155/2239397891.png"
    data-height="385" data-width="497" data-unresolved-comment-count="0"
    data-linked-resource-id="2239397891" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Workbench Install - Location.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770155"
    data-linked-resource-container-version="20"
    data-media-id="ddf4b2f2-bff8-4a6e-97b7-59e75ebcba2b"
    data-media-type="file" />

4.  Enter the location of your java executable (java.exe) and click
    **Next \>**

    <img src="attachments/455770155/2239266823.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770155/2239266823.png"
    data-height="385" data-width="498" data-unresolved-comment-count="0"
    data-linked-resource-id="2239266823" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Workbench Install - Java Path.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770155"
    data-linked-resource-container-version="20"
    data-media-id="365fb51d-bcd6-4dd1-9ff0-cec5eb2652d9"
    data-media-type="file" />

    Ensure you use the Ellipsis button ('…') to find your Java path and
    insert in correctly into the text field.

5.  Installation will only take a few seconds, then click **Next \>**

    <img src="attachments/455770155/2238873613.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770155/2238873613.png"
    data-height="380" data-width="495" data-unresolved-comment-count="0"
    data-linked-resource-id="2238873613" data-linked-resource-version="2"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Workbench Install - Installing.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770155"
    data-linked-resource-container-version="20"
    data-media-id="9f88633b-e867-4a34-a665-4190787ceb22"
    data-media-type="file" />

6.  Click **Finish** when installation is complete

    <img src="attachments/455770155/2238480492.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770155/2238480492.png"
    data-height="386" data-width="496" data-unresolved-comment-count="0"
    data-linked-resource-id="2238480492" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Workbench Install - Finish.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770155"
    data-linked-resource-container-version="20"
    data-media-id="d600967c-a268-43bb-9da9-d74fb774bac9"
    data-media-type="file" />

7.  Open the Services application and verify that the Workbench service
    has been installed and configured to start automatically.

    <img src="attachments/455770155/2239365136.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770155/2239365136.png"
    data-height="50" data-width="993" data-unresolved-comment-count="0"
    data-linked-resource-id="2239365136" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Workbench Install - Service.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770155"
    data-linked-resource-container-version="20"
    data-media-id="f84863a8-8a6d-4fbc-af9a-b7a393927b8f"
    data-media-type="file" />

## Automated Installation

The installation of MettleCI Workbench version 1499 and later can be
automated via the `/S` option:

``` java
Usage: start "" /wait dm-mettleci-workbench-1.0-1449-setup.exe /S /mcihome <MettleCI Home> /javaexec <path/to/java.exe>
```

Sample output:

``` java
C:\>start "" /wait dm-mettleci-workbench-1.0-1449-setup.exe /S /mcihome C:\dm\mci /javaexec "C:\Program Files\Java\jdk8u332-b09\bin\java.exe"

MettleCI Workbench installation completed

C:\>echo %errorlevel%
0
```

## Post-installation

1.  Configure your MettleCI environment by opening the following URL in
    your browser: `http://[SERVER_URL]:8080`. If you're running on the
    Windows host serving the Workbench application you can use
    `http://localhost:8080`.

2.  Follow the prompts provided by the <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/459997264/Configuring+MettleCI+Workbench"
    rel="nofollow">MettleCI Setup Wizard</a>.

## Uninstall Workbench

You can uninstall or re-install the MettleCI Workbench by re-running the
same installer used to originally install it.

## Upgrading or Downgrading Workbench

You can upgrade (or downgrade!) MettleCI Workbench by downloading and
running a different version of the installer from the MettleCI software
website.

In order for the upgrade to succeed, you **must** stop the MettleCI
Workbench service (using the Windows Services Manager) **before** you
run the installer. The Workbench installer should start the Workbench
service up again once the process is complete. If it fails to re-start
you can start it manually in the Windows Services Manager.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20191030-061015.png](attachments/455770155/459735133.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20191030-061446.png](attachments/455770155/459735140.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.58.14 pm.png](attachments/455770155/463732778.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.45.14 pm.png](attachments/455770155/463765558.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.56.32 pm.png](attachments/455770155/463765563.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.38.32 pm.png](attachments/455770155/463732783.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.38.22 pm.png](attachments/455770155/464420979.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 4.11.01 pm.png](attachments/455770155/463798335.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 4.50.26 pm.png](attachments/455770155/463798340.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.37.21 pm.png](attachments/455770155/463798345.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.38.10 pm.png](attachments/455770155/463831096.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.47.06 pm.png](attachments/455770155/463732788.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.46.39 pm.png](attachments/455770155/463765573.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.34.33 pm.png](attachments/455770155/463732793.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.34.23 pm.png](attachments/455770155/463831101.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.46.39 pm.png](attachments/455770155/463765592.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2019-11-20 at 3.38.22 pm.png](attachments/455770155/463765568.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200408-113417.png](attachments/455770155/671678485.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200408-113427.png](attachments/455770155/673447947.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200408-113536.png](attachments/455770155/671481876.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200408-113615.png](attachments/455770155/671481886.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install - Welcome.png](attachments/455770155/2238480482.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install - Location.png](attachments/455770155/2239397891.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install - Java
Path.png](attachments/455770155/2239266823.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install -
Installing.png](attachments/455770155/2237792371.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install - Finish.png](attachments/455770155/2238480492.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install -
Installing.png](attachments/455770155/2238873613.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Workbench Install - Service.png](attachments/455770155/2239365136.png)
(image/png)  
