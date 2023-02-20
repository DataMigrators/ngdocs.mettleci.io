# Creating a Local Compliance Rule Git Repository

MettleCI Compliance Rules are delivered as a zip file containing a
ready-to-use Local Git repository. This means you can install and run
Compliance Rules simply by unzipping the file to your DataStage Engine’s
file system, without necessarily requiring a Git server to host a Remote
repository. This is a good way to get started quickly with executing
Compliance from within the MettleCI Workbench, allowing to you move
towards using a Remote repository when you’re ready. In the meantime,
the use of a Local repository imposes some limitations:

-   You shouldn’t use the use the Local repository as a source of
    Compliance Rules outside of the MettleCI Workbench context. In
    particular, you shouldn’t attempt to reference a Local repository in
    your build (CI/CD) pipeline (it’ll work, but it’s not good
    practice).

-   The use of a Local Compliance repository does not easily support the
    collaborative development or maintenance of Compliance rules. For
    that purpose it is recommended to host your Compliance repository as
    a Remote Git repository served by a Git server.

For these reasons we recommended you always use Remote Git repositories
for managing your Compliance rules.

# Creating your Local Repository

You can configure your local repository from your O/S command line. The
example below is for UNIX-based systems:

``` bash
# Start in your MettleCI home directory (default: /opt/dm/mci/)
$> pwd
/opt/dm/mci

# SCP/FTP the compliance zip file from your download media to this directory 
$> ls -l dm-compliance-rules-59.zip

-rw-r--r-- 1 root root 38578 Jan 13 11:41 dm-compliance-rules-59.zip

# Unzip it.  This will create a subdirectory /opt/dm/mci/compliance.
$> unzip dm-compliance-rules-59.zip
Archive:  dm-compliance-rules-59.zip
   creating: compliance/
  inflating: compliance/One Dataflow.sjb.grm
  inflating: compliance/rules.cfg
  inflating: compliance/Link Sort.pjb.grm
  inflating: compliance/Range Lookup.pjb.grm
   creating: compliance/.git/
# etc.

$> ls -l compliance/
total 128
-rw-rw-r-- 1 ec2-user dstage  1478 Jan  8 15:59 Adjacent Transformers.pjb.grm
-rw-rw-r-- 1 ec2-user dstage  3246 Jan  8 15:59 CCMigrateTool Stages.pjb.grm
-rw-rw-r-- 1 ec2-user dstage  2227 Jan  8 15:59 CCMigrateTool Stages.sjb.grm
# etc.

# The compliance directory is a local Git repository of default Compliance Rules
$> cd compliance
$> git status
# On branch master
#
# Initial commit
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#       Adjacent Transformers.pjb.grm
#       CCMigrateTool Stages.pjb.grm
#       CCMigrateTool Stages.sjb.grm
# etc.

# You're ready to go!  Next steps are:
# 1. Configure your MettleCI Workbench project(s) to use your Local Repository
# 2. Begin modifying your Compliance repository to meet your team's needs.  
```

# Configuring MettleCI Workbench to use your Local Repository

To set MettleCI to use a local Compliance repository for your DataStage
project you just need to point Workbench to the appropriate repository
directory. Under your user icon (top right) in Workbench select **Manage
Projects** , edit the settings of the relevant project and for
**Compliance Repository** set the **URL** field to an appropriate value
following the examples below:

`file://C:\MettleCI\compliance\.git` WINDOWS

`file:///opt/dm/mci/compliance/.git` UNIX

Note the three forward slashes after `file:` in the Unix example. Two
are required for the protocol specification (`file://`) and one
referencing the root of the host filesystem (`/`).

In all cases leave the **Branch** field blank (uses default branch,
`master`) and the **Path** field empty.

<img src="attachments/506953729/1988755457.png?width=170"
class="image-left" loading="lazy"
data-image-src="attachments/506953729/1988755457.png" data-height="612"
data-width="730" data-unresolved-comment-count="0"
data-linked-resource-id="1988755457" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="image-20210907-013522.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="506953729"
data-linked-resource-container-version="16"
data-media-id="7f11d810-e5d9-4b72-b455-16014853777a"
data-media-type="file" width="170" />

------------------------------------------------------------------------

# See also

When you’re ready to collaborate on Compliance Rule development, or just
what to have better governance over your Compliance Rules, you may
<a href="Promoting_a_local_Git_repository_to_a_remote_repository"
data-linked-resource-id="507019277" data-linked-resource-version="11"
data-linked-resource-type="page">migrate your Local Git repository to a
shared Remote Git repository</a>.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210520-064719.png](attachments/506953729/1739259958.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210907-013507.png](attachments/506953729/1988722689.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20210907-013522.png](attachments/506953729/1988755457.png)
(image/png)  
