# Standalone DataStage on Unix - Dedicated Agent Host

A Unix-based multi-tier DataStage environment where…

-   The MettleCI Workstation is installed on your DataStage Engine tier,
    and

-   The MettleCI Agent is installed on a dedicated Windows host

# Notes

-   The Information Server environment can be deployed using a 1-tier,
    2-tier, or 3-tier architecture. Common best practise places the
    Engine tier on a dedicated host, and the Services and Repository
    tiers together on a separate host.

-   The MettleCI Workbench Service runs (in this topology) on a
    Unix-based DataStage Engine tier. This is because this service
    requires a shared filesystem with the MettleCI Unit Test Harness
    which can only be installed on the Engine tier.

-   The MettleCI Agent host is a dedicated host reserved exclusively for
    use by your selected CI/CD build tool via the installed CD/CD agent.
    The MettleCI CLI is used by the CI/CD Agent to automate build and
    deployment activities. The MettleCI CLI and Agent need to be
    installed on a Windows host co-resident with a DataStage Client tier
    in order to enable the automation of the DataStage job compilation
    process, which requires the use of a Windows-based Client tier.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1633845302/1633845315.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1633845302/1633845318)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[windows-13475.png](attachments/1633845302/1633845321.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[red-hat.png](attachments/1633845302/1633845324.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064728.png](attachments/1633845302/1633845327.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-060008.png](attachments/1633845302/1633845330.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064722.png](attachments/1633845302/1633845333.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[DataStage on Unix Separate Agent](attachments/1633845302/2122842113)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[DataStage on Unix Separate
Agent.png](attachments/1633845302/2122874881.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[DataStage on Unix Separate Agent](attachments/1633845302/1631682974)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[DataStage on Unix Separate
Agent.png](attachments/1633845302/1631682980.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[aws_icon.png](attachments/1633845302/2326724627.png) (image/png)  
