---
title: Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00df44a3f87e5a3fc3374f1429f6b427e0d3d76e
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой
При размещении веб-службы в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] можно интегрировать в приложение диспетчер авторизации, чтобы обеспечить службу возможностью авторизации. Диспетчер авторизации позволяет разработчику приложения определить отдельные операции, которые можно сгруппировать для образования задач. Администратор затем может авторизовать роли на выполнение определенных задач или отдельных операций. Диспетчер авторизации предоставляет средство администрирования в виде оснастки консоли управления (MMC) для управления ролями, задачами, операциями и пользователями. Администратор может настроить хранилище политик диспетчера авторизации в XML-файле, Active Directory или в хранилище Active Directory Application Mode (ADAM).  
  
 Диспетчер авторизации интегрируется в приложение путем настройки поставщика ролей диспетчера авторизации [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] для приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в котором размещается веб-служба. Как и другие поставщики ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], диспетчер авторизации [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] настраивается с помощью элемента <`providers`>.  
  
 Следующий пример кода представляет собой отрывок файла конфигурации для веб-службы, за счет которого диспетчер авторизации интегрируется в приложение.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Дополнительные сведения об интеграции [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поставщика ролей с [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приложения, в разделе [как: использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Дополнительные сведения об использовании диспетчера авторизации с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в разделе [как: использовать диспетчер авторизации (AzMan) с ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=71303).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
