---
title: "Collecting Performance Statistics by Using Sampling"
ms.custom: na
ms.date: 10/04/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8e36361b-bb3d-40c6-b286-0e68c0ecb915
caps.latest.revision: 21
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Collecting Performance Statistics by Using Sampling
By default, the Visual Studio Premium Profiling Tools sampling method collects profiling information every 10,000,000 processor cycles (approximately every one-hundredth of a second on a 1 GHz computer). The sampling method is useful for finding processor utilization issues and is the suggested method for starting most performance investigations.  
  
 **Requirements**  
  
-   Visual Studio Ultimate, Visual Studio Premium, Visual Studio Professional  
  
> [!NOTE]
>  Enhanced security features in Windows 8 and Windows Server 2012 required significant changes in the way the Visual Studio profiler collects data on these platforms. Windows Store apps also require new collection techniques. See [Performance Tools on Windows 8 and Windows Server 2012 applications](../VS_IDE/Performance-Tools-on-Windows-8-and-Windows-Server-2012-applications.md).  
  
 You can specify the sampling method by using one of the following procedures:  
  
-   On the first page of the Profiling Wizard, click **CPU Sampling (recommended)**.  
  
-   On the **Performance Explorer** toolbar, in the **Method** list, click **Sampling**.  
  
-   On the **General** page of the properties dialog box for the performance session, click **Sampling**.  
  
## Common Tasks  
 You can specify additional options in the *Performance Session***Property Pages** dialog box of the performance session. To open this dialog box:  
  
-   In **Performance Explorer**, right-click the performance session name, and then click **Properties**.  
  
 The tasks in the following table describe options that you can specify in the *Performance Session***Property Pages** dialog box when you profile by using the sampling method.  
  
|Task|Related Content|  
|----------|---------------------|  
|On the **General** page, add .NET memory allocation and lifetime data collection, and specify naming details for the generated profiling data (.vsp) file.|-   [Collecting .NET Memory Allocation and Lifetime Data](../VS_IDE/Collecting-.NET-Memory-Allocation-and-Lifetime-Data.md)<br />-   [How to: Set Performance Data File Name Options](../VS_IDE/How-to--Set-Performance-Data-File-Name-Options.md)|  
|On the **Sampling** page, change the sampling rate, change the sampling event from processor clock cycles to another processor performance counter, or change both..|-   [How to: Choose Sampling Events](../VS_IDE/How-to--Choose-Sampling-Events.md)|  
|On the **Launch** page, specify the application to start and the start order if you have multiple .exe projects in your code solution.|-   [Collecting tier interaction data](../VS_IDE/Collecting-tier-interaction-data.md)|  
|On the **Tier Interaction** page, add ADO.NET call information to to the data collected in theprofiling run.|-   [Collecting tier interaction data](../VS_IDE/Collecting-tier-interaction-data.md)|  
|On the **Windows Events** page, specify one or more Event Tracing for Windows (ETW) events to collect with the sampling data.|-   [How to: Collect Event Tracing for Windows (ETW) Data](../VS_IDE/How-to--Collect-Event-Tracing-for-Windows--ETW--Data.md)|  
|On the **Windows Counters** page, specify one or more operating system performance counters to add to the profiling data as marks.|-   [How to: Collect Windows Counter Data](../VS_IDE/How-to--Collect-Windows-Counter-Data.md)|  
|On the **Advanced** page, specify the version of the .NET Framework runtime to profile if your application modules use multiple versions. By default, the first version loaded is profiled.|-   [How to: Specify the .NET Framework Runtime](../VS_IDE/How-to--Specify-the-.NET-Framework-Runtime.md)|