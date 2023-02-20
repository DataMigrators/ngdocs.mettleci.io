# Installing MettleCI CLI on Unix

Before installing MettleCI Command Line Interface you will need to
perform a <a href="Prerequisite_Java_Installation"
data-linked-resource-id="488800406" data-linked-resource-version="24"
data-linked-resource-type="page">pre-installation Java update</a> to
make sure your Java environment is compatible with MettleCI.

These instructions assume you have already obtained a MettleCI license
file. If necessary, you can reuse the license file used by MettleCI
Workbench. The installation of Workbench is **not** a prerequisite to
installing the MettleCI Command Line Interface.

## Installation

1.  Download the latest MettleCI Command Shell distribution package (see
    <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1565687876"
    rel="nofollow">Accessing the MettleCI Software Distribution</a>).
    Note that Data Migrators provide a single multi-platform
    distribution package which supports both Unix and Windows.

2.  As per the MettleCI Workbench installation, the `DM_WORKBENCH_USER`
    environment variable can be used to set file ownership to a user
    other than the default `mciworkb`.

3.  Open a shell and navigate to the location of your install images.
    Install the mettleCI CLI using Red Hat Package Manager (RPM)

    ``` java
    $> sudo rpm -U dm-mettleci-command-shell-x.x-x.noarch.rpm
    $> # or for IBM AIX...
    $> sudo rpm -U dm-mettleci-command-shell-x.x-x.noarch.rpm --nodeps --ignoreos
    ```

    … where **x.x.x** is the build version of the workbench you
    downloaded.

4.  If you are installing the MettleCI CLI alongside the MettleCI
    Workstation on a DataStage engine tier, you will already have a
    MettleCI license file which the Command Shell will use without need
    for configuration.

MettleCI Workbench requires the account running the Workbench Service to
have **read** and **write** permissions to the MettleCI License file.

## Linking to your MettleCI License file

By default, the `config.properties` configuration file refers to the
license file location by `license.file=../mettleci.lic` (the parent
directory). Save the license file and update the `license.file` setting
to refer to its location.

If you don’t already have a MettleCI license file, request one from your
Data Migrators or IBM representative, as appropriate.

The user that runs the MettleCI Workbench service (defined by the
`DM_WORKBENCH_USER` environment variable - typically set to `mciworkb`)
must have Read/Write (minimum <a
href="https://en.wikipedia.org/wiki/File-system_permissions#Numeric_notation"
rel="nofollow">600</a>) permissions to the MettleCI Workbench license
file (`mettleci.lic`)

## Modify the MettleCI CLI configuration

The MettleCI CLI locates all required DataStage executables relative to
a known DataStage Client or Engine directory.

Edit the `config.properties` file to comment and uncomment lines
appropriately so the file specifies configuration settings for UNIX:-

``` plain
# MettleCI Command Line Interface Configure File
# (C)2018-2022 Data Migrators Pty Ltd
# This line is mandatory and tells the CLI where to find your MettleCI License
# file. If you are installing the CLI on the same tier as MettleCI Workbench
# then you should configure this line to point to the same license file used by
# Workbench (and referenced in its config.yml file).  This might be...
# Unix
license.file=../mettleci.lic
# Windows
# license.file=mettleci.lic

# If the DataStage client executables directory is not on your system path you
# should uncomment one of the following lines and ensure it correctly points to
# a directory containing the DataStage dsadmin executable.  Note that double
# backslashes are required for Windows systems.
# Unix
ds.client.path=/opt/IBM/InformationServer/Server/DSEngine
# Windows
# ds.client.path=C:\\IBM\\InformationServer\\Clients\\Classic
```

The MettleCI CLI will continue to work if `ds.client.path` is not set
but will assume that all required executables are available on the
operating system PATH. This is not a recommended configuration because
it prevents MettleCI generating user friendly error reporting when
required executables are not found.

# Verify your install/upgrade

1.  Verify your MettleCi is running:

    ``` java
    $> mettleci
    MettleCI Command Line. Build xxx
    (C)2018-2020 Data Migrators Pty Ltd
    mettleci>
    ```

# Uninstall the Command Line Interface

1.  You can uninstall the MettleCI Workbench package like any other RPM
    package:

    ``` java
    $> sudo rpm -e dm-mettleci-command-shell
    ```

# Downgrading Command Line Interface

1.  If something goes wrong and you need to downgrade your version of
    MettleCI Command Line Interface, without performing an
    uninstall/reinstall, you can use the following command:

    ``` java
    $> rpm -Uvh --oldpackage dm-mettleci-command-shell-x.x-x.noarch.rpm
    ```

    … where **x.x.x** is the build version of the CLI you want to
    downgrade to.
