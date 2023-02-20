# Prerequisite Java Installation

MettleCI’s Workbench and Command Line components cannot work with the
IBM-specific version of Java typically shipped with DataStage due to
technical limitations with that version. To resolve this you need to
install a more recent version of Java <u>alongside</u> (**not**
replacing) your IBM-supplied version. This page provides instructions
for doing so on <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/488800406/Prerequisite+Java+Installation#Installing-Java-v1.8-on-Unix"
rel="nofollow">Unix</a> and <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/488800406/Prerequisite+Java+Installation#Installing-Java-v1.8-on-Windows"
rel="nofollow">Windows</a>.

For more information about this dependency, refer to the FAQ page <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/466485268/Why+do+I+have+to+install+another+version+of+Java"
rel="nofollow">Why do I have to install another version of Java?</a>

If you believe that you may already have a compatible Java Virtual
Machine installed on your DataStage environment then see <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1031897089/Can+I+use+my+existing+version+of+Java+Virtual+Machine"
rel="nofollow">Can I use my existing version of Java Virtual
Machine?</a>

------------------------------------------------------------------------

## Installing Java 8 on Unix

Follow these steps before installing the MettleCI Workbench or Command
Shell on your Unix host.

Download and Install OpenJDK v8. We test MettleCI with - and therefore
recommend - <a href="https://adoptium.net/temurin/releases/?version=8"
rel="nofollow">the latest OpenJDK distribution</a> of OpenJDK 8 LTS.

1.  If your DataStage Engine tier **has direct access to the internet**
    then you can use your machine’s package manger to install Java 8
    using an RPM reference which resolves to a URL. For example, on a
    Red Hat Enterprise Linux host :

    ``` bash
    $> sudo yum install java-1.8.0-openjdk-devel.x86_64
    $> export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.212.b04-0.el6_10.x86_64
    $> export JRE_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.212.b04-0.el6_10.x86_64/jre
    ```

2.  If your DataStage Engine tier **does not have direct access to the
    internet** then you can use your machine’s package manger to install
    Java 8 using a local RPM file reference.

    1.  Download the OpenJDK RPM image from the OpenJDK website (you’ll
        need to unzip it once you’ve downloaded it.)

    2.  Install it using your machine’s package manager. For example, on
        a Red Hat Enterprise Linux host :

        ``` bash
        $> sudo yum localinstall /path/to/file/java-1.8.0-openjdk-devel.x86_64
        $> export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.212.b04-0.el6_10.x86_64
        $> export JRE_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.212.b04-0.el6_10.x86_64/jre
        ```

Note that your Java build numbers will most likely vary from those show
above. The actual files you need to point the JAVA_HOME and JRE_HOME are
named with the pattern **java-1.8.0-openjdk-1.8.0.nnn.xxxx.x86_64** and
**java-1.8.0-openjdk-1.8.0.nnn.xxxx.x86_64/jre**. The simplest method of
getting the right values is to use your shell’s
<a href="https://en.wikipedia.org/wiki/Command-line_completion"
rel="nofollow">command-line completion</a> capabilities.

For AIX: Download the latest OpenJDK 8 from
<a href="https://adoptium.net/temurin/releases/?version=8"
rel="nofollow">https://adoptium.net/temurin/releases/?version=8</a>

UnZip and UnTar on AIX:
`gunzip -c OpenJDK8U-jdk_ppc64_aix_hotspot_8u282b08.tar.gz | tar -xvf -`

Add the following to the `.profile` file for the MettleCI Workbench
User:-

`export JAVA_HOME=/usr/lib/jvm/jdk8u282-b08`  
`export JRE_HOME=/usr/lib/jvm/jdk8u282-b08/jre`

`PATH=$JAVA_HOME/bin:<OLD_PATH>`  
`export PATH`

If you intend to use Oracle’s JDK, ensure that you have obtained a
license (usually paid-for) from Oracle on behalf of your organisation.
The license you acquire must permit production use of the JDK by
MettleCI.

------------------------------------------------------------------------

## Installing Java 8 on Windows

Before installing the MettleCI workbench you’ll need to install Java 8.
For example…

1.  Download the Windows 64-bit installer for Java 8. We test MettleCI
    with - and therefore recommend -
    <a href="https://adoptium.net/temurin/releases/?version=8"
    rel="nofollow">the latest OpenJDK distribution</a> of OpenJDK 8 LTS.

2.  Run the installer and click **Next** until prompted to accept the
    license terms.

3.  Select the checkbox to accept the licence terms and click **Next**.

4.  Leave the custom setup options as supplied.

5.  <img src="attachments/488800406/488865865.png" class="image-center"
    loading="lazy" data-image-src="attachments/488800406/488865865.png"
    data-height="388" data-width="495" data-unresolved-comment-count="0"
    data-linked-resource-id="488865865" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="image-20191030-061446.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="488800406"
    data-linked-resource-container-version="24"
    data-media-id="78a5f5a0-ceab-4c9f-874f-4a54bf850f4a"
    data-media-type="file" />

6.  Set the <u>System-level</u> **PATH** variable if the installer
    hasn’t already done so:

    1.  Select **Control Panel** then either **System** or **System and
        Security** then **System**.

    2.  Click **Advanced** and then **Environment Variables**.

    3.  Add the location of the bin folder of the JDK installation to
        the **PATH** variable in **System Variables**.

    4.  The following is an example of the **PATH** variable:

        ``` java
        C:\WINDOWS\system32;C:\WINDOWS;"C:\Program Files\Java\jdk-8\bin"
        ```

7.  You don’t need to set the **JAVA_HOME** variable.

NOTE: At this time versions beyond Java 8 / 1.8 (for example 1.11 or
“Java 11”) are **NOT** supported.

------------------------------------------------------------------------

# See also

-   <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/2293497857/MettleCI+Installation+Walkthrough#Introduction-and-Prerequisites"
    rel="nofollow">MettleCI Installation Walkthrough - Introduction and
    Prerequisites</a>

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20191030-061446.png](attachments/488800406/488865865.png)
(image/png)  
