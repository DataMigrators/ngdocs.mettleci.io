# Virtual Desktop Example Topology

An example topology for an environment using the following technologies:

-   Citrix desktop virtualisation

-   Atlassian Bitbucket Git repository

-   Atlassian Jira work item management platform

-   Jenkins build tool

# Components connections

<table class="confluenceTable" data-layout="default"
data-local-id="acb1419a-613f-4dca-a606-4113f565d35f">
<tbody>
<tr class="header">
<th class="confluenceTh"><p><strong>#</strong></p></th>
<th class="confluenceTh"><p><strong>Description</strong></p></th>
<th class="confluenceTh"><p><strong>Access notes</strong></p></th>
</tr>
&#10;<tr class="odd">
<td class="confluenceTd"><p>1</p></td>
<td class="confluenceTd"><p>The Citrix client running on your Developer
Workstation presents a virtualised DataStage Designer client to your
Developer</p></td>
<td class="confluenceTd"><p>Dependent upon your Citrix configuration.
See the <a
href="https://docs.citrix.com/en-us/tech-zone/build/tech-papers/citrix-communication-ports.html"
rel="nofollow">Citrix documentation</a>.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>2</p></td>
<td class="confluenceTd"><p>Depending upon your Citrix configuration,
the MettleCI menu items in the virtualised DataStage client invoke the
MettleCI Workbench interface in a virtualised browser window served by
Citrix, or…</p></td>
<td class="confluenceTd"><p>The browser running on your Citrix DataStage
Client can access the MettleCI Workbench Service using a port that <a
href="Configuring_MettleCI_Workbench_to_use_a_Custom_Port_Number"
data-linked-resource-id="588972035" data-linked-resource-version="8"
data-linked-resource-type="page">you choose and configure</a>.</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>3</p></td>
<td class="confluenceTd"><p>.. in a native browser window on your
Developer Workstation. In either case this communicates (over ports you
configure) with the MettleCI Workbench Service running on your DataStage
Engine.</p></td>
<td class="confluenceTd"><p>The browser running natively on your local
machine can access the MettleCI Workbench Service using a port that <a
href="Configuring_MettleCI_Workbench_to_use_a_Custom_Port_Number"
data-linked-resource-id="588972035" data-linked-resource-version="8"
data-linked-resource-type="page">you choose and configure</a>.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>4</p></td>
<td class="confluenceTd"><p>Your work item management tool (e.g.
Atlassian Jira) can be accessed from your Developer Workstation by
configuring network access to the the relevant host ports.</p></td>
<td class="confluenceTd"><p>The Jira user interface accessed from your
browser <a
href="https://confluence.atlassian.com/adminjiraserver/changing-jira-application-tcp-ports-938847762.html"
rel="nofollow">configured to use any port you wish</a>.</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>5</p></td>
<td class="confluenceTd"><p>Your Git tool (e.g. Atlassian Bitbucket) can
be accessed from your Developer Workstation by configuring network
access to the the relevant host ports.</p></td>
<td class="confluenceTd"><p>Your Git tool is accessed using ports
configured within that tool. For example, you can configure the ports
for <a
href="https://confluence.atlassian.com/bitbucketserverkb/which-ports-does-bitbucket-server-listen-on-and-what-are-they-used-for-806029586.html"
rel="nofollow">Atlassian Bitbucket Server</a>.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>6</p></td>
<td class="confluenceTd"><p>Your build tool (e.g. Jenkins) can be
accessed from your Developer Workstation by configuring network access
to the the relevant host ports.</p></td>
<td class="confluenceTd"><p>The Jenkins Controller and Agents
communicate using <a
href="https://www.jenkins.io/doc/book/security/services/"
rel="nofollow">a set of default ports</a> which can be modified through
the <a
href="https://www.jenkins.io/doc/book/system-administration/reverse-proxy-configuration-with-jenkins/"
rel="nofollow">use of a reverse proxy</a>.</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>7</p></td>
<td class="confluenceTd"><p>The virtualised DataStage Designer client
running on Citrix will need regular access to DataStage Service and
Engine tiers, as documented by IBM.</p></td>
<td class="confluenceTd"><p>The DataStage Client tier running on your
Citrix environment uses <a
href="https://www.ibm.com/docs/en/iis/11.7?topic=computers-configuring-your-network"
rel="nofollow">standard IBM DataStage ports</a>.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>8</p></td>
<td class="confluenceTd"><p>Your MettleCI Workbench will need network
access to your Jira server to perform Work item lookup from the
Workbench’s Git Commit page.</p></td>
<td class="confluenceTd"><p>The Jira API uses the same as is used to
access the Jira user interface from your browser, <a
href="https://confluence.atlassian.com/adminjiraserver/changing-jira-application-tcp-ports-938847762.html"
rel="nofollow">whatever your organization has configured that to
be</a>.</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>9</p></td>
<td class="confluenceTd"><p>Your MettleCI Workbench will need network
access to your Bitbucket server to commit work to your Git
repositories.</p></td>
<td class="confluenceTd"><p>Workbench accesses your Git repositories
using the references they publish - usually via HTTPS (port 443) or SSH
(port 22).</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>10</p></td>
<td class="confluenceTd"><p>The Jenkins Controller running on your
Jenkins host will need network access to your Bitbucket instance to poll
for, and retrieve, changes to your Git repositories</p></td>
<td class="confluenceTd"><p>TBC</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>11</p></td>
<td class="confluenceTd"><p>The Jenkins Controller running on your
Jenkins host will need network access to the Jenkins Agent running on
the MettleCI Agent Host.</p></td>
<td class="confluenceTd"><p>The Jenkins Controller and Agents
communicate with reach other using <a
href="https://www.jenkins.io/doc/book/security/services/"
rel="nofollow">a set of default ports</a> which can be modified through
the <a
href="https://www.jenkins.io/doc/book/system-administration/reverse-proxy-configuration-with-jenkins/"
rel="nofollow">use of a reverse proxy</a>.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>12</p></td>
<td class="confluenceTd"><p>The Jenkins Agent will require access to the
Bitbucket repository in order to checkout newly-committed artefacts for
deployment, as well as accessing the Compliance repository to fetch its
constituent rules.</p></td>
<td class="confluenceTd"><p>The Jenkins Agent accesses your Git
repositories using the references they publish - usually via HTTPS (port
443) or SSH (port 22).</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>13</p></td>
<td class="confluenceTd"><p>The Jenkins Agent, MettleCI CLI, and
DataStage Client programs running on the MettleCI Agent Host will
require network access to the DataStage Service and Engine
tiers.</p></td>
<td class="confluenceTd"><p>The DataStage Client tier running on your
Citrix environment uses <a
href="https://www.ibm.com/docs/en/iis/11.7?topic=computers-configuring-your-network"
rel="nofollow">standard IBM DataStage ports</a>.</p>
<p>The MettleCI CLI will communicate with the DataStage host over SSH on
your specified port.</p></td>
</tr>
</tbody>
</table>

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Topology Citrix](attachments/2257911823/2257649673)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Topology Citrix.png](attachments/2257911823/2258370564.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Topology Citrix](attachments/2257911823/2258567169)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Topology Citrix.png](attachments/2257911823/2258599937.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Topology Citrix](attachments/2257911823/2258436097)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Topology Citrix.png](attachments/2257911823/2257682437.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259058697) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259353607.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2258829321) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259484675.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259419157) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259157011.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2258632735) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259484689.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2258862100) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2258862110.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259124268) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259058729.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2258894901) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259157037.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259124282) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259058739.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259124292) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259157047.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259157057) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2259157067.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2259451929) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2258894931.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2290909246) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2290909256.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2291499041) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2290843662.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2291499055) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2291007510.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2312634421) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2314010631.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2314108941) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2314010645.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2313715727) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2313486355.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2321678337) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2321219612.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2321219622) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2321416197.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2322366503) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2323021825.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2322890755) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2322759686.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology](attachments/2257911823/2257551373) (application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Citrix
Topology.png](attachments/2257911823/2258501637.png) (image/png)  
