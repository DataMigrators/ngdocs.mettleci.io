# Upgrading MettleCI installations to Workbench build 1165 or later

**SUMMARY**

MettleCI Workbench build **1165** (released on 10th March, 2021)
introduces some breaking changes which will require the execution of
some manual steps to restore your MettleCI environment’s
previously-configured interface to a work item management system.

MettleCI Workbench installations prior to build 1165 were configured to
use a single work item management system when searching for issues
during Git commit operations. This presented a challenge where different
projects on a single DataStage Engine needed to reference different work
item management systems in their respective commit messages. This could
be the case when different DataStage teams sharing an engine tier want
to reference work items managed in different systems, or when an
organisation migrates from one work item management platform to another
(replacing Service Now with Jira, for example).

Workbench build 1165 (and later) provide the ability to define multiple
work item management systems in your Workbench instance, and then
associate each individual DataStage project with a one of those systems
as part of the <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1373339649/Registering+a+DataStage+Project+with+MettleCI"
data-linked-resource-id="1373339649" data-linked-resource-version="10"
data-linked-resource-type="page">project registration process</a>.

To get Workbench working correctly with the new capability, users of
MettleCI Workbench versions prior to 1165 will need to update their work
item management system connection details and define which work item
management system each DataStage project should use during Git commits.
Questions worth considering before proceeding are:

1.  How many work item management systems you wish to support?

2.  Which if those systems is the most commonly used, and hence should
    be the default for newly-<a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1373339649/Registering+a+DataStage+Project+with+MettleCI"
    data-linked-resource-id="1373339649" data-linked-resource-version="10"
    data-linked-resource-type="page">registered</a> DataStage projects?

# The Upgrade Process

MettleCI build 1165+ is delivered with a single work item management
system definition, referred to by its label ‘**Default Generic Issue
Manager**’. When new DataStage projects are registered with MettleCI
Workbench they are automatically associated with this work item
management system by default. Most users will find it most convenient to
edit the details of this entry to match their most commonly used work
item management system. To do this follow these steps:

1.  Upgrade your MettleCI installation to the 1165 or later build using
    the instructions appropriate to your platform (whether
    <a href="Installing_or_Upgrading_Workbench_on_Unix"
    data-linked-resource-id="455802915" data-linked-resource-version="55"
    data-linked-resource-type="page">Unix</a> or
    <a href="Installing_or_Upgrading_Workbench_on_Windows"
    data-linked-resource-id="455770155" data-linked-resource-version="20"
    data-linked-resource-type="page">Windows</a>). Be sure to restart
    your Workbench service.

2.  Log in to the MettleCI Workbench as a user with DataStage
    Administrator privileges.

3.  Go to **User → Issue Management**. If you don’t see this menu (or
    any other options described below) perform a force refresh of your
    browser as described on <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/488800735/A+Workbench+update+doesn+t+appear+to+have+installed"
    rel="nofollow">this page</a>.

4.  You'll be presented with the a list of registered work item
    management systems. Initially you will have only the single default
    available.

    <img src="attachments/1506345010/1506902122.png" class="image-center"
    loading="lazy" data-image-src="attachments/1506345010/1506902122.png"
    data-height="255" data-width="1716" data-unresolved-comment-count="0"
    data-linked-resource-id="1506902122" data-linked-resource-version="2"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="image-20210120-030257.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="1506345010"
    data-linked-resource-container-version="13"
    data-media-id="f9d8e45f-1ade-4b4c-b483-345c52735384"
    data-media-type="file" />

5.  Click the **Edit** (pencil) icon next to the system whose details
    you wish to edit.

    <img src="attachments/1506345010/1506902128.png" class="image-center"
    loading="lazy" data-image-src="attachments/1506345010/1506902128.png"
    data-height="634" data-width="1550" data-unresolved-comment-count="0"
    data-linked-resource-id="1506902128" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="image-20210120-033341.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="1506345010"
    data-linked-resource-container-version="13"
    data-media-id="705d369f-7b2a-401c-8600-e5376a55c3c8"
    data-media-type="file" />

