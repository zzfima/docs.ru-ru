---
title: Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 98ffad7e717aac949509fa701c77d8ba2b80a695
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834696"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля

По умолчанию, если для проверки подлинности используется имя пользователя и пароль, Windows Communication Foundation (WCF) использует Windows для проверки имени пользователя и пароля. Однако WCF позволяет создавать пользовательские схемы проверки подлинности имени пользователя и пароля, которые также называются *проверяющими*. Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.

Пример приложения см. в разделе [средство проверки пароля для имени пользователя](../samples/user-name-password-validator.md).

### <a name="to-create-a-custom-user-name-and-password-validator"></a>Создание пользовательского проверяющего элемента управления для имени пользователя и пароля

1. Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.

    Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля

1. Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).

    При использовании безопасности сообщений добавьте одну из предоставляемых системой привязок, например [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)или [> \<customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , которая поддерживает безопасность сообщений и тип учетных данных `UserName`.

    При использовании безопасности на транспортном уровне по HTTP (S) добавьте [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) или [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md), @no__t [5NetTcpBinding >](../../configure-apps/file-schema/wcf/nettcpbinding.md) или @no__t [-7customBinding >](../../configure-apps/file-schema/wcf/custombinding.md) , использующих HTTP (S), и Схема проверки подлинности `Basic`.

    > [!NOTE]
    > Если используется платформа [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] или более поздняя версия, на уровне безопасности сообщений и транспорта можно применять пользовательский модуль проверки имени пользователя и пароля. С помощью WinFX пользовательское средство проверки имени пользователя и пароля может использоваться только с защитой сообщений.

    > [!TIP]
    > Дополнительные сведения об использовании \<netTcpBinding > в этом контексте см. в разделе [\<security >](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).

    1. В файле конфигурации в элементе [> \<system. ServiceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) добавьте элемент [\<bindings >](../../configure-apps/file-schema/wcf/bindings.md) .

    2. Добавьте элемент [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) или [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязки. Дополнительные сведения о создании элемента привязки WCF см. в разделе [How to: Укажите привязку службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).

    3. Установите атрибут `mode` [> \<security](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [\<security](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) > в `Message`, `Transport` или `TransportWithMessageCredential`.

    4. Задайте атрибут `clientCredentialType` для > [\<message >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [\<transport](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).

        При использовании безопасности сообщений установите атрибут `clientCredentialType` [> \<message](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) в значение `UserName`.

        При использовании безопасности на транспортном уровне через HTTP (S) установите атрибут `clientCredentialType` для [\<transport >](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [\<transport >](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) в `Basic`.

        > [!NOTE]
        > Если служба WCF размещается в службы IIS (IIS) с использованием безопасности на транспортном уровне, а свойство <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> имеет значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, то настраиваемая схема проверки подлинности использует подмножество проверки подлинности Windows. Это связано с тем, что в этом случае IIS выполняет проверку подлинности Windows перед тем, как WCF вызовет настраиваемую проверку подлинности.

    Дополнительные сведения о создании элемента привязки WCF см. в разделе [How to: Укажите привязку службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).

    В следующем примере показан код конфигурации для привязки:

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.

    1. В качестве дочернего элемента [\<system. serviceModel >](../../configure-apps/file-schema/wcf/system-servicemodel.md) добавьте элемент [\<behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    2. Добавьте [> \<serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) в элемент [\<behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    3. Добавьте элемент [\<behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) и задайте для атрибута `name` соответствующее значение.

    4. Добавьте [> \<serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md) в элемент [\<behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .

    5. Добавьте [> @no__t 1userNameAuthentication](../../configure-apps/file-schema/wcf/usernameauthentication.md) в [> \<serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md).

    6. Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.

        > [!IMPORTANT]
        > Если значение `userNamePasswordValidationMode` не задано, WCF использует проверку подлинности Windows вместо настраиваемого средства проверки имени пользователя и пароля.

    7. Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.

    В следующем примере показан фрагмент `<serviceCredentials>` до этой точки:

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>Пример

В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля. Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Практическое руководство. Использование поставщика членства ASP.NET @ no__t-0
- [Authentication](authentication-in-wcf.md)
