---
title: "Use Command-Line Parameters to Install Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology:
  - "vs-ide-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords:
  - "command-line parameters"
  - "switches"
  - "command prompt"
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: "TerryGLee"
ms.author: "tglee"
manager: "ghogen"
translation.priority.ht:
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt:
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Use Command-Line Parameters to Install Visual Studio 2017 RC
When you install Visual Studio 2017 RC from a command prompt, you can use the following command-line parameters (also known as switches).  


> [!NOTE]
>  Make sure that you use the actual installer and not the bootstrapper file. For example, make sure you use **`vs_enterprise.exe`** instead of vs_enterprise_*GUID*.exe. You can download an installer from [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015).  

## List of command-line parameters  
 Visual Studio command-line parameters are not case-sensitive.  

| **Command-line option** | **Description** |
| ----------------------- | --------------- |  
| ```[--catalog] <uri>``` *[&#60;uri&#62; ...]* | *Required*: One or more file paths or URIs to catalogs. |
|  ```--installDir <dir>```, ```--installationDirectory <dir>``` | *Required*: The target installation directory. |
|  ```-l <path>, --log <path>``` | Specify the log file; otherwise, one is automatically generated. |
|  ```-v, --verbose``` | Display verbose messages. |
|  ```-?, -h, --help``` | Display parameter usage. |
| ```--instanceId <id>``` | Optional: The instance ID to install or repair. |
| ```--productId <id>``` | Optional: The product ID to install. Otherwise, the first product found is installed. |
| ```--all``` | Optional: Whether to install all workloads and components for a product. |
| ```--add <workload or component ID>``` *[&#60;workload or component ID&#62; ...]* | Optional: One or more workload or component IDs to add. |
| ```--remove <workload or component ID>``` *[&#60;workload or component ID&#62; ...]* | Optional: One or more workload or component IDs to remove. |
| ```--optional, --includeOptional``` | Optional: Whether to install all optional workloads and components for selected workload. |
| ```--lang, --language <language-locale>``` *[&#60;language-locale&#62; ...]* | Optional: Install/uninstall resource packages with the specified language(s). |
|  ```--sharedInstallDir <dir>``` | Optional: The target installation directory for shared payloads. |  
| ```--compatInstallDir <dir>``` | Optional: The target installation directory for legacy compatibility payloads. |  
|  ```--layoutDir <dir>```, ```--layoutDirectory <dir>``` | Optional: The layout directory in which to find packages.|

## See Also  
 * [Create an offline installation of Visual Studio 2017 RC](create-an-offline-installation-of-visual-studio.md)
 * [Visual Studio Administrator Guide](install/visual-studio-administrator-guide.md)