# Installing or Upgrading Individual MettleCI CLI Commands

The MettleCI Command Line Interface itself offers no useful
functionality, and simply acts as a shell for the invocation of
functionality provided by MettleCI CLI **Plugins**. Which plugin
provides which commands are listed in the <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/458850547/MettleCI+Command+Line+Reference"
data-linked-resource-id="458850547" data-linked-resource-version="58"
data-linked-resource-type="page">MettleCI CLI Plugin Reference</a>. The
default MettleCI CLI that a user downloads contains the latest version
of all the Mettle Plugins, but there may be times when you wish to
update a plugin, or install a new plugin which provides new
functionality.

# Installing New Plugins

Installing MettleCI Command Line Interface Plugins is as simple as
placing them in the plugins sub-directory of your CLI installation
directory. Note that plugins are loaded when the CLI is started, so
you’ll need to exit and restart any running CLI sessions before any
newly installed plugins are recognised.

<img src="attachments/488865967/784138399.png?width=340"
class="image-center" loading="lazy"
data-image-src="attachments/488865967/784138399.png" data-height="314"
data-width="795" data-unresolved-comment-count="0"
data-linked-resource-id="784138399" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="image-20200602-133558.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="488865967"
data-linked-resource-container-version="9"
data-media-id="dd9d483f-e5dc-4c2c-9afc-7a980460dae6"
data-media-type="file" width="340" />

# Updating Plugins

Upgrading a plugin is as simple as downloading the upgraded plugin JAR
file and placing in the plugins sub-directory of your CLI installation
directory.

**Do not have two versions of the same plugin installed at the same
time.**

Plugins are released as JAR files with a filename that indicates their
major, minor, and revision number in the form `n.n-nnn`. When installing
an upgraded version of a plugin you should remove the version of the
plugin you’re replacing from the `plugins` directory.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200602-133558.png](attachments/488865967/784138399.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200602-133558.png](attachments/488865967/784367806.png)
(image/png)  
