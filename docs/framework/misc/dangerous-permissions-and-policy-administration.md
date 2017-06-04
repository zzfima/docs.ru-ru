---
title: "Dangerous Permissions and Policy Administration | Microsoft Docs"
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
  - "permissions [.NET Framework], policy administration"
  - "security [.NET Framework], dangerous permissions"
  - "code security, dangerous permissions"
  - "secure coding, dangerous permissions"
  - "permissions [.NET Framework], dangerous"
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Dangerous Permissions and Policy Administration
Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности. Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости. Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.  
  
> [!NOTE]
>  В версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] произошли серьезные изменения в терминологии и модели безопасности .NET Framework. Дополнительные сведения об этих изменениях см. в разделе [Изменения системы безопасности](../../../docs/framework/security/security-changes.md).  
  
 Небезопасные разрешения приведены в следующей таблице.  
  
|Разрешение|Потенциальный риск|  
|----------------|------------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Без проверки код может что\-либо сделать.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Непроверенное свидетельство может обмануть систему безопасности.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Возможность изменять политику безопасности может отключить систему безопасности.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Использование сериализации позволяет обойти механизмы специальных возможностей. Подробные сведения см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Возможность установки текущего участника может сбить с толку безопасность на основе ролей.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Можно использовать закрытые члены для нарушения правил доступа.|  
  
## См. также  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)