---
title: "Авторизация в WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09bbbaad055447103a1153f1888dcae4a511cbeb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="authorization-in-wcf"></a>Авторизация в WCF
Авторизация - процесс управления доступом и правами на ресурсы, например службы и файлы. В подразделах этого раздела описано, как решить эту основную задачу в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] различными способами.  
  
## <a name="in-this-section"></a>Содержание  
 [Механизмы управления доступом](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 Предоставляет краткий обзор механизмов авторизации в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и предлагает варианты использования.  
  
 [Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Показывает процесс ограничения доступа к сервису с помощью класса <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Как: использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Пошаговое руководство по конфигурации службы, в котором рассказывается, как разрешить ей использовать функцию поставщика ролей инфраструктуры [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
 [Как: использование поставщика ролей диспетчера авторизации ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] может использовать диспетчер авторизации для управления авторизацией на веб-сайте. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может сходным образом использовать сочетание [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/диспетчер авторизации для авторизации клиентов.  
  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 Объясняет основы использования инфраструктуры модели удостоверения для механизма авторизации на основе утверждений.  
  
 [Делегирование и олицетворение](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 Объясняет разницу между делегированием и олицетворением.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Проверка подлинности](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
