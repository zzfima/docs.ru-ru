---
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184772"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей ASP.NET со службой

Поставщик ASP.NET роли (совместно с ASP.NET поставщиком членства) — это функция, позволяющая ASP.NET разработчикам создавать веб-сайты, позволяющие пользователям создавать учетную запись с сайта и присваиваться роли для целей авторизации. Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого, любой пользователь, который поставляет свои учетные данные (комбинация имени пользователя /пароль) может использовать сайт и его услуги.  
  
Для примера приложения [см.](../../../../docs/framework/wcf/samples/membership-and-role-provider.md) Для получения дополнительной информации о функции поставщика ASP.NET членства [ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)см.  
  
Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях. Разработчики Windows Communication Foundation (WCF) могут воспользоваться этими функциями в целях безопасности. При интеграции в приложение WCF пользователи должны предоставить клиентское приложение WCF комбинацию имени пользователя/пароля. Чтобы WCF мог использовать базу данных, необходимо <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> класса, установить его свойство <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>и добавить экземпляр в коллекцию поведения к <xref:System.ServiceModel.ServiceHost> тому, что размещает службу.  
  
## <a name="configure-the-role-provider"></a>Настройка поставщика ролей  
  
1. В файле Web.config под `system.web` элементом <`roleManager`> добавить `enabled` элемент `true`<> и установить его атрибут.  
  
2. Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.  
  
3. В качестве ребенка `roleManager` в элемент <`providers`> добавьте элемент> <.  
  
4. Как ребенок, к `providers` элементу <`add`>, добавьте элемент <> со `name` `type`следующими атрибутами, установленными к соответствующим значениям: , `connectionStringName`и, `applicationName`как показано в следующем примере.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Настройка службы для использования ролевой услуги поставщика  
  
1. В файле Web.config добавьте [ \<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемент.  
  
2. Добавьте элемент [ \<>поведения](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) `system.ServiceModel` в элемент> <.  
  
3. Добавьте><`behaviors`> элемента [ \<serviceBehaviors.](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)  
  
4. Добавьте [ \<элемент поведения>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и установите `name` атрибут в соответствующее значение.  
  
5. Добавьте [ \<>авторизации службы](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) в элемент <`behavior`>.  
  
6. Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.  
  
7. Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`. В следующем примере показан фрагмент файла конфигурации.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [Практическое руководство. Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
