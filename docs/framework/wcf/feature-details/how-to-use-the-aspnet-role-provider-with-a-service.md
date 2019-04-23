---
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 8f3fadc60645ef81d2683c63fda0ddd5bf24c982
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301143"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей ASP.NET со службой
Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (совместно с поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) - возможность, позволяющая разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-сайты, на которых пользователи могут создавать учетные записи и получать роли, используемые для авторизации. Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.  
  
 Образец приложения, см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Дополнительные сведения о [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика участия см. в разделе [как: Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях. Windows Communication Foundation (WCF) разработчикам воспользоваться преимуществами этих функций в целях безопасности. При интеграции в приложение WCF, пользователям необходимо ввести сочетание имя/пароль пользователя клиентскому приложению WCF. Чтобы включить WCF для использования базы данных, необходимо создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> класса, задайте его <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> свойства <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>и добавьте экземпляр в коллекцию поведений узла <xref:System.ServiceModel.ServiceHost> , на котором размещена служба.  
  
### <a name="to-configure-the-role-provider"></a>Настройка поставщика ролей  
  
1. В файле Web.config в разделе <`system.web`> элемента, добавьте <`roleManager`> и присвойте его `enabled` атрибут `true`.  
  
2. Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.  
  
3. Дочерний элемент <`roleManager`> элемента, добавьте <`providers`> элемента.  
  
4. Дочерний элемент <`providers`> элемента, добавьте <`add`> задайте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, и `applicationName`, как показано в следующем примере.  
  
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
  
1. Добавьте в файл Web.config, [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемент.  
  
2. Добавить [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент <`system.ServiceModel`> элемента.  
  
3. Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемента.  
  
4. Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и присвойте `name` атрибут соответствующее значение.  
  
5. Добавить [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для <`behavior`> элемента.  
  
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
  
## <a name="see-also"></a>См. также

- [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [Практическое руководство. Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
