---
title: "Аутентификация в WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a08627e213196c2d5fb296f458a5d3a8c7bb1a0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="authentication-in-wcf"></a>Аутентификация в WCF
В следующем разделе показаны различные механизмы безопасности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], которые обеспечивают проверку подлинности. Например, проверка подлинности Windows, сертификаты X.509, имя пользователя и пароль.  
  
## <a name="in-this-section"></a>Содержание  
 [Как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации. В этом разделе объясняется, как службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут использовать ту же базу данных для проверки подлинности и авторизации пользователей.  
  
 [Как: используйте имя пользовательского пользователя и пароль проверяющий элемент управления](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.  
  
 [Службы идентификации и проверки подлинности](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 В качестве дополнительного средства защиты, клиент может проверить подлинность службы, задавая ожидаемое *удостоверение* службы. Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.  
  
 [Согласование безопасности и тайм-ауты](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Отладка ошибок проверки подлинности Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
