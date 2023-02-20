# Standalone DataStage on Windows - Consolidated Agent Host

A Windows-only single-tier DataStage environment where…

-   The MettleCI Workstation is installed on your DataStage Engine tier,
    and

-   The MettleCI Agent is installed on your DataStage Engine tier.

**This topology may find some applications in POC or Demo environment,
but is <u>not recommended</u> for real-world DataStage development.**

# Notes

-   The Information Server environment (in this topology) has all tiers
    deployed on a single host. **This is not recommended as your
    DataStage Engine will have its licensed capacity reduced by the
    presence of other software components.**

-   The MettleCI Workbench Service runs (in this topology) on the
    Windows-based DataStage Engine tier. This is because this service
    requires a shared filesystem with the MettleCI Unit Test Harness
    which can only be installed on the Engine tier.

-   The MettleCI Agent host also shares the same host, and will have
    actions invoked by your selected CI/CD build tool via the installed
    CD/CD agent. The MettleCI CLI is used by the CI/CD Agent to automate
    build and deployment activities. The MettleCI CLI and Agent need to
    be installed on a Windows host co-resident with a DataStage Client
    tier in order to enable the automation of the DataStage job
    compilation process, which requires the use of a Windows-based
    Client tier.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[windows-13475.png](attachments/1633812481/1633812494.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1633812481/1633812497.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1633812481/1633812500)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[red-hat.png](attachments/1633812481/1633812503.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064728.png](attachments/1633812481/1633812506.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-060008.png](attachments/1633812481/1633812509.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064722.png](attachments/1633812481/1633812512.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent host](attachments/1633812481/1631780969)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent
host.png](attachments/1633812481/1631682906.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent host](attachments/1633812481/1631813726)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent
host.png](attachments/1633812481/1631813736.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent host](attachments/1633812481/1631780993)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent
host.png](attachments/1633812481/1631682934.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent host](attachments/1633812481/1635385345)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent
host.png](attachments/1633812481/1635385355.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent host](attachments/1633812481/1631780948)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Windows
Topology Cosolidated Agent
host.png](attachments/1633812481/1631780954.png) (image/png)  
