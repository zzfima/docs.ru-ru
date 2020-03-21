---
title: Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 009b96defdf27591ddb98afaa684745b5fcbe0d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184809"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой
При ASP.NET усебясырует веб-службу, вы можете интегрировать диспетчера авторизации в приложение для предоставления авторизации службе. Диспетчер авторизации позволяет разработчику приложения определить отдельные операции, которые можно сгруппировать для образования задач. Администратор затем может авторизовать роли на выполнение определенных задач или отдельных операций. Диспетчер авторизации предоставляет средство администрирования в виде оснастки консоли управления (MMC) для управления ролями, задачами, операциями и пользователями. Администратор может настроить хранилище политик диспетчера авторизации в XML-файле, Active Directory или в хранилище Active Directory Application Mode (ADAM).  
  
 Диспетчер авторизации интегрирован в приложение, настраивая диспетчера авторизации ASP.NET ролевую роль поставщика для ASP.NET приложения, которое размещает веб-службу. Как и другие ASP.NET ролевые поставщики, диспетчер `providers` авторизации ASP.NET ролевой поставщик настраивается с использованием элемента> <.  
  
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
  
 Для получения дополнительной информации об интеграции ASP.NET ролевой роли поставщика с приложением WCF, см [ASP.NET.](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md) Для получения дополнительной информации об использовании диспетчера авторизации с ASP.NET [см. Как: Используйте диспетчер авторизации (AzMan) с ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
