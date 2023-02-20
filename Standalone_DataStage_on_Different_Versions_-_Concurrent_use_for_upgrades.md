# Standalone DataStage on Different Versions - Concurrent use for upgrades

This topology describes an environment featuring two DataStage
platforms:

1.  A traditional standalone DataStage environment on v11.5.0 (for
    example) referred to below as the **Legacy DataStage** environment,
    and

2.  A traditional standalone DataStage environment on v11.7.1 (for
    example) referred to below as the **Target DataStage** environment

Each environment has its own dedicated MettleCI Agent running on a
dedicated Windows host.

This topology is ideal for customers using MettleCI to upgrade between
different versions of Standalone DataStage. Customers upgrading to Cloud
Pak for Data should refer to <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1656815621"
data-linked-resource-id="1656815621" data-linked-resource-version="12"
data-linked-resource-type="page">Standalone DataStage and Cloud Pak
DataStage - Concurrent use for upgrades</a>.

# Connections

1.  Developer’s DataStage Designer Client to Legacy DataStage platform
    (using DataStage Multi-Client Manager, desktop virtualisation, or
    equivalent)

2.  Legacy Workbench service to Work Item Management (Work Item lookup
    on Workbench Commit page)

3.  Legacy Workbench service to Git (Compliance Clone, DataStage
    Commit/Push)

4.  Legacy build pipeline invokes MettleCI CLI activity on the Legacy
    build system agent

5.  Legacy build system agent uses MettleCI CLI to perform CI/CD
    operations on Legacy DataStage Development environment

6.  Legacy build system agent uses MettleCI CLI to perform CI/CD
    operations on Legacy non-development DataStage environments (e.g.
    QA, PROD)

7.  Developer’s DataStage Designer Client to Target DataStage platform
    (using DataStage Multi-Client Manager, desktop virtualisation, or
    equivalent)

8.  Target Workbench service to Work Item Management (Work Item lookup
    on Workbench Commit page)

9.  Target DataStage Workbench service to Git (Compliance Clone,
    DataStage Commit/Push)

10. Target build pipeline invokes MettleCI CLI activity on the Target
    build system agent

11. Target build system agent uses MettleCI CLI to perform CI/CD
    operations on Target DataStage Development environment

12. Target build system agent uses MettleCI CLI to perform CI/CD
    operations on Target non-development Target DataStage environments
    (e.g. QA, PROD)

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Uber
Topology 2.png](attachments/1984397313/1984397326.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Uber
Topology 2](attachments/1984397313/1984397329)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Uber Topology.png](attachments/1984397313/1984397332.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Uber Topology](attachments/1984397313/1984397335)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology](attachments/1984397313/1983479833)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology.png](attachments/1984397313/1983479837.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1983905814)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1983610911.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1983479846)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1983610921.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1984528391)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1984528401.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1985314817)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1985282051.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1982857422)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1985216515.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1986232340)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1984856100.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1986723848)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1986822147.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2](attachments/1984397313/1983447081)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Version
Upgrade Topology 2.png](attachments/1984397313/1983905809.png)
(image/png)  
