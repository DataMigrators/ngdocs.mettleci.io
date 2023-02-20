# Using Multiple MettleCI Agents

# Introduction

Many customers cannot use a single MettleCI Agent Host to communicate
with multiple DataStage environments due to organizational security
policies.

This page describes how multiple MettleCI Agents Host can be configured
when you need to segregate agent access by DataStage environment or
network zone.

Components featuring on this page are described in
<a href="A_Summary_of_MettleCI_Components"
data-linked-resource-id="1770520622" data-linked-resource-version="8"
data-linked-resource-type="page">MettleCI Topology Components</a>.

# A single MettleCI Agent Host for everything

This is the default (and simplest) topology to use when it’s permissible
for a single MettleCI Agent host to connect to every DataStage
environment and network zone.

# Separate MettleCI Agent Hosts per network zone

This topology is appropriate when it’s not permitted for a single
MettleCI Agent host to connect to every DataStage environment and
network zone. In particular, this topology is useful when a single
instance of a CI/CD Agent is not permitted to access non-Production and
Production environments/network zones.

# Separate MettleCI Agent Hosts per DataStage environment

This topology is appropriate when each DataStage environment requires
its own MettleCI Agent host, usually as a result of organizational
security policies.

# Configuring pipeline activity to the appropriate Agent host

The following links describe how various build tools provide support for
specifying which pipeline activities are assigned to which build
Agent/Runner.

-   **Azure DevOps:** <a
    href="https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/agents?view=azure-devops&amp;tabs=browser#capabilities"
    rel="nofollow">Azure Pipelines Agents - Azure Pipelines</a>

-   **Atlassian Bamboo:** <a
    href="https://confluence.atlassian.com/bamboo/agents-and-capabilities-289277114.html"
    rel="nofollow">Bamboo agents and capabilities</a>

-   **GitLab:** <a
    href="https://docs.gitlab.com/ee/ci/runners/#use-tags-to-limit-the-number-of-jobs-using-the-runner"
    rel="nofollow">Configuring runners in GitLab</a>

-   **Jenkins:**
    <a href="https://www.jenkins.io/doc/book/using/using-agents/"
    rel="nofollow">Using Jenkins agents</a>

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[DataStage on Unix Separate
Agent.png](attachments/1766817793/1766817806.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[DataStage on Unix Separate Agent](attachments/1766817793/1766817809)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064722.png](attachments/1766817793/1766817812.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-060008.png](attachments/1766817793/1766817815.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210421-064728.png](attachments/1766817793/1766817818.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[red-hat.png](attachments/1766817793/1766817821.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[windows-13475.png](attachments/1766817793/1766817824.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology](attachments/1766817793/1766817827)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Default
Deployment Topology.png](attachments/1766817793/1766817830.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agents](attachments/1766817793/1767014415)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agents.png](attachments/1766817793/1767178249.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agents](attachments/1766817793/1767211011)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agents.png](attachments/1766817793/1767211017.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts 1](attachments/1766817793/1770520692)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts
1.png](attachments/1766817793/1770061913.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2](attachments/1766817793/1770651651)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2.png](attachments/1766817793/1770487834.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2](attachments/1766817793/1770324078)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2.png](attachments/1766817793/1770553409.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Single
MettleCI Agent Host](attachments/1766817793/1770389552)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Single
MettleCI Agent Host.png](attachments/1766817793/1770061834.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts 1](attachments/1766817793/1770061923)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts
1.png](attachments/1766817793/1770618967.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts 1](attachments/1766817793/1770848319)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts
1.png](attachments/1766817793/1770848329.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts 1](attachments/1766817793/2326921249)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts
1.png](attachments/1766817793/2325774379.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2](attachments/1766817793/2238021661)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2.png](attachments/1766817793/2238316551.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2](attachments/1766817793/2327576589)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2.png](attachments/1766817793/2327314467.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts 1](attachments/1766817793/1770356743)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Multiple MettleCI Agent Hosts
1.png](attachments/1766817793/1770323979.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2](attachments/1766817793/1770389533)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[MettleCI Agent Hosts 2.png](attachments/1766817793/1770389538.png)
(image/png)  
