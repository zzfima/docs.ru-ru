---
title: Практическое руководство. Использование поставщика членства ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 5b15d56c7150a8478bc32651538903778e3b877d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184797"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Практическое руководство. Использование поставщика членства ASP.NET

Поставщик ASP.NET членства — это функция, которая позволяет разработчикам ASP.NET создавать веб-сайты, позволяющие пользователям создавать уникальные комбинации имен пользователей и паролей. Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого, любой пользователь, который поставляет свои учетные данные (комбинация имени пользователя / пароля) может использовать сайт и его услуги.

Для примера приложения [см.](../../../../docs/framework/wcf/samples/membership-and-role-provider.md) Для получения информации об использовании функции поставщика ASP.NET роли [ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)см.

Возможность членства требует использования базы данных SQL Server для хранения сведений о пользователе. Эта возможность также включает методы напоминания пользователю его пароля с помощью специального вопроса.

Разработчики Windows Communication Foundation (WCF) могут воспользоваться этими функциями в целях безопасности. При интеграции в приложение WCF пользователи должны предоставить клиентское приложение WCF комбинацию имени пользователя/пароля. Для передачи данных в службу WCF используйте привязку, поддерживающую учетные данные имени пользователя/пароля, такие как <xref:System.ServiceModel.WSHttpBinding> (в конфигурации, [ \<wsHttpBinding>) ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)и установите тип учетных данных `UserName`клиента. На службе служба безопасности WCF проверяет подлинность пользователя на основе имени пользователя и пароля, а также назначает роль, указанную ASP.NET роль.

> [!NOTE]
> WCF не предоставляет методы заполнения базы данных комбинациями имени/паролем пользователя или другой информацией пользователя.

### <a name="to-configure-the-membership-provider"></a>Настройка поставщика членства

1. В файле Web.config под `system.web` элементом <`membership`> создается элемент <>.

2. В элементе `<membership>`.

3. Как ребенок, чтобы `providers` <> `<clear />` элемент, добавьте элемент, чтобы промыть коллекцию поставщиков.

4. Под `<clear />` элементом создайте `add` элемент <> со следующими атрибутами, установленными `enablePasswordReset` `requiresQuestionAndAnswer`на `requiresUniqueEmail`соответствующие значения: `name`, `type` `connectionStringName`, `applicationName` `enablePasswordRetrieval`, , , , , и `passwordFormat`. Атрибут `name` используется далее в качестве значения в файле конфигурации. В следующем примере задается значение `SqlMembershipProvider`.

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

1. В файле конфигурации, под [ \<элементом system.serviceModel>,](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) добавьте [ \<привязки>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемент.

2. Добавьте [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) в раздел привязки. Для получения дополнительной информации о создании элемента связывания WCF [см.](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)

3. Задайте атрибуту `mode` элемента `<security>` значение `Message`.

4. Установите `clientCredentialType` атрибут элемента `message` <`UserName`>. В этом случае пара "имя пользователя и пароль" будет использоваться в качестве учетной записи клиента.

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

1. Как ребенок, `<system.serviceModel>` добавляйте [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент поведения

2. Добавьте><`behaviors`> элемента [ \<serviceBehaviors.](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)

3. Добавьте [ \<поведение>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и установите `name` атрибут соответствующим значением.

4. Добавьте [ \<>serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) `behavior` в элемент <>.

5. Добавьте к элементу `<serviceCredentials>` [ \<>userNameAuthentication.](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)

6. Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.

    > [!IMPORTANT]
    > Если `userNamePasswordValidationMode` значение не установлено, WCF использует аутентификацию Windows вместо ASP.NET поставщика членства.

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

## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
