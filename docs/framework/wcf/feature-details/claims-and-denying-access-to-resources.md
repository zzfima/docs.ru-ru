---
title: "Утверждения и запрет доступа к ресурсам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00d6a797b8099313c15d075457ee757c1f22f744
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="claims-and-denying-access-to-resources"></a>Утверждения и запрет доступа к ресурсам
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает механизм авторизации на основе утверждений. Системы могут предоставлять доступ к ресурсам на основе утверждений или отказывать в доступе к ресурсам на основе утверждений. Такие системы должны сначала проверять контекст <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие утверждений, запрещающих доступ, а лишь затем - на наличие утверждений, разрешающих доступ.  
  
 Например, система может отказать в доступе к ресурсу всем пользователям, имеющим утверждение типа `Age`, право <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> и значение ресурса `Under 21`, если для данного удостоверения также имеется утверждение типа `Name`, право <xref:System.IdentityModel.Claims.Rights.Identity%2A> и значение ресурса `Mallory`. Иными словами, система отказывает в доступе пользователям младше 21 года и предоставляет доступ пользователю с именем Mallory. Для правильно реализации такой семантики важно сначала проверять утверждение `Age`, чтобы определить, что пользователю исполнился 21 год. В противном случае, если пользователь Мэллори младше 21 года, он получит доступ к ресурсам только на том основании, что он соответствует утверждению `Name`.  
  
## <a name="see-also"></a>См. также  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Утверждения и маркеры](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
