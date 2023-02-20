# Pre-installation checklist

Here’s a checklist of major steps you should have completed before
starting your installation. See also
<a href="MettleCI_For_DevOps_-_Technical_Prerequisites"
data-linked-resource-id="373424141" data-linked-resource-version="91"
data-linked-resource-type="page">MettleCI technical prerequisites</a>.

<table class="confluenceTable" data-layout="default"
data-local-id="b064b857-29c7-46d1-989d-aa0e78f00895">
<tbody>
<tr class="header">
<th class="confluenceTh"><p><strong>Section</strong></p></th>
<th class="confluenceTh"><p><strong>Notes</strong></p></th>
</tr>
&#10;<tr class="odd">
<td class="confluenceTd"><p>Infrastructure</p></td>
<td class="confluenceTd"><ol>
<li><p>Browse the diagrams which describe the most common <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1631977495/Deployment+Topologies"
rel="nofollow">DataStage installation topologies</a>. You can use the
guidance on each page to understand The only piece of new infrastructure
you’re likely to require is a dedicated <a href="The_Mettle_Agent_Host"
data-linked-resource-id="2327019539" data-linked-resource-version="4"
data-linked-resource-type="page">MettleCI Agent Host</a> (see the
explanation of all the components involved in a DataStage environment
using MettleCI <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1770520622/A+Summary+of+MettleCI+Components#MettleCI-Agent-Host"
rel="nofollow">here</a>).</p></li>
</ol></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>Environmental Configuration</p></td>
<td class="confluenceTd"><ol>
<li><p>You have chosen the port(s) MettleCI Workbench will run on.
Defaults are 8080 (HTTP) or 8443 (HTTPS)</p></li>
<li><p>Your <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1109491891/MettleCI+-+Firewall+Rules+Security"
rel="nofollow">firewall configuration</a> permits users to access
MettleCI Workbench - running on your chosen port(s) - from their Client
workstations.</p></li>
<li><p>Any endpoint security management software should be configure to
permit the execution of the software detailed in the section
below.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>MettleCI License</p></td>
<td class="confluenceTd"><ol>
<li><p>You have a valid, current MettleCI license file available to you,
for which you may require you DataStage Engine tier’s MAC address. See
our <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/2326822920/Finding+a+Host%27s+MAC+Address"
data-linked-resource-id="2326822920" data-linked-resource-version="5"
data-linked-resource-type="page">guide to finding this</a> on your
system.</p></li>
</ol></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>OpenJDK</p></td>
<td class="confluenceTd"><ol>
<li><p>See <a href="Prerequisite_Java_Installation"
data-linked-resource-id="488800406" data-linked-resource-version="24"
data-linked-resource-type="page">Prerequisite Java
Installation</a>.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p>MettleCI Software</p></td>
<td class="confluenceTd"><ol>
<li><p>Download <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/2244149314/MettleCI+IBM+OEM+Release+History"
data-linked-resource-id="2244149314" data-linked-resource-version="13"
data-linked-resource-type="page">the latest release</a> of the MettleCI
distribution.</p></li>
<li><p>Ensure the following applications (WINDOWS) or RPM packages
(UNIX) may be invoked using <code>Administrator</code> (WINDOWS) or
<code>root</code> (UNIX) privileges on the relevant host:</p></li>
</ol>
<ul>
<li><p><strong>MettleCI Workbench installer on your DataStage
Engine:</strong></p>
<ul>
<li><p>WINDOWS
<code>dm-mettleci-workbench-n.n-nnn-setup.exe</code></p></li>
<li><p>UNIX
<code>dm-mettleci-workbench-n.n-nnn.noarch.rpm</code></p></li>
</ul></li>
<li><p><strong>MettleCI Unit Test Harness installer on your DataStage
Engine:</strong></p>
<ul>
<li><p>WINDOWS
<code>dm-unittest-harness-x.x-xxx-setup.exe</code></p></li>
<li><p>UNIX <code>dm-unittest-harness-x.x-xxx.noarch.rpm</code></p></li>
</ul></li>
<li><p><strong>MettleCI DataStage Designer menu installer on your
DataStage Client Workstation:</strong></p>
<ul>
<li><p>WINDOWS <code>MCI_Setup.exe</code> (This is <a
href="Integrating_MettleCI_Workbench_and_DataStage_Designer_on_Windows"
data-linked-resource-id="454623235" data-linked-resource-version="15"
data-linked-resource-type="page">downloaded from the MettleCI Workbench
application</a> once it has been installed)</p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200521-050334.png](attachments/760676393/762216476.png)
(image/png)  
