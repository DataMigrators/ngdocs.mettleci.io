# Integrating MettleCI Workbench and DataStage Designer on Windows

Workbench functionality can be accessed directly via the Workbench UI,
or may be triggered directly from the DataStage Client using
newly-introduced menu items accessed from the **Tools \> Custom** menu.
These menu items can be installed in your DataStage Designer client
using the option available on the front page of the Workbench user
interface.

Note that running the Menu Installation setup wizard multiple times will
result in multiple duplicate entries being added to your DataStage
client.

If you do this by mistake, either:

1.  Use the DataStage Designer’s **Tools \> Custom \> Customise** menu
    to remove the redundant entries, or

2.  Use the <a
    href="https://support.microsoft.com/search/results?query=Registry+Editor"
    rel="nofollow">Windows RegEdit</a> tool to delete redundant custom
    menu entries by deleting the keys from the Windows Registry.
    Relevant keys are <a
    href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/454590482"
    data-linked-resource-id="454590482" data-linked-resource-version="5"
    data-linked-resource-type="page">described here</a>.

# Configuration Steps

1.  To configure this functionality, click the purple **Integrate with
    DataStage Client** button on the Workbench home page.

    <img src="attachments/454623235/454787076?width=272"
    class="image-center" loading="lazy"
    data-image-src="attachments/454623235/454787076" data-height="150"
    data-width="749" data-unresolved-comment-count="0"
    data-linked-resource-id="454787076" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Integrate%20button.png?version=1&amp;modificationDate=1543362705737&amp;cacheVersion=1&amp;api=v2&amp;height=150"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/webp"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="e64cca89-fb63-4dae-a20c-359e37fd88c6"
    data-media-type="file" width="272" />

2.  This offers you a download file called `MCI_Setup.exe`. Run this
    setup file, agreeing to any Windows Security queries which might be
    presented. Any warnings from Windows Defender should be dsicmissed
    by clicking the **Run Anyway** button.

    <img src="attachments/454623235/454787083?width=272"
    class="image-center" loading="lazy"
    data-image-src="attachments/454623235/454787083" data-height="400"
    data-width="545" data-unresolved-comment-count="0"
    data-linked-resource-id="454787083" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Screen%20Shot%202018-11-27%20at%203.46.32%20pm.png?version=3&amp;modificationDate=1569471194603&amp;cacheVersion=1&amp;api=v2&amp;height=400"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/webp"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="de0e5a76-302f-46c5-b84d-69642d23eb3f"
    data-media-type="file" width="272" />

3.  Click **Next \>\>** to begin the installation wizard.

    <img src="attachments/454623235/2239070228.png" class="image-center"
    loading="lazy" data-image-src="attachments/454623235/2239070228.png"
    data-height="386" data-width="496" data-unresolved-comment-count="0"
    data-linked-resource-id="2239070228" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Custom Menu - Welcome.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="2c3ca973-cab4-4fe3-a107-1e7d67705927"
    data-media-type="file" />

4.  Enter the URL to MettleCI Workbench, then click **Install**

    <img src="attachments/454623235/2239135757.png" class="image-center"
    loading="lazy" data-image-src="attachments/454623235/2239135757.png"
    data-height="386" data-width="497" data-unresolved-comment-count="0"
    data-linked-resource-id="2239135757" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Custom Menu - Host.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="f6378039-0e69-4cec-8cb9-2bee93a9448c"
    data-media-type="file" />

5.  Click **Yes** to confirm the path to the DataStage client.

    <img src="attachments/454623235/2239397903.png" class="image-center"
    loading="lazy" data-image-src="attachments/454623235/2239397903.png"
    data-height="384" data-width="496" data-unresolved-comment-count="0"
    data-linked-resource-id="2239397903" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Custom Menu - Integrate.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="7c49ec5f-d6a7-4316-a9d3-23bb1f9b8a40"
    data-media-type="file" />

6.  Exit the wizard and log into DataStage.

    <img src="attachments/454623235/2237792391.png" class="image-center"
    loading="lazy" data-image-src="attachments/454623235/2237792391.png"
    data-height="384" data-width="496" data-unresolved-comment-count="0"
    data-linked-resource-id="2237792391" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Custom Menu - Finish.png"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/png"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="5b24a7de-5d77-4bf2-9caa-a7075bd186ff"
    data-media-type="file" />

7.  Inspect the **Tools \> Custom \> Customise...** settings and note
    the last four entries.

    <img src="attachments/454623235/454787101?width=204"
    class="image-center" loading="lazy"
    data-image-src="attachments/454623235/454787101" data-height="400"
    data-width="533" data-unresolved-comment-count="0"
    data-linked-resource-id="454787101" data-linked-resource-version="1"
    data-linked-resource-type="attachment"
    data-linked-resource-default-alias="Screen%20Shot%202018-11-27%20at%203.50.06%20pm.png?version=1&amp;modificationDate=1543300854759&amp;cacheVersion=1&amp;api=v2&amp;height=400"
    data-base-url="https://datamigrators.atlassian.net/wiki"
    data-linked-resource-content-type="image/webp"
    data-linked-resource-container-id="454623235"
    data-linked-resource-container-version="15"
    data-media-id="460bfce7-326c-48b6-8f40-e9c5e1272509"
    data-media-type="file" width="204" />

These allow the user to invoke Workbench functionality from within
DataStage: Workbench navigates to the appropriate view and
auto-populates the Project Name and Job Name with the values from the
active job in the DataStage Designer. Open a job and select each menu
item, ensuring each time that you are presented with the Workbench page
relevant to your menu selection.

# Notes

See the <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/454590482/What+does+the+Workbench+Integrated+with+DataStage+Client+button+do"
rel="nofollow">FAQ entry</a> for details of the registry keys which are
created.

If you don’t have the permissions necessary to run the menu installer or
it fails for some other reason, you can <a
href="https://datamigrators.atlassian.net/wiki/spaces/MCIDOC/pages/745078910/Manually+Configuring+the+DataStage+Designer+MettleCI+Menu+Items"
rel="nofollow">create the menu items manually</a>.

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Integrate%20button.png?version=1&modificationDate=1543362705737&cacheVersion=1&api=v2&height=150](attachments/454623235/454787076)
(image/webp)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Screen%20Shot%202018-11-27%20at%203.46.32%20pm.png?version=3&modificationDate=1569471194603&cacheVersion=1&api=v2&height=400](attachments/454623235/454787083)
(image/webp)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Screen%20Shot%202018-11-27%20at%203.46.54%20pm.png?version=1&modificationDate=1543300227523&cacheVersion=1&api=v2&height=400](attachments/454623235/454787089)
(image/webp)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Screen%20Shot%202018-11-27%20at%203.48.37%20pm.png?version=1&modificationDate=1543300702399&cacheVersion=1&api=v2&height=400](attachments/454623235/454787095)
(image/webp)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[Screen%20Shot%202018-11-27%20at%203.50.06%20pm.png?version=1&modificationDate=1543300854759&cacheVersion=1&api=v2&height=400](attachments/454623235/454787101)
(image/webp)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Custom
Menu - Welcome.png](attachments/454623235/2239070228.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Custom
Menu - Host.png](attachments/454623235/2239135757.png) (image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Custom
Menu - Integrate.png](attachments/454623235/2239397903.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Custom
Menu - Finish.png](attachments/454623235/2237792391.png) (image/png)  
