---
title: "Enabling JIT-Attach Debugging | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "JIT-attach debugging"
  - "debugging [.NET Framework], JIT-attach debugging"
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Enabling JIT-Attach Debugging
Отладка с JIT\-присоединением представляет собой фразу, используемую для описания присоединения отладчика к процессу при обнаружении ошибок, или же ее можно включить с помощью особых методов или функций.  
  
 Отладка с JIT\-присоединением используется в соответствии со следующими условиями ошибок.  
  
-   Необработанные исключения \(в машинном и управляемом коде\).  
  
-   Метод <xref:System.Environment.FailFast%2A?displayProperty=fullName> или функция [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) \(семейство Windows 7\).  
  
-   Неустранимые ошибки среды выполнения.  
  
 Отладка с JIT\-присоединением также включается вызовами следующих методов и функций.  
  
-   Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName>.  
  
-   Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName>.  
  
-   Функция [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) \(Win32\).  
  
 До [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] платформе .NET Framework предоставлялись отдельные разделы реестра для управления поведением отладчиков машинного и управляемого кода.  Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] управление объединено под одним разделом реестра: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\Current Version\\AeDebug.  Значения, которые можно задать для этого раздела, определяют необходимость вызова отладчика и в случае его вызова определяют необходимость его вызова с диалоговым окном, требующим взаимодействия с пользователем.  Дополнительные сведения о настройке этого раздела реестра см. в разделе [Настройка автоматическая отладка](http://go.microsoft.com/fwlink/?LinkId=181767) в библиотеке MSDN.  
  
## См. также  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [Упрощение отладки образов](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Enabling Profiling](http://msdn.microsoft.com/ru-ru/3b669676-f0e0-4ebf-8674-68986dd2020d)