# Installing or Upgrading the Server Job Unit Test Harness

Unlike MettleCI’s Parallel Unit Test Harness, which is installed once
for an entire DataStage Engine tier, the MettleCI **Server** Unit Test
Harness must be installed individually for each project for which you
wish to enable Server unit testing. To do this, follow the instructions
below.

## Enable Unit Testing of Server Jobs

**Only** perform these steps if your DataStage solution uses Server
Jobs. They must be **repeated for each DataStage project** for which
Server unit testing is required.

1.  Ensure you have performed the Unit Test Harness
    <a href="Installing_MettleCI_Unit_Test_Harness"
    data-linked-resource-id="454393879" data-linked-resource-version="12"
    data-linked-resource-type="page">installation steps for Parallel
    Jobs</a> and that you have tested that this MettleCI feature is
    operating correctly.

2.  Source `dsenv` in the $DSHOME directory. We ‘source’ the file,
    rather than just execute it, as we want to make changes in the
    user’s current shell:

    ``` java
    # e.g.
    . /path/to/dsenv        # using the 'dot' method (only works in bash-related shells), or
    source /path/to/dsenv   # using the `source` command
    ```

3.  Unzip `dm-server-unit-test-harness-routine-x.x-xxx.zip` and copy all
    the routine files within it to
    `$DSHOME/../Projects/<Project-Name>/DSU_BP`

4.  After copying them, change their ownership to `dsadm:dstage` (or
    whatever userid and group are the owners of your DataStage
    installation). Permissions can remain 640

5.  Start the UniVerse shell using `uvsh` or `dssh` from the
    `$DSHOME/../Projects/<Project-Name>` folder

6.  Once, you’re in the UniVerse shell, run the following commands (once
    for each copied routine) to compile the routines:

    ``` java
    BASIC DSU_BP  DSU.ExtractArgs
    BASIC DSU_BP  DSU.STUB
    ```

7.  Modify the Universe Catalog to rename `DSD.RUN` to `DSD.RUN_ORIG`
    and install `DSU_STUB` as `DSD.RUN`:

    ``` java
    CATALOG DSU_BP DSU.ExtractArgs DSU.ExtractArgs LOCAL
    CATALOG DSD_BP DSD.RUN_ORIG DSD_RUN.B LOCAL
    CATALOG DSU_BP DSD.RUN DSU.STUB LOCAL
    ```

8.  Use <a
    href="https://www.ibm.com/support/pages/how-set-environment-variables-infosphere-datastage"
    rel="nofollow">the linked IBM instructions</a> to apply the
    following two environment variables at the DataStage instance or
    Project level, replacing values between `< >` with values specific
    to your installation. If you need to perform Server Job unit testing
    across multiple Projects, we recommend setting these variables at
    the **instance** level to avoid the risk of accidental configuration
    gaps.

    ``` java
    DM_UNIT_TESTING_JAR=<datastage install directory>/Server/DSComponents/bin/dm-unittest-harness-<x.x-xxx>.jar
    DM_METTLE_HOME=<MettleCI home location>   
    ```

9.  Ensure a <a
    href="https://www.ibm.com/support/knowledgecenter/SSZJPZ_11.7.0/com.ibm.swg.im.iis.found.moz.wc.admin.doc/topics/t_wcadmin_defining_default_credentials.html"
    rel="nofollow">default credential mapping</a> has been set for your
    DataStage engine. Please see this <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/2352578583/How+set+configure+default+credential+mapping+when+user+registry+sharing+is+enabled"
    data-linked-resource-id="2352578583" data-linked-resource-version="7"
    data-linked-resource-type="page">FAQ page</a> for completing this
    step when your DataStage engine is configured to use shared user
    credentials.

## Post-installation

### To enable MettleCI Unit Testing for an existing DataStage project:

1.  Log into your development DataStage Engine(s) and navigate to your
    DataStage project folder. This would typically be:

    ``` java
    /opt/IBM/InformationServer/Server/Projects/<Your Existing Project>
    ```

2.  Add the following Environment variable definition to the `DSParams`
    file under the `[EnvVarDefns]` section:

    ``` java
    DM_ENABLE_UNIT_TESTING\MettleCI\-1\List/Disabled//Test//Intercept/\Disabled\3\Project\Unit Testing Configuration\
    ```

This will make the following Environment Variable available to add to
the DataStage jobs for which you wished to enable unit testing:

<img src="attachments/455737424/1144193157.png?width=204"
class="image-center" loading="lazy"
data-image-src="attachments/455737424/1144193157.png" data-height="760"
data-width="974" data-unresolved-comment-count="0"
data-linked-resource-id="1144193157" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="image-20200406-002139.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="455737424"
data-linked-resource-container-version="38"
data-media-id="15a7ea0c-3003-4b5a-937f-df29ef2e0625"
data-media-type="file" width="204" />

 

### To enable MettleCI Unit Testing for all newly-created DataStage projects:

1.  Add the same entry described above to the DSParams for your
    ‘Template’ project, located in directory:

    ``` java
    /opt/IBM/InformationServer/Server/Template
    ```

## If your Server Job execution hangs

These steps can also be applied to the template project in
`$DSHOME/../Template` to ensure DataStage Server Unit Testing is enabled
on all projects created in the future

After deploying Server Job Unit Testing you ***may*** experience a
situation in which a Server job hangs in a ‘running’ state when
executing a Unit Test. To address this you will need to run the
following command on your a DataStage client tier to update DataStage’s
understanding of available stage types.

``` java
<Datastage-Root-Folder>/IBM/InformationServer/Clients/Classic/DSStageTypeUpdater.exe 
```

`DSStageTypeUpdater.exe` needs to be run project by project basis. If
you have 10 projects, you will need to run it 10 times, once per
project. For more details, please refer to
<a href="https://www-01.ibm.com/support/docview.wss?uid=swg21498616"
rel="nofollow">https://www-01.ibm.com/support/docview.wss?uid=swg21498616</a>

## Changing the level of Unit Test log messages

Enabling Unit Testing will set the log type as Warning. This is to help
remind developers to switch the Unit Testing mode off before deploying
to Production. If that causes an issue, if you can override it by adding
a new environment variable `DM_LOG_UNITTEST_LEVEL` with value of `INFO`
to the `dsenv` file. For example:

``` bash
# Data Migrators Set Enable Unit Testing as INFO (default is Warning)
DM_LOG_UNITTEST_LEVEL=INFO
export DM_LOG_UNITTEST_LEVEL
```

  

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200406-002139.png](attachments/455737424/1144193157.png)
(image/png)  
