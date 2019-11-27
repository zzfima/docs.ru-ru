---
title: Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 3d01a29671f42e80fdb7ca45223007aa60273ba9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283261"
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

    При использовании безопасности сообщений добавьте одну из предоставляемых системой привязок, например [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)или [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , которая поддерживает безопасность сообщений и тип учетных данных `UserName`.

    При использовании безопасности на транспортном уровне через HTTP (S) добавьте [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) или [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md), [\<netTcpBinding >](../../configure-apps/file-schema/wcf/nettcpbinding.md) или [\<CustomBinding >](../../configure-apps/file-schema/wcf/custombinding.md) , который использует HTTP (S) и схему проверки подлинности `Basic`.

    > [!NOTE]
    > При использовании .NET Framework 3,5 или более поздних версий можно использовать пользовательское средство проверки имени пользователя и пароля с защитой сообщений и транспорта. С помощью WinFX пользовательское средство проверки имени пользователя и пароля может использоваться только с защитой сообщений.

    > [!TIP]
    > Дополнительные сведения об использовании \<netTcpBinding > в этом контексте см. в разделе [\<security >](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).

    1. В файле конфигурации в элементе [\<System. serviceModel >](../../configure-apps/file-schema/wcf/system-servicemodel.md) добавьте элемент [\<привязки >](../../configure-apps/file-schema/wcf/bindings.md) .

    2. Добавьте элемент [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) или [\<BasicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязки. Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).

    3. Задайте атрибут `mode` [\<безопасности >](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [\<](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) > `Message`, `Transport`или `TransportWithMessageCredential`.

    4. Задайте атрибут `clientCredentialType` [\<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [\<транспортного >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).

        При использовании безопасности сообщений задайте для атрибута `clientCredentialType` [\<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) значение `UserName`.

        При использовании безопасности на транспортном уровне через HTTP (S) установите атрибут `clientCredentialType`\<транспортного [>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [\<транспортного >](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) в `Basic`.

        > [!NOTE]
        > Если служба WCF размещается в службы IIS (IIS) с использованием безопасности на транспортном уровне, а свойство <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> имеет значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, то настраиваемая схема проверки подлинности использует подмножество проверки подлинности Windows. Это связано с тем, что в этом случае IIS выполняет проверку подлинности Windows перед тем, как WCF вызовет настраиваемую проверку подлинности.

    Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).

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

    1. В качестве дочернего элемента [\<System. serviceModel >](../../configure-apps/file-schema/wcf/system-servicemodel.md) добавьте элемент [\<Behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    2. Добавьте [\<serviceBehaviors >](../../configure-apps/file-schema/wcf/servicebehaviors.md) в элемент [\<Behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    3. Добавьте элемент [\<behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) и задайте для атрибута `name` соответствующее значение.

    4. Добавьте [\<serviceCredentials >](../../configure-apps/file-schema/wcf/servicecredentials.md) в элемент [> поведения\<](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .

    5. Добавьте [\<усернамеаусентикатион >](../../configure-apps/file-schema/wcf/usernameauthentication.md) в [>\<ServiceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md).

    6. Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.

        > [!IMPORTANT]
        > Если значение `userNamePasswordValidationMode` не задано, WCF использует проверку подлинности Windows вместо настраиваемого средства проверки имени пользователя и пароля.

    7. Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.

    В следующем примере показан фрагмент `<serviceCredentials>` к этому моменту:

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
- [Практическое руководство. Использование поставщика членства ASP.NET](how-to-use-the-aspnet-membership-provider.md)
- [Проверка подлинности](authentication-in-wcf.md)
