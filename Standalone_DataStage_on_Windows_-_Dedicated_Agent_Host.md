# Standalone DataStage on Windows - Dedicated Agent Host

A Windows-only multi-tier DataStage environment where…

-   The MettleCI Agent is installed

-   The MettleCI Workstation is installed on your Windows-based
    DataStage Engine tier, and

-   The MettleCI Agent is installed on a separate, dedicated Windows
    host

# Notes

-   The Information Server environment can be deployed using a 1-tier,
    2-tier, or 3-tier architecture. Common best practise places the
    Engine tier on a dedicated host, and the Services and Repository
    tiers together on a separate host.

-   The MettleCI Workbench Service runs (in this topology) on the
    Windows-based DataStage Engine tier. This is because this service
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

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-060008.png](attachments/1630928930/1631682821.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[red-hat.png](attachments/1630928930/1630928954.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[windows-13475.png](attachments/1630928930/1631682834.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064722.png](attachments/1630928930/1631944729.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-060008.png](attachments/1630928930/1631780911.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064728.png](attachments/1630928930/1630928948.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1630928930/1631649839)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1630928930/1630928967.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[windows-13475.png](attachments/1630928930/1631649855.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[red-hat.png](attachments/1630928930/1630928943.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1630928930/1631780959)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1630928930/1631682896.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[windows-13475.png](attachments/1630928930/1631813673.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1630928930/1631813702)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1630928930/1631813712.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1630928930/1635483649)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1630928930/1635516417.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1630928930/1631813678)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1630928930/1631649821.png)
(image/png)  
