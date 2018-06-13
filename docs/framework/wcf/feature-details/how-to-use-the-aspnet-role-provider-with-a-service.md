---
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 846caf59816ee23166fb382a0c36ac0fed9df151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492962"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей ASP.NET со службой
Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (совместно с поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) - функция, позволяющая разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-сайты, на которых пользователи могут создавать учетные записи и получать роли, используемые для авторизации. Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.  
  
 Пример приложения см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Дополнительные сведения о [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика членства, см. [как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях. Разработчики Windows Communication Foundation (WCF) можно воспользоваться преимуществами этих функций в целях безопасности. При интеграции в приложение WCF, пользователи должны предоставлять сочетание имени и пароля пользователя клиентского приложения WCF. Чтобы включить WCF использовать базу данных, необходимо создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> класса, задайте его <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> свойства <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>и добавить экземпляр в коллекцию поведений <xref:System.ServiceModel.ServiceHost> , на котором размещена служба.  
  
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
 [Практическое руководство. Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
