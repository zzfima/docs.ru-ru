---
title: "Поиск утверждений в наборах утверждений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cc6a4d98529357aa58f55be2fc33d6b7a95a8999
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="finding-claims-in-a-claimset"></a>Поиск утверждений в наборах утверждений
При использовании авторизации на основе утверждений часто выполняется проверка содержимого <xref:System.IdentityModel.Claims.ClaimSet> для определенных типов утверждений. Чтобы проверить <xref:System.IdentityModel.Claims.ClaimSet> на наличие определенных утверждений, используйте метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>. Этот метод обеспечивает более высокую производительность по сравнению с выполнением итерации непосредственно с <xref:System.IdentityModel.Claims.ClaimSet>. Использование этого метода показано в следующем примере. Обратите внимание, что параметры `claimType` и `claimRight` могут иметь значение `null`. В этом случае параметры будут соответствовать всем типам и правам утверждения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
