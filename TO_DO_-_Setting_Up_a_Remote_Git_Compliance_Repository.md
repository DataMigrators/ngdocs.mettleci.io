# TO DO - Setting Up a Remote Git Compliance Repository

## Remote Repository Setup

Create your repository in your Git system of choice (Git, GitHub,
GitLab, Bitbucket, Azure DevOps, etc.) then clone it to your local
DataStage Engine tier:

``` java
# Windows example
C:\Users\Me>git config --global user.name "admin"
C:\Users\Me>git config --global user.email "admin@admin.com"
C:\Users\Me>git clone http://localhost/bitbucket/scm/mci/compliance.git
Cloning into 'compliance'...
warning: You appear to have cloned an empty repository.

C:\Users\Me>
```

Configure MettleCI Workbench

<img src="attachments/784171256/784171262.png" class="image-center"
loading="lazy" data-image-src="attachments/784171256/784171262.png"
data-height="253" data-width="366" data-unresolved-comment-count="0"
data-linked-resource-id="784171262" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="image-20200317-233118.png"
data-base-url="https://datamigrators.atlassian.net/wiki"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="784171256"
data-linked-resource-container-version="2"
data-media-id="c12abe82-c850-40c3-bd50-8bab7afa67a1"
data-media-type="file" />

(NEED A FILESYSTEM-BASED EXAMPLE HERE)

Download the Compliance Rule zip file from
<a href="http://software.mettleci.io"
rel="nofollow">software.mettleci.io</a> and unzip unto the Git
repository directory:

``` java
C:\Users\Me\compliance>:: Download the compliance rules zip, presumably into your Downloads directory
C:\Users\Me\compliance>unzip -d compliance Downloads\datamigrators-compliance-rules-fa14b4baf624.zip
Archive:  Downloads/datamigrators-compliance-rules-fa14b4baf624.zip

fa14b4baf624694b17fbbd90c73d38334aee950f
   creating: datamigrators-compliance-rules-fa14b4baf624/
  inflating: datamigrators-compliance-rules-fa14b4baf624/Adjacent Transformers.pjb.grm
  inflating: datamigrators-compliance-rules-fa14b4baf624/Adjacent Transformers.sjb.grm
etc.

C:\Users\Me>
```

Commit the files to Git:

``` java
C:\Users\Me>cd compliance
C:\Users\Me\compliance>git add *.grm
warning: LF will be replaced by CRLF in Adjacent Transformers.pjb.grm.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in Adjacent Transformers.sjb.grm.
The file will have its original line endings in your working directory
etc.

C:\Users\Me\compliance>git commit -m "First version"
[master (root-commit) c78df15] First version
 63 files changed, 4397 insertions(+)
 create mode 100644 Adjacent Transformers.pjb.grm
 create mode 100644 Adjacent Transformers.sjb.grm
etc.

C:\Users\Me\compliance>git push origin master
Enumerating objects: 60, done.
Counting objects: 100% (60/60), done.
Delta compression using up to 4 threads
Compressing objects: 100% (60/60), done.
Writing objects: 100% (60/60), 55.94 KiB | 2.15 MiB/s, done.

Total 60 (delta 11), reused 0 (delta 0)
To http://localhost/bitbucket/scm/mci/compliance.git
 * [new branch]      master -> master

C:\Users\Me\compliance>:: You're done!
```

## Attachments:

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image-20200317-233118.png](attachments/784171256/784171262.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Git
Repository Integration Options.png](attachments/784171256/784171265.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" /> [Git
Repository Integration Options](attachments/784171256/784171268)
(application/gliffy+json)  
