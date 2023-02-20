# Installing or Upgrading Workbench on Unix

The MettleCI Workbench is browser-based application which is served from
a lightweight agent that resides on your DataStage **development**
environment’s Engine Tier.

In order to be able to install Workbench, you must be in a terminal
session either logged in as `root` or as a user that can `sudo` as
`root`.

Before installing MettleCI Workbench you will need to perform a
<a href="Prerequisite_Java_Installation"
data-linked-resource-id="488800406" data-linked-resource-version="24"
data-linked-resource-type="page">pre-installation Java update</a> to
make sure your Java environment is compatible with MettleCI.

# Pre-install steps if operating Workbench with a non-default user

By default, the MettleCI Workbench installer creates a new user called
`mciworkb` (if it doesn’t already exist) and sets its primary group to
`dstage`. All files created during the installation are owned by that
user and group.

If your environment requires you to use a different **user**, do the
following:

1.  As `root`, create an environment variable called `DM_WORKBENCH_USER`
    and set it to the name of the user you want to use.

If your environment requires you to use a different **group**, do the
following:

1.  As `root`, create an environment variable called `DM_DSTAGE_GROUP`
    and set it to the name of the group you want to use.

Use the `export` or `setenv` command (depending on which shell you’re
using) to set these environment variables. This ensures the the
installation processes are able to access them.

Avoid changing shells between the setting of environment variables and
the execution of installation commands.

# Installation / Upgrade

Before you perform an upgrade:

1.  Record the ownership and permissions for the MettleCI Home folder
    (*usually* `opt/dm/mci`)

2.  Back up the MettleCI Home folder.

1.  Download the latest RPM distributable (see
    <a href="Accessing_the_MettleCI_Software_Distribution"
    data-linked-resource-id="1565687876" data-linked-resource-version="1"
    data-linked-resource-type="page">Accessing the MettleCI Software
    Distribution</a>). The rest of these instructions assume this is
    located in your user’s HOME directory (~).

2.  From that directory, install the package from the shell of your
    DataStage Development Engine using Package Manager (RPM) (**NOTE**:
    For new installations this will create a user called `mciworkb`. A
    full set of changes that this process performs are listed in the <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/455802915/Installing+Workbench+on+Unix#Installation-Details"
    rel="nofollow">Installation Details</a> section below.)

    ``` java
    $> sudo rpm -U dm-mettleci-workbench-x.x-x.noarch.rpm
    $> # or for IBM AIX...
    $> sudo rpm -U dm-mettleci-workbench-x.x-x.noarch.rpm --nodeps --ignoreos
    ```

    … where **x.x.x** is the build version of the workbench you
    downloaded.

3.  Request a MettleCI licence from your Data Migrators contact, or
    request an evaluation licence from the
    <a href="https://software.mettleci.io/" rel="nofollow">MettleCI software
    download website</a>. The license will be installed during the first
    step of the Post Installation wizard process.

4.  Start the MettleCI Workbench service using the following command

    ``` java
    $> sudo service dm-mettleci-workbench start
    $> # or for AIX...
    $> mciworkbench.rc start
    ```

5.  Access the updated workbench using the relevant URL

6.  Perform a force refresh of your browser while accessing MettleCI
    Workbench using the instructions described <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/488800735/A+Workbench+update+doesn+t+appear+to+have+installed"
    rel="nofollow">here</a>.

if you receive a warning about cipher suites and protocols when
attempting to connect to Workbench for the first time then please see
the troubleshooting article <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1953366240/Workbench+login+fails+with+No+appropriate+protocol+error"
rel="nofollow">Workbench login fails with ‘No appropriate protocol’
error</a>.

# Verify your install/upgrade

1.  Verify your Workbench service is running:

    ``` bash
    $> sudo service dm-mettleci-workbench status
    $> # or for AIX...
    $> mciworkbench.rc status
    ```

2.  Opening the following URL in your browser:
    `http://[SERVER_URL]:8080`. and check the build number at the bottom
    of your Workbench browser screen. This should match the number in
    the number in the filename of the latest RPM distributable you
    downloaded and installed. If not, see the troubleshooting article <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/488800735/A+Workbench+update+doesn%27t+appear+to+have+installed"
    data-linked-resource-id="488800735" data-linked-resource-version="5"
    data-linked-resource-type="page">A Workbench update doesn't appear to
    have installed</a>.

## Post-installation

1.  Configure your MettleCI environment by opening the following URL in
    your browser: `http://[SERVER_URL]:8080` to start a wizard-based
    process.

2.  Follow the setup wizard to provide the various configuration
    information MettleCI requires.

# Uninstall Workbench

1.  You can uninstall the MettleCI Workbench package like any other RPM
    package:

    ``` java
    $> sudo rpm -e dm-mettleci-workbench
    ```

Warning: The `/opt/dm/mci/specs` and `/opt/dm/mci/reports` directories
are removed during the Uninstall. Make sure that backups of these
directories have been taken if required.

You'll need to use a similar command to
<a href="Installing_MettleCI_Unit_Test_Harness"
data-linked-resource-id="454393879" data-linked-resource-version="12"
data-linked-resource-type="page">uninstall the Unit Test Harness</a>
too.

# Downgrading Workbench

1.  If something goes wrong and you need to downgrade your version of
    MettleCI Workbench, without performing an uninstall/reinstall, you
    can use the following command:

    ``` java
    $> rpm -Uvh --oldpackage dm-mettleci-workbench-x.x-x.noarch.rpm
    ```

    … where **x.x.x** is the build version of the workbench you want to
    downgrade to.

------------------------------------------------------------------------

## Related pages

-   <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/718831996/Workbench+Installation+-+System+Administrator+Notes"
    data-linked-resource-id="718831996" data-linked-resource-version="3"
    data-linked-resource-type="page">Workbench Installation - System
    Administrator Notes</a>
