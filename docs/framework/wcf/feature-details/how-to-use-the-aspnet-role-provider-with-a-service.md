---
title: "Как использовать поставщик ролей ASP.NET со службой | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как использовать поставщик ролей ASP.NET со службой
Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] \(совместно с поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\) — функция, позволяющая разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб\-сайты, на которых пользователи могут создавать учетные записи и получать роли, используемые для авторизации.Эта функция позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам.В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.Вместо этого любой пользователь, который предоставляет свои учетные данные \(сочетание имени пользователя и пароля\), может использовать сайт и его службы.  
  
 Пример приложения см. в разделе [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] функции поставщика участия [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] см. в разделе [Как использовать поставщик членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 Функция поставщика ролей использует базу данных SQL Server для хранения информации о пользователях.Разработчики [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут воспользоваться преимуществами этих функций в целях безопасности.Когда эти функции интегрированы в приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], пользователи должны предоставлять сочетание имя\/пароль пользователя клиентскому приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Чтобы включить использование базы данных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], необходимо создать экземпляр класса <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>, задать его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> значение <xref:System.ServiceModel.Description.PrincipalPermissionMode> и добавить экземпляр в коллекцию поведений узла <xref:System.ServiceModel.ServiceHost>, в котором размещена служба.  
  
### Настройка поставщика ролей  
  
1.  В файле Web.config в элементе \<`system.web`\> добавьте элемент \<`roleManager`\> и присвойте его атрибуту `enabled` значение `true`.  
  
2.  Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.  
  
3.  Добавьте элемент \<`providers`\> в качестве дочернего для элемента \<`roleManager`\>.  
  
4.  В качестве дочернего элемента \<`providers`\> добавьте элемент \<`add`\>, присвоив надлежащие значения следующим атрибутам: `name`, `type`, `connectionStringName` и `applicationName`, как показано в следующем примере.  
  
    ```  
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
  
### Настройка службы на использование поставщика ролей  
  
1.  В файле Web.config добавьте элемент [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md).  
  
2.  Добавьте элемент [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) в элемент \<`system.ServiceModel`\>.  
  
3.  Добавьте элемент [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) в элемент \<`behaviors`\>.  
  
4.  Добавьте элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и присвойте атрибуту `name` соответствующее значение.  
  
5.  Добавьте элемент [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) в элемент \<`behavior`\>.  
  
6.  Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.  
  
7.  Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`.В следующем примере показан фрагмент файла конфигурации.  
  
    ```  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## См. также  
 [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)   
 [Как использовать поставщик членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)