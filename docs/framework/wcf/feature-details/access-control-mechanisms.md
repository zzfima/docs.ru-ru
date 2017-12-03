---
title: "Механизмы управления доступом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cb3afec00fea5432329bd30fc993ac0cafd8b10
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="access-control-mechanisms"></a>Механизмы управления доступом
При помощи [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно контролировать доступ несколькими способами. В настоящем разделе кратко описываются различные механизмы и приводятся рассуждения о том, когда и какой способ использовать; раздел должен помочь пользователю выбрать правильный механизм использования. Технологии доступа перечислены в порядке сложности. Самым простым является <xref:System.Security.Permissions.PrincipalPermissionAttribute>; самым сложным - модель удостоверения.  
  
 Помимо этих механизмов, олицетворение и делегирование в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] подробно описан [делегирования и олицетворения](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 Для ограничения доступа к методу службы используется <xref:System.Security.Permissions.PrincipalPermissionAttribute>. Когда атрибут применяется к методу, он может использоваться для запроса идентификации заданного вызывающего или членства в группе Windows или роли [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Если подлинность клиента проверена при помощи сертификата X.509, клиенту дается первичное удостоверение, состоящее из имени субъекта и отпечатка сертификата.  
  
 Для контроля доступа к ресурсам на компьютере, на котором работает служба, используется <xref:System.Security.Permissions.PrincipalPermissionAttribute>, если пользователи службы всегда будут частью того же домена Windows, на котором работает служба. Можно легко создать группы Windows, которые имеют заданный уровень доступа (такой как отсутствие доступа, только для чтения или чтение и запись).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью атрибута, в разделе [как: ограничение доступа с использованием класса PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]удостоверение, в разделе [удостоверения службы и проверки подлинности](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>Поставщик участия ASP.NET  
 Функция [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] является поставщиком членства по умолчанию. Даже если поставщик членства технически не является механизмом контроля доступа, он позволяет контролировать доступ к службе путем ограничения набора возможных удостоверений, которые могут получить доступ к конечной точке службы. Функция членства включает в себя базу данных, которая может быть заполнена комбинациями имени/пароля, что позволяет пользователям веб-сайта создавать учетные записи на сайте. Для доступа к службе, которая использует поставщика членства, пользователь должен войти в систему со своими именем пользователя и паролем.  
  
> [!NOTE]
>  База данных должна быть заполнена при помощи функции [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], перед тем как она сможет использоваться службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с целью авторизации.  
  
 Кроме того, функцию членства также можно использовать, если уже имеется база данных членства из существующего веб-сайта [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и нужно разрешить тем же пользователям, авторизованным с теми же именами пользователей и паролями, использовать эту службу.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью функции членства в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы см. в разделе [как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>Поставщик ролей ASP.NET  
 Другой функцией [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] является способность управлять авторизацией при помощи ролей. Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] позволяет разработчику создавать роли для пользователей и соотносить каждого пользователя с ролью или ролями. Как и в случае с поставщиком членства, роли и назначения хранятся в базе данных и могут быть заполнены при помощи средств, предоставленных отдельной реализацией поставщика ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Как и с функцией членства, разработчики [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут использовать информацию в базе данных, чтобы авторизовать пользователей разрешения по ролям. Они могут, например, использовать поставщик ролей совместно с описанным выше механизмом контроля доступа `PrincipalPermissionAttribute`.  
  
 Кроме того, можно использовать поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], если имеется база данных существующего поставщика ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и нужно использовать тот же набор правил и назначений пользователя в своей службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью функцию поставщика ролей в разделе [как: использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Диспетчер авторизации  
 Другая функция авторизации клиентов комбинирует диспетчер авторизации (AzMan) и поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Когда на [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] размещается веб-служба, AzMan можно интегрировать в приложение таким образом, чтобы авторизация для доступа к службе выполнялась через AzMan. Диспетчер ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] предусматривает API, позволяющий управлять ролями приложения, добавлять пользователей в роли и удалять из них и проверять членство в ролях, но не позволяющий выполнять запросы для определения, может ли пользователь выполнять определенную задачу или операцию. AzMan позволяет определять отдельные операции и комбинировать их в задачах. При помощи AZMan кроме проверок роли можно также проверять, может ли пользователь выполнять задачу. Назначение роли и авторизация задачи могут быть настроены вне приложения или выполнены программно внутри приложения. Оснастка администрирования AzMan консоли управления MMC позволяет администраторам менять задачи, которые может выполнять определенная роль во время выполнения и управлять членством ролей каждого пользователя.  
  
 Кроме того, AzMan и поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] можно использовать, если уже есть доступ к существующей установке AzMan и нужно авторизовать пользователей своей службы при помощи функций комбинации AzMan/поставщик ролей.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]AzMan и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поставщика ролей в разделе [How To: использовать диспетчер авторизации (AzMan) с ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=88951). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью AzMan и поставщик ролей для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы, см. [как: использование поставщика ролей диспетчера авторизации ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Модель удостоверения  
 Модель удостоверения представляет собой набор API, которые позволяют управлять требованиями и политиками для авторизации клиентов. При помощи модели удостоверения можно рассматривать каждое требование, содержащееся в учетных данных, которое пользователь использовал для проверки своей подлинности, сравнить требования с набором политик для службы и на основе сравнения разрешить или запретить доступ.  
  
 Модель удостоверения используется, если необходимы точный контроль и способность задавать специальные условия перед предоставлением доступа. Например, при использовании <xref:System.Security.Permissions.PrincipalPermissionAttribute>, критерием является просто проверка подлинности удостоверения пользователя и его принадлежность определенной роли. В отличие от этого, при помощи модели удостоверения можно создавать политику, устанавливающую, что для получения разрешения на просмотр документа пользователь должен быть старше 18 лет и иметь действительное водительское удостоверение.  
  
 Одним из примеров, где можно воспользоваться контролем доступа на базе требования модели удостоверения, является использование учетных данных федерации в сценарии выданного токена. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Федерация и выданные маркеры в разделе [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Модель удостоверения в разделе [управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [Как: использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [Как: использование поставщика ролей диспетчера авторизации ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Делегирование и олицетворение](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
