# Installing or Upgrading the Parallel Job Unit Test Harness on Unix

## Installation

1.  Download the latest RPM distributable of the MettleCI parallel Unit
    Test Harness (see
    <a href="Accessing_the_MettleCI_Software_Distribution"
    data-linked-resource-id="1565687876" data-linked-resource-version="1"
    data-linked-resource-type="page">Accessing the MettleCI Software
    Distribution</a>). The rest of these instructions assume this is
    located in your user’s `$HOME` directory.

2.  From that directory, install the package from the shell of your
    DataStage Development Engine using Red Hat Package Manager (RPM).

    ``` java
    sudo rpm -U dm-unittest-harness-x.x-x.noarch.rpm
    # or for AIX...
    sudo rpm -U dm-unittest-harness-x.x-x.noarch.rpm --ignoreos
    ```

3.  Verify that your rpm package installation has been successful. Note
    that this command uses the package name ('dm-unittest-harness') and
    not the RPM filename ('dm-unittest-harness-x.x-x.noarch.rpm').

    ``` java
    sudo rpm -V dm-unittest-harness
    .....UG..    /opt/IBM/InformationServer/Server/DSComponents/bin/dm-unittest-harness-1.0-219.jar
    .....UG..    /opt/IBM/InformationServer/Server/PXEngine/bin/osh-dm
    ```

4.  If your MettleCI licence file has not already been installed by the
    Workbench then copy your MettleCI licence file into the location
    `/opt/dm/mci/mettleci.lic`

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

<img src="attachments/455868494/668532753.png?width=204"
class="image-center" loading="lazy"
data-image-src="attachments/455868494/668532753.png" data-height="760"
data-width="974" data-unresolved-comment-count="0"
data-linked-resource-id="668532753" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="image-20200406-002139.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="455868494"
data-linked-resource-container-version="25"
data-media-id="d527e98b-1e0a-4888-9ab3-7942ddb8bfab"
data-media-type="file" width="204" />

### To enable MettleCI Unit Testing for all newly-created DataStage projects:

1.  Add the same entry described above to the DSParams for your
    ‘Template’ project, located in directory:

    ``` java
    /opt/IBM/InformationServer/Server/Template
    ```

## Uninstalling the Unit Test Harness

1.  You can uninstall the MettleCI Unit Test Harness package like any
    other RPM package:

    ``` java
    sudo rpm -e dm-unittest-harness
    ```

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200406-002139.png](attachments/455868494/668532753.png)
(image/png)  
