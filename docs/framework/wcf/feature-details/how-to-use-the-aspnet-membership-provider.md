---
title: Практическое руководство. Использование поставщика членства ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 8011b026e857dd6e5815ef7da00c1c33db8b5b4d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310360"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Практическое руководство. Использование поставщика членства ASP.NET
Поставщик членства в среде [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] - это функция, которая позволяет разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-узлы с возможностью создания пользователями уникальных комбинаций имени пользователя и пароля. Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать узел и его службы.  
  
 Образец приложения, см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Дополнительные сведения об использовании [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика ролей см. в разделе [как: Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 Возможность членства требует использования базы данных SQL Server для хранения сведений о пользователе. Эта возможность также включает методы напоминания пользователю его пароля с помощью специального вопроса.  
  
 Windows Communication Foundation (WCF) разработчикам воспользоваться преимуществами этих функций в целях безопасности. При интеграции в приложение WCF, пользователям необходимо ввести сочетание имя/пароль пользователя клиентскому приложению WCF. Чтобы передать данные в службу WCF, использовать привязку, которая поддерживает учетные данные имени и пароля пользователя, такие как <xref:System.ServiceModel.WSHttpBinding> (в конфигурации, [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) и задать тип учетных данных для клиента`UserName`. В службе безопасности WCF проверяет подлинность пользователя на основе имени пользователя и пароля и назначает роль, заданную [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] роли.  
  
> [!NOTE]
>  WCF не поддерживает методы для заполнения базы данных с помощью сочетания имени и пароля пользователя или другие сведения о пользователе.  
  
### <a name="to-configure-the-membership-provider"></a>Настройка поставщика членства  
  
1. В файле Web.config в разделе <`system.web`> элемент, создайте <`membership`> элемента.  
  
2. В элементе `<membership>`<providers> создайте элемент`<providers>`.  
  
3. Дочерний элемент <`providers`> элемента, добавьте `<clear />` элемент, чтобы записать коллекцию поставщиков.  
  
4. В разделе `<clear />` элемент, создайте <`add`> задайте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, и `passwordFormat`. Атрибут `name` используется далее в качестве значения в файле конфигурации. В следующем примере задается значение `SqlMembershipProvider`.  
  
     В следующем примере демонстрируется раздел конфигурации.  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>Настройка системы безопасности службы на прием сочетания имя/пароль пользователя  
  
1. В файле конфигурации в разделе [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемент.  
  
2. Добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) в раздел привязок. Дополнительные сведения о создании элемента привязки WCF, см. в разделе [как: Указание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3. Задайте атрибуту `mode` элемента `<security>` значение `Message`.  
  
4. Задайте `clientCredentialType` атрибут <`message`> элемент `UserName`. В этом случае пара "имя пользователя и пароль" будет использоваться в качестве учетной записи клиента.  
  
     В следующем примере показан код конфигурации для привязки.  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a>Настройка службы на использование поставщика членства  
  
1. Дочерний элемент `<system.serviceModel>` элемента, добавьте [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент  
  
2. Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемента.  
  
3. Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и задайте `name` атрибут соответствующее значение.  
  
4. Добавить [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) для <`behavior`> элемента.  
  
5. Добавить [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) для `<serviceCredentials>` элемент.  
  
6. Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Если `userNamePasswordValidationMode` значение не задано, WCF использует проверку подлинности Windows вместо [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поставщика членства.  
  
7. Задайте для атрибута `membershipProviderName` значение "имя поставщика" (указывается при добавлении поставщика в первой процедуре данного раздела). В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Пример  
 В следующем коде показана конфигурация службы, использующей возможность членства в ASP.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