6.  From the Issue Management Type drop down list select the default
    (most commonly used) work item management platform your DataStage
    projects

7.  Edit the default name to something more descriptive

8.  Enter the values specific to your chosen technology. Note:

    1.  Users with the appropriate permissions who are having trouble
        finding their correct configuration values can SSH to their
        DataStage Engine tier and derive the appropriate values from the
        `config.yml` file in the MettleCI Home directory. For example:

        ``` bash
        $> cd /opt/dm/mci/

        $> # Get your previously configured work item management settings
        $> cat config.yml
        issueManagement: JIRA

        jira:
           
           url: http://demo.mettleci.io/jira
           consumerKey: "BC847C98-FDAF-48A0-87B1-7B4B8888AACC"
           consumerSecret: /opt/dm/mci/jira_privatekey.pcks8

        ...
        ```

    2.  double-quoted values in your `config.yml` should have the
        double-quotes removed when entered into the Workbench interface.

    3.  Where your `config.yml` references private key files (e.g.
        `/opt/dm/mci/jira_privatekey.pcks8`) you actually need to
        retrieve the *contents* of those files for the Edit Issue
        Management Service form, **not** the file name specified in your
        `config.yml`. For example:

        ``` bash
        $> # Get the contents of your previously configured private key
        $> cat /opt/dm/mci/jira_privatekey.pcks8
        -----BEGIN PRIVATE KEY-----

        MIIp98nymta3498my4t398pmt43c98mt43gserooICAQDrp4tl//9kc7k6
        6SDVlophmkvkwmBuvPRCegVPIKMde2H5xcyAFpnibZC61+Tfo/NgijZAUd08C/Jn
        .....
        aW5dZNuXf5bfY4bujqixoVoUwM3eNSFe

        -----END PRIVATE KEY-----
        ```

9.  Click **Submit** when you’re done. You’ll now see your default work
    item management system listed with its specified type (in this case,
    JIRA).

<img src="attachments/1506345010/1512767512.png?width=680"
class="image-center" loading="lazy"
data-image-src="attachments/1506345010/1512767512.png" data-height="550"
data-width="3360" data-unresolved-comment-count="0"
data-linked-resource-id="1512767512" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="image-20210311-022750.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="1506345010"
data-linked-resource-container-version="13"
data-media-id="32b23a72-0c04-4c17-9659-804f3770ff1a"
data-media-type="file" width="680" />

All of your currently registered projects will now use this Jira
configuration by default, and you can choose to move to another issue
management service or server by creating another configuration. To
create additional issue management services simply click the **\[+\]**
icon in the top right hand corner.

# See also

-   <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1349419012/Registering+Issue+Management+Systems+in+Workbench"
    data-linked-resource-id="1349419012" data-linked-resource-version="13"
    data-linked-resource-type="page">Registering Issue Management Systems in
    Workbench</a>

-   <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1507328025/Integrating+Atlassian+Jira+with+MettleCI+Workbench"
    data-linked-resource-id="1507328025" data-linked-resource-version="28"
    data-linked-resource-type="page">Integrating Atlassian Jira with
    MettleCI Workbench</a>

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210120-025552.png](attachments/1506345010/1506902116.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210120-030257.png](attachments/1506345010/1506902170.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210120-033341.png](attachments/1506345010/1506902128.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210120-034008.png](attachments/1506345010/1506902134.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20201106-044950.png](attachments/1506345010/1506902140.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2020-11-23 at 2.00.05
pm.png](attachments/1506345010/1506902146.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2020-11-23 at 2.04.54
pm.png](attachments/1506345010/1506902152.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Screen
Shot 2020-11-23 at 3.53.18
pm.png](attachments/1506345010/1506902158.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210120-051558.png](attachments/1506345010/1506902164.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210120-030257.png](attachments/1506345010/1506902122.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210311-022750.png](attachments/1506345010/1512767512.png)
(image/png)  
