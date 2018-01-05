---
title: "Замена объекта Principal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c53064ae12889df09b5259fbb7c8159cfdcd07aa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="replacing-a-principal-object"></a>Замена объекта Principal
Приложения, предоставляющие службы проверки подлинности, должны иметь возможность заменять объект **Principal** (<xref:System.Security.Principal.IPrincipal>) для данного потока. Более того, система безопасности должна защищать возможность замены объектов **Principal** , так как злонамеренно подключенный неправильный **Principal** является угрозой безопасности приложения, предоставляя неверное удостоверение или роль. Таким образом, приложениям, которым требуется возможность замены **основной** объекты должны быть предоставлены <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> объекта для основного элемента управления. (Обратите внимание, что это разрешение не требуется для выполнения проверок безопасности на основе ролей или для создания объектов **Principal** .)  
  
 Текущий объект **Principal** можно заменить, выполнив следующие задачи.  
  
1.  Создайте замещающий объект **Principal** и связанный объект **Identity** (удостоверение).  
  
2.  Подключите новый объект **Principal** к контексту вызова.  
  
## <a name="example"></a>Пример  
 В следующем примере показывается, как создать универсальный объект Principal и использовать его для задания участника потока.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [Объекты Principal и Identity](../../../docs/standard/security/principal-and-identity-objects.md)
