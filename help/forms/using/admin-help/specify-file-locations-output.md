---
title: Specify file locations for Output
seo-title: Specify file locations for Output
description: Learn how to specify file locations for Output.
seo-description: Learn how to specify file locations for Output.
uuid: 3287274f-85b5-4811-8abb-d347a9b80947
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.5/FORMS
discoiquuid: 460bbb31-8187-469c-8102-b310093b6c03
exl-id: 620c69d6-4fe1-46d6-b5d4-3b562142e547
---
# Specify file locations for Output {#specify-file-locations-for-output}

You can specify the locations where Output looks for certain types of files that it requires.

1. In administration console, click Services &gt; output.
1. Under Locations, specify the appropriate options.
1. Click Save.

## Locations settings {#locations-settings}

**Content Root URI:** The URI or absolute location of the repository from which forms are retrieved. This value is combined with the sForm parameter, specified through the API, to construct the absolute path to the form that is retrieved. This value can reference a directory or a web location that is accessible using HTTP.

The default value is an empty string.

**XCI Configuration File:** The relative or absolute location of the XCI configuration file that the Output service uses for rendering. For a relative value, it is assumed that the XCI file resides in the AEM forms deployable EAR file.

The default value is `com/adobe/formServer/PA/pa_output.xci`.

**Cache Location:** Specifies the location of the Output disk cache. When you change this setting, all existing cache information from the current location is reset and a new cache is created at the new location. Select one of the following options:

**Default Location:** This is the default selection. When this option is selected, the cache is created at a location that is dependent on the application server you are using:

* **JBoss:** `[JBoss Home]\server\[install type]\svcdata\Output\Cache`
* **WebLogic:** `[WebLogic Home]\user_projects\domains\[aem-forms domain Name]\adobe\[forms server name]\Output\Cache`
* **WebSphere:** `[IBM Home]\WebSphere\AppServer\installedApps\adobe\server1\Output\Cache`

**LC Temp Directory:** The cache is created in a subdirectory of the AEM forms temp directory, which is specified in the administration console under Settings > Core System Settings > Configurations > Location of Temp Directory. The subdirectory is named `adobeoutput_[servername]`.

>[!NOTE]
>
>If you are using a temp cleaning utility, be aware that while deleting these directories does not affect functionality, it can significantly impact performance for a short time, until the new cache is created. To avoid this issue, do not delete these directories while clearing the AEM forms temp directory.
