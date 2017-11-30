---
title: "Опасные разрешения и администрирование политик"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c8a01cbae2077838a8eef3f2f673e7d9d646717
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dangerous-permissions-and-policy-administration"></a>Опасные разрешения и администрирование политик
Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности. Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости. Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.  
  
> [!NOTE]
>  В версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]произошли серьезные изменения в терминологии и модели безопасности .NET Framework. Дополнительные сведения об этих изменениях см. в разделе [изменения системы безопасности](../../../docs/framework/security/security-changes.md).  
  
 Небезопасные разрешения приведены в следующей таблице.  
  
|Разрешение|Потенциальный риск|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Без проверки код может что-либо сделать.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Непроверенное свидетельство может обмануть систему безопасности.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|Возможность изменять политику безопасности может отключить систему безопасности.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|Использование сериализации позволяет обойти механизмы специальных возможностей. Подробные сведения см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|Возможность установки текущего участника может сбить с толку безопасность на основе ролей.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Можно использовать закрытые члены для нарушения правил доступа.|  
  
## <a name="see-also"></a>См. также  
 [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
