# How the Parallel Unit Test Harness Integrates with DataStage

DataStage Parallel jobs are compiled into an <a
href="https://www.ibm.com/support/knowledgecenter/en/SSZJPZ_11.7.0/com.ibm.swg.im.iis.ds.parengmsg.ref.doc/topics/c_osh_cmdline.html"
rel="nofollow">osh</a> script which describes the processes (operators)
required to implement the job to the desired degree of parallelism. When
DataStage begins executing a Parallel job it forwards this osh script to
the <a
href="https://www.ibm.com/support/knowledgecenter/en/SSZJPZ_11.7.0/com.ibm.swg.im.iis.ds.parengmsg.ref.doc/topics/c_osh_cmdline.html"
rel="nofollow">osh</a> command line program which determines the
required structure of conductor, section leader, and player processes,
before then invoking these processes to execute your job.

The MettleCI Unit Testing Harness intervenes in the invocation of the
`osh` command and inspects the value of the <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/470319149/Configuring+Jobs+for+Unit+Testing"
rel="nofollow">$DM_ENABLE_UNIT_TESTING</a> parameter to determine if the
job invocation is a normal execution, Interception, or Unit Test
execution. Normal execution requests are forwarded to the regular
IBM-supplied `osh` command. Requests for Interception or Unit Test
executions, however, will cause MettleCI to modify your job’s osh script
before forwarding it to the `osh` command.

MettleCI achieves this by modifying your osh execution infrastructure
during installation of the Unit Test harness. Specifically, the
installation process does the following:

1.  renames the `osh` command to `osh-ibm` (to identify it as the
    original IBM-supplied `osh` command)

2.  installs a new executable called `osh-dm` (to identify it as a new
    command supplied by Data Migrators)

3.  replaces the original `osh` command with a new symbolic link named
    `osh` which points to `osh-dm`

Contrast an unmodified` ../PXEngine/bin` directory:

``` bash
>$ pwd
/opt/IBM/InformationServer/Server/PXEngine/bin
>$ ls -al osh*
-rwxrwxr-x. 1 dsadm dstage 73224 Mar 23 2019 osh
-rwxrwxr-x. 1 dsadm dstage 10648 Mar 23 2019 oshprinthost
-rwxrwxr-x. 1 dsadm dstage 19192 Mar 23 2019 oshwrapper
>$
```

…with one in which the MettleCI Unit Test Harness has been installed:

``` bash
$> pwd
/opt/IBM/InformationServer/Server/PXEngine/bin
$> ls -al osh*
lrwxrwxrwx 1 dsadm dstage 6 Jan 21 18:50 osh -> osh-dm
-rwxr-xr-x 1 dsadm dstage 2668 Jan 21 18:20 osh-dm
-rwxr-xr-x 1 dsadm dstage 69048 Jul 5 2018 osh-ibm
-rwxrwxr-x. 1 dsadm dstage 10648 May 10 2017 oshprinthost
-rwxrwxr-x. 1 dsadm dstage 19192 May 10 2017 oshwrapper
$>
```

To execute your jobs your DataStage client will call the `osh` symbolic
link. This will invoke the MettleCI executable `osh-dm` which will
identify any requirement to modify the supplied osh script before
invoking `osh-ibm` with that script as the input. The MettleCI Unit Test
Harness can be temporarily (or permanently) disabled by modifying the
`osh` symlink to point directly to the IBM-supplied original:

``` java
 $> ln -fs osh-ibm osh
```

If you apply a DataStage fix pack that contains a new version of `osh`,
you must make provisions to restore the symbolic link which invokes
`osh-dm`otherwise the patch may replace the symlink with a new version
of `osh`. As discussed in <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1457750170"
data-linked-resource-id="1457750170" data-linked-resource-version="6"
data-linked-resource-type="page">How do we safely update DataStage where
the MettleCI Unit Test Harness has been Installed?</a>, the easiest way
to do this is run the harness uninstaller prior to applying the patch.
Harness installation is reversible and uninstallation will restore the
directory structure to the non-symbolically linked version. This
uninstall process performs the same set of checks as the install process
to ensure it doesn't do anything destructive. 

## See also

-   <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1456996470/Updating+DataStage+Stops+the+MettleCI+Unit+Test+Harness+Working+for+Parallel+Jobs"
    rel="nofollow">Updating DataStage Stops the MettleCI Unit Test Harness
    Working for Parallel Jobs</a>

-   <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/1457750170/How+do+we+safely+update+DataStage+where+the+MettleCI+Unit+Test+Harness+has+been+Installed"
    rel="nofollow">How do I safely update a DataStage Installation in which
    the MettleCI Unit test harness has been Installed?</a>

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1468956816)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1468956826.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1469087838)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1468530813.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1469055094)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1469055104.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1472069724)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1471873178.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1468957007)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1469088026.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1471873196)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1472004198.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1474920459)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1474625553.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1477705766)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1477705776.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1584857189)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1587478551.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration](attachments/1465778187/1469087830)
(application/gliffy+json)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Parallel Unit Test Harness
Integration.png](attachments/1465778187/1468530805.png) (image/png)  
