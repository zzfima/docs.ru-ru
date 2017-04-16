---
title: "Уменьшение: реализации пользовательских IMessageFilter.PreFilterMessage | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 2
---
# Уменьшение: реализации пользовательских IMessageFilter.PreFilterMessage
В приложениях Windows Forms, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], реализация настраиваемого метода <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> может безопасно фильтровать сообщения, когда вызывается метод <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>, если реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:  
  
-   Выполняет одно или оба следующих действия:  
  
    -   добавляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.AddMessageFilter%2A>;  
  
    -   удаляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. метод.  
  
-   **И** передает сообщения путем вызова метода <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.  
  
## Последствия  
 Это изменение затрагивает только приложения Windows Forms, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 В приложениях Windows Forms, которые предназначены для предыдущих версий платформы .NET Framework, такие реализации в некоторых случаях вызывают исключение <xref:System.IndexOutOfRangeException> при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.  
  
## Уменьшение  
 Если это изменение нежелательно, его можно отключить для приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], добавив в раздел [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" /> </runtime>  
  
```  
  
 Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Для этого добавьте в раздел [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" /> </runtime>  
  
```  
  
## См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)