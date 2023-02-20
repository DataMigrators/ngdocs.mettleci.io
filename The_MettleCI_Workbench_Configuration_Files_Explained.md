# The MettleCI Workbench Configuration Files Explained

-   [The config.yml
    File](#TheMettleCIWorkbenchConfigurationFilesExplained-Theconfig.ymlFile)
-   [The datastage-users.yaml
    File](#TheMettleCIWorkbenchConfigurationFilesExplained-Thedatastage-users.yamlFile)
-   [The issuesmanagement-settings.yaml
    File](#TheMettleCIWorkbenchConfigurationFilesExplained-Theissuesmanagement-settings.yamlFile)
-   [The project-settings.yaml
    File](#TheMettleCIWorkbenchConfigurationFilesExplained-Theproject-settings.yamlFile)

------------------------------------------------------------------------

# The `config.yml` File

This is the primary MettleCI Workbench configuration file.

e.g.

``` java
gitAuthentication:
  sshKey: "/opt/dm/mci/workbench.key"
  httpsProvider: "SunJSSE"
  httpsCredentialsStore:
    type: "PKCS12"
    path: "/opt/dm/mci/.secrets/git-credentials.p12"
    password: ${file:UTF-8:/opt/dm/mci/.secrets/git-credentials-keystore-password}
datastage:
  installDir: "/opt/IBM/InformationServer/Server/DSEngine"
  domain: "demo115-svcs.dm-demo-datastage.datamigrators.io:59445"
  server: "demo115-engn.dm-demo-datastage.datamigrators.io"
  username: "isadmin"
  password: "{iisenc}W3ZIJYGenK408WMCS36N69SIFaSI9o1ikzRO4SJgjBU="
server:
  applicationConnectors:
    - type: https
      port: 8443
      keyStoreType: PKCS12
      keyStorePath: /opt/dm/mci/mettleci-trust.p12
      keyStorePassword: changeit
      trustStoreType: PKCS12
      trustStorePath: /opt/dm/mci/mettleci-trust.p12
      trustStorePassword: changeit
userInactiveTimeout: 0
featureToggles:
  projectRegistration: true
  issueManagement: true
  multipleWorkItemManagementEnabled: true
logging:
  type: "default"
  level: "INFO"
  appenders:
  - type: "file"
    threshold: "ALL"
    timeZone: "UTC"
    queueSize: 256
    discardingThreshold: -1
    currentLogFilename: "/opt/dm/mci/mci.log"
    archive: true
    archivedLogFilenamePattern: "/opt/dm/mci/mci-%d.log.gz"
    archivedFileCount: 5
    bufferSize: "8192 bytes"
    immediateFlush: true
admin:
  healthChecks:
    minThreads: 1
    maxThreads: 4
    workQueueSize: 1
  tasks: {}
```

# The `datastage-users.yaml` File

This MettleCI Workbench configuration file stores use-specific
information.

e.g.

``` java
---
- id: 1                                  # MettleCI internal user Id
  username: "peterparker"                # IIS username
  name: "Peter Parker"
  email: "peter.parker@mettleci.com"     # Used to identify users to most Git systems
  roles:                                 # IIS roles of this user
  - "ADMINISTRATOR"
  - "DEVELOPER"
  gitUsername: peter.parker               #
```

# The `issuesmanagement-settings.yaml` File

This stores connection details for your registered Work Item Management
systems.

e.g.

``` java
---
- id: 0
  type: "GENERIC"                                           # The default 'generic' issue management system
  name: "Default Generic Issue Manager"
- id: 1
  type: "JIRA"                                              # A Jira instance and its required configuration properties
  name: "Demo Jira"
  url: "http://atlassian.dm-demo-alm.mettleci.io/jira"
  consumerKey: "WB@demo115-engn.dm-demo-datastage"
  consumerSecret: "-----BEGIN PRIVATE KEY-----
  <SNIP>
  ZgdaxMMXs5Mlg4Oo=\n-----END PRIVATE KEY-----"
- id: 2
  type: "GITLAB"                                            # A GitLab instance and its required configuration properties
  name: "gitlab-wwi-115"
  url: "https://gitlab.dm-demo-alm.mettleci.io/"
  appId: "a945fc88a3 <SNIP> 439b7228f70fc363e"
  secret: "c74aa75f2 <SNIP> c0e87620f2ec1b7d5"
```

# The `project-settings.yaml` File

This stores details of each of the DataStage Projects registered with
MettleCI Workbench

e.g.

``` java
---
- id: 1
  name: "wwi_bamboo_ds115_dev"                                        # A project using Atlassian Bamboo
  repository:
    url: "ssh://git@atlassian.io:7999/ad/wwi_bamboo_ds115.git"
    branch: ""
    path: "datastage"
  compliance:
    url: "ssh://git@atlassian.io:7999/cr/compliance-rules.git"
    branch: ""
    path: ""
  issueManagementId: 1
- id: 2
  name: "wwi_azure_ds115_dev"                                         # A project using Microsoft Azure Devops
  repository:
    url: "git@ssh.dev.azure.com:v3/mettleci/ADO-WWI/ADO-WWI-115"
    branch: "main"
    path: "datastage"
  compliance:
    url: "git@ssh.dev.azure.com:v3/mettleci/ADO-WWI/ADO-Compliance"
    branch: "main"
    path: "WORKBENCH"
  issueManagementId: 0
- id: 3
  name: "wwi_github_ds115_dev"                                        # A project using GitHub
  repository:
    url: "ssh://git@github.com:peterparker/demo1115.github.git"
    branch: "main"
    path: "datastage"
  compliance:
    url: "ssh://git@github.com:peterparker/Compliance.git"
    branch: "main"
    path: ""
  issueManagementId: 0
- id: 4
  name: "wwi_gitlab_ds115_dev"                                        # A project using GitLab
  repository:
    url: "ssh://git@gitlab.io:data-migrators/gitlab-wwi-115.git"
    branch: "main"
    path: "datastage"
  compliance:
    url: "ssh://git@gitlab.io:data-migrators/gitlab-compliance.git"
    branch: "main"
    path: "WORKBENCH"
  issueManagementId: 2
```
