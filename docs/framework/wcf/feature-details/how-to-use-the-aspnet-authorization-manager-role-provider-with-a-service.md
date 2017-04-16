---
title: "Как использовать поставщик ролей диспетчера авторизации ASP.NET со службой | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Как использовать поставщик ролей диспетчера авторизации ASP.NET со службой
При размещении веб\-службы в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] можно интегрировать в приложение диспетчер авторизации, чтобы обеспечить службу возможностью авторизации.  Диспетчер авторизации позволяет разработчику приложения определить отдельные операции, которые можно сгруппировать для образования задач.  Администратор затем может авторизовать роли на выполнение определенных задач или отдельных операций.  Диспетчер авторизации предоставляет средство администрирования в виде оснастки консоли управления \(MMC\) для управления ролями, задачами, операциями и пользователями.  Администратор может настроить хранилище политик диспетчера авторизации в XML\-файле, Active Directory или в хранилище Active Directory Application Mode \(ADAM\).  
  
 Диспетчер авторизации интегрируется в приложение путем настройки поставщика ролей диспетчера авторизации [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] для приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в котором размещается веб\-служба.  Как и другие поставщики ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], диспетчер авторизации [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] настраивается с помощью элемента \<`providers`\>.  
  
 Следующий пример кода представляет собой отрывок файла конфигурации для веб\-службы, за счет которого диспетчер авторизации интегрируется в приложение.  
  
```  
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
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] интеграции поставщика ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] с приложением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Как использовать поставщик ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] использовании диспетчера авторизации с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] см. в разделе [Как использовать диспетчер авторизации \(AzMan\) с ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=71303).  
  
## См. также  
 [Как использовать поставщик ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)