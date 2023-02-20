# Installing or Upgrading the Parallel Job Unit Test Harness on Windows

## Installation

1.  Download the latest Windows Installer
    (`dm-unittest-harness-X.X-X-setup.exe`). See
    <a href="Accessing_the_MettleCI_Software_Distribution"
    data-linked-resource-id="1565687876" data-linked-resource-version="1"
    data-linked-resource-type="page">Accessing the MettleCI Software
    Distribution</a>.

2.  Run `dm-unittest-harness-X.X-X-setup.exe` using a user with
    Administrator privileges

3.  Allow Unit Test Harness installer to make changes on the “User
    Account Control” screen

    <img src="attachments/455770211/639434865.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770211/639434865.png"
    data-height="360" data-width="452" data-unresolved-comment-count="0"
    data-linked-resource-id="639434865" data-linked-resource-version="2"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Step 1 - UAC.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770211"
    data-linked-resource-container-version="26"
    data-media-id="161e7a81-aa29-46ed-bf1e-1ec2ea970102"
    data-media-type="file" />

4.  Click next at the welcome screen

    <img src="attachments/455770211/642023433.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770211/642023433.png"
    data-height="389" data-width="506" data-unresolved-comment-count="0"
    data-linked-resource-id="642023433" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Step 2 - Welcome.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770211"
    data-linked-resource-container-version="26"
    data-media-id="2983c718-7870-4df0-8cd9-4ecdfa04bc71"
    data-media-type="file" />

5.  Select a location to install Unit Test Harness. This location is
    used for storing the uninstaller

    <img src="attachments/455770211/641990665.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770211/641990665.png"
    data-height="391" data-width="501" data-unresolved-comment-count="0"
    data-linked-resource-id="641990665" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Step 3 - Uninstaller Path.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770211"
    data-linked-resource-container-version="26"
    data-media-id="df89b289-16ee-47eb-956c-3e82448f5a79"
    data-media-type="file" />

6.  Select Mettle Home location. This screen will only appear if you
    install MettleCI Unit Test Harness before MettleCI Workbench

    <img src="attachments/455770211/642056193.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770211/642056193.png"
    data-height="386" data-width="488" data-unresolved-comment-count="0"
    data-linked-resource-id="642056193" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Step 4 - MCI Home.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770211"
    data-linked-resource-container-version="26"
    data-media-id="c0233197-ad84-4aa5-83ac-4aebdcfcc9d7"
    data-media-type="file" />

7.  Select DataStage Home directory.

    <img src="attachments/455770211/642023427.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770211/642023427.png"
    data-height="347" data-width="509" data-unresolved-comment-count="0"
    data-linked-resource-id="642023427" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Step 5 - DS Home.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770211"
    data-linked-resource-container-version="26"
    data-media-id="8c2d7d87-1d18-4da8-94f5-b34f9c0d0718"
    data-media-type="file" />

8.  Congratulations! Installation of MettleCI Unit Test Harness is now
    completed

    <img src="attachments/455770211/641990659.png" class="image-center"
    loading="lazy" data-image-src="attachments/455770211/641990659.png"
    data-height="383" data-width="493" data-unresolved-comment-count="0"
    data-linked-resource-id="641990659" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Step 6 - Uninstall Complete.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="455770211"
    data-linked-resource-container-version="26"
    data-media-id="7f9386a5-4673-4faf-9482-178a608ef03f"
    data-media-type="file" />

## Automated Installation

The installation of MettleCI Unit Test Harness version 1.0-353 and later
can be automated via the `/S` option:

``` java
Usage: 
start "" /wait <Unit Test Harness EXE file> /S /mcihome <MettleCI Home> /uthome <path/to.unittestharness> /dshome <path/to/datastage/home>
```

Sample output:

``` java
C:\>start "" /wait dm-unittest-harness-1.0-353-setup.exe /S /mcihome C:\dm\mci /uthome C:\dm\mci-unittest-harness /dshome C:\IBM\InformationServer\Server\DSEngine

MettleCI Unit Test Harness installation completed

C:\>echo %errorlevel%
0
```

## Enable MettleCI Unit Testing for DataStage projects

### To enable MettleCI Unit Testing for an existing DataStage project:

1.  Log into your development DataStage Engine(s) and navigate to your
    DataStage project folder. This would typically be:

    ``` java
    # Windows
    <DRIVE-LETTER>:\YOUR\PATH\TO\INFORMATION-SERVER-ROOT-FOLDER\Server\Projects\<Your Existing Project>
    or
    # Unix
    /your/path/to/InformationServer/Server/Projects/<Your Existing Project>
    ```

2.  Add the following Environment variable definition to the `DSParams`
    file under the `[EnvVarDefns]` section:

    ``` java
    DM_ENABLE_UNIT_TESTING\MettleCI\-1\List/Disabled//Test//Intercept/\Disabled\3\Project\Unit Testing Configuration\
    ```

### To enable MettleCI Unit Testing for all newly-created DataStage projects:

1.  Add the same entry described above to the DSParams for your
    ‘Template’ project, located in directory:

    ``` java
    <DRIVE-LETTER>:PATH\TO\INFORMATION-SERVER-ROOT-FOLDER\Server\Template
    ```

## Upgrade MettleCI Unit Testing Harness

To upgrade MettleCI Unit Testing Harness, is as simple as

-   Uninstall the old version

-   Install the new version

## Uninstall

The MettleCI UnitTest Harness uninstaller can be found under Windows
Start Menu. Click on it, and the wizard will guide you through the
uninstalling process.

<img src="attachments/455770211/634028223.png?width=102"
class="image-center" loading="lazy"
data-image-src="attachments/455770211/634028223.png" data-height="202"
data-width="325" data-unresolved-comment-count="0"
data-linked-resource-id="634028223" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="Uninstaller.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="455770211"
data-linked-resource-container-version="26"
data-media-id="2eb75cb4-c85c-4c3c-9456-60eac851335d"
data-media-type="file" width="102" />

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [1.
Computer Properties.png](attachments/455770211/564756487.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200214-124810.png](attachments/455770211/564723729.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200214-124924.png](attachments/455770211/564723737.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200214-125103.png](attachments/455770211/564592677.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
5 - DS Home.png](attachments/455770211/642023427.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
2 - Welcome.png](attachments/455770211/642023433.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
4 - MCI Home.png](attachments/455770211/642056193.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
1 - UAC.png](attachments/455770211/644120577.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
6 - Uninstall Complete.png](attachments/455770211/641990659.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
3 - Uninstaller Path.png](attachments/455770211/641990665.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Uninstaller.png](attachments/455770211/634028223.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Step
1 - UAC.png](attachments/455770211/639434865.png) (image/png)  
