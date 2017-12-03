---
title: "Практическое руководство. Использование поставщика ролей ASP.NET со службой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb5adec17f834687038b729a475fbcc0e2311c01
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей ASP.NET со службой
Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (совместно с поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) - функция, позволяющая разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-сайты, на которых пользователи могут создавать учетные записи и получать роли, используемые для авторизации. Эта функция позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.  
  
 Пример приложения см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика членства, см. [как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях. Разработчики [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут воспользоваться преимуществами этих функций в целях безопасности. Когда эти функции интегрированы в приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], пользователи должны предоставлять сочетание имя/пароль пользователя клиентскому приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Чтобы включить использование базы данных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], необходимо создать экземпляр класса <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>, задать его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> значение <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> и добавить экземпляр в коллекцию поведений узла <xref:System.ServiceModel.ServiceHost>, в котором размещена служба.  
  
### <a name="to-configure-the-role-provider"></a>Настройка поставщика ролей  
  
1.  В файле Web.config в разделе <`system.web`> элемента, добавьте <`roleManager`> и присвойте его `enabled` атрибут `true`.  
  
2.  Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.  
  
3.  Как дочерние для <`roleManager`> элемента, добавьте <`providers`> элемент.  
  
4.  Как дочерние для <`providers`> элемента, добавьте <`add`> присвойте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, и `applicationName`, как показано в следующем примере.  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a>Настройка службы на использование поставщика ролей  
  
1.  Добавьте в файл Web.config, [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента.  
  
2.  Добавить [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента <`system.ServiceModel`> элемент.  
  
3.  Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемент.  
  
4.  Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и присвойте `name` соответствующее значение атрибута.  
  
5.  Добавить [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для <`behavior`> элемент.  
  
6.  Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.  
  
7.  Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`. В следующем примере показан фрагмент файла конфигурации.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>См. также  
 [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [Как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
