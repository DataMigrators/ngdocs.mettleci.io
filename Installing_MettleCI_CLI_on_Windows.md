# Installing MettleCI CLI on Windows

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
    <a href="Accessing_the_MettleCI_Software_Distribution"
    data-linked-resource-id="1565687876" data-linked-resource-version="1"
    data-linked-resource-type="page">Accessing the MettleCI Software
    Distribution</a>). Note that Data Migrators provide a single
    multi-platform distribution package which supports both Unix and
    Windows.

2.  Extract the distribution package to the `C:\MettleCI\cli` directory
    on your Windows host

3.  If you don’t have one already, obtain your MettleCI license file
    (`mettleci.lic`) from the account manager of the organisation who
    supplied MettleCI.

4.  Save the `mettleci.lic` file to the location specified in the
    `config.properties` file. You can change the default location if
    required.

MettleCI Workbench requires the account running the Workbench Service to
have **read** and **write** permissions to the MettleCI License file.

## Add the MettleCI Command Line to your Windows path

1.  Start the System Control Panel applet (commonly accessed via
    **Start** → **Settings** → **Control Panel** → **System**).

2.  Select the **Advanced** tab, or **Advanced System Settings**,
    depending upon your version of Windows.

3.  Click the **Environment Variables** button.

4.  Under **System Variables**, select **Path**, then click either
    **Edit** or **New**, again depending upon your version of Windows.

5.  You'll see a list of folders, such as
    `C:\Program Files\Windows Resource Kits\Tools\;%SystemRoot%\system32;%SystemRoot%;`
    *…* etc.

6.  Add `C:\MettleCI\cli;` to your system path

7.  Click **OK** until you’re out of the Control Panel applet.

## Add DataStage Client path to MettleCI Command Line config

The MettleCI CLI locates all required DataStage executables relative to
a known DataStage Client or Engine directory.

Edit the `config.properties` file to comment and uncomment lines
appropriately so the file specifies configuration settings for Windows:

1.  Navigate to your MettleCI CLI directory (`C:\MettleCI\cli`) and open
    the `config.properties` file

2.  Update `config.properties` with **one** of the following options,
    depending upon your deployment topology (ensure you use double
    backslashes):

    1.  For a **DataStage Client Tier on a Windows host** (the most
        common use case), specify the path to the DataStage
        `Clients\Classic` directory to the file. i.e.,
        `ds.client.path=C:\\IBM\\InformationServer\\Clients\\Classic`

    2.  For a **DataStage Engine Tier on a Windows host**, specify the
        path to the `DSEngine` directory to the file. e.g.,
        `ds.client.path=C:\\IBM\\InformationServer\\Server\\DSEngine`

    3.  For a **Combined DataStage Engine and Client Tier on a single
        Windows host** (the least common topology), specify the path to
        the DataStage `Clients\Classic` directory to the file. i.e.,
        `ds.client.path=C:\\IBM\\InformationServer\\Clients\\Classic`

The MettleCI CLI will continue to work if `ds.client.path` is not set,
but will assume that all required executables are available on the
operating system `PATH`. This configuration is **not** recommended as it
prevents MettleCI generating user friendly error messages when required
executables are not found.

e.g.,

``` plain
# MettleCI Command Line Interface Configure File
# (C)2018-2022 Data Migrators Pty Ltd
# This line is mandatory and tells the CLI where to find your MettleCI License
# file. If you are installing the CLI on the same tier as MettleCI Workbench
# then you should configure this line to point to the same license file used by
# Workbench (and referenced in its config.yml file).  This might be...
# Unix
# license.file=../mettleci.lic
# Windows
license.file=mettleci.lic

# If the DataStage client executables directory is not on your system path you
# should uncomment one of the following lines and ensure it correctly points to
# a directory containing the DataStage dsadmin executable.  Note that double
# backslashes are required for Windows systems.
# Unix
# ds.client.path=/opt/IBM/InformationServer/Server/DSEngine
# Windows
ds.client.path=C:\\IBM\\InformationServer\\Clients\\Classic
```

## Test your MettleCI CLI

Start a new Command prompt and enter `mettleci` to verify your path now
contains the MettleCI CLI directory. You should now be presented with
the MettleCI prompt like this:

``` bash
C:\Users\MyUserName>mettleci
MettleCI Command Line (build nnn)
(C) 2018-2022 Data Migrators Pty Ltd
Enter [namespace] [command] [options]
or 'help' for more information, 'exit' or 'quit' to leave.
mettleci>
```

Use the following command to test that the CLI can work with DataStage
properly:-

``` bash
C:\Users\MyUserName>mettleci datastage execute -domain <domain:port> -server <engine> -username <user> -password <password> -project <project> -jobname TestJob
MettleCI Command Line (build nnn)
(C) 2018-2020 Data Migrators Pty Ltd
Preparing... TestJob
Executing... TestJob
TestJob executed successfully (10.361 seconds)
```

Note: If an error is received relating to needing to run
UpdateSignerCerts, please see <a
href="https://www.ibm.com/docs/en/iis/11.7?topic=certificates-running-updatesignercerts-command"
rel="nofollow">Running the UpdateSignerCerts Command</a>.

## Upgrade/Downgrade your MettleCI CLI

1.  Unzip your MettleCI CLI distribution media.

2.  Replace your existing `mettleci.cmd` with the version extracted from
    the download media.

3.  Enter the MettleCI CLI console and see that you have a newer version
    number reported. e.g.,

    ``` bash
    C:\Users\MyUserName>mettleci
    MettleCI Command Line (build 128)
    (C) 2018-2022 Data Migrators Pty Ltd
    Enter [namespace] [command] [options]
    or 'help' for more information, 'exit' or 'quit' to leave.
    mettleci>
    ```
