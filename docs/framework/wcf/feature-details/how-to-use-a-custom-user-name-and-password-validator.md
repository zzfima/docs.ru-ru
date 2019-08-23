---
title: Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 57bd650caef831f3ee886c0422e13cc4149d3416
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968809"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
По умолчанию, если для проверки подлинности используется имя пользователя и пароль, Windows Communication Foundation (WCF) использует Windows для проверки имени пользователя и пароля. Однако WCF позволяет создавать пользовательские схемы проверки подлинности имени пользователя и пароля, которыетакже называются проверяющими. Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.  
  
 Пример приложения см. в разделе [средство проверки пароля для имени пользователя](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a>Создание пользовательского проверяющего элемента управления для имени пользователя и пароля  
  
1. Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2. Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.  
  
     Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля  
  
1. Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).  
  
     При использовании безопасности сообщений добавьте одну из предоставляемых системой привязок, например [ \<WSHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), или `UserName` [ \<> CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , который поддерживает безопасность сообщений и тип учетных данных.  
  
     При использовании безопасности на транспортном уровне через HTTP (S) добавьте [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) [ \<BasicHttpBinding >, NetTcpBinding > или CustomBinding > ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), использующий HTTP (S) `Basic` и схему проверки подлинности.  
  
    > [!NOTE]
    > Если используется платформа [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] или более поздняя версия, на уровне безопасности сообщений и транспорта можно применять пользовательский модуль проверки имени пользователя и пароля. С помощью WinFX пользовательское средство проверки имени пользователя и пароля может использоваться только с защитой сообщений.  
  
    > [!TIP]
    >  Дополнительные сведения об использовании \<> NetTcpBinding в этом контексте см. в разделе [ \<безопасность >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1. В файле [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) конфигурации [ в\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элементе System. ServiceModel > Добавьте привязки > элемент.  
  
    2. Добавьте элемент привязки [ \<WSHttpBinding > или BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязок. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Дополнительные сведения о создании элемента привязки WCF см. в разделе [как Укажите привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3. Задайтедля`Message` [атрибута > \<безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [ \<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) значение, `Transport`или .`TransportWithMessageCredential` `mode`  
  
    4. `clientCredentialType` Задайте атрибут [ >сообщенияилитранспортного>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)  
  
         При использовании безопасности сообщений задайте `clientCredentialType` атрибуту [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) `UserName`значение.  
  
         При использовании безопасности на транспортном уровне через HTTP (S) задайте `clientCredentialType` для `Basic`атрибута [ \<> транспорта](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [ \<транспортного >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) значение.  
  
        > [!NOTE]
        >  Если служба WCF размещается в службы IIS (IIS) с использованием безопасности на транспортном <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> уровне <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, а свойство имеет значение, настраиваемая схема проверки подлинности использует подмножество проверки подлинности Windows. Это связано с тем, что в этом случае IIS выполняет проверку подлинности Windows перед тем, как WCF вызовет настраиваемую проверку подлинности.  
  
     Дополнительные сведения о создании элемента привязки WCF см. в разделе [как Укажите привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
     В следующем примере показан код конфигурации для привязки.  
  
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
  
    1. В качестве [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) дочернего [ \<элемента System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) добавьте элемент Behaviors >.  
  
    2. Добавьте > serviceBehaviors в элемент [ Behaviors>\<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) . [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)  
  
    3. Добавьте элемент [Behavior > и присвойте атрибуту соответствующее значение. \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) `name`  
  
    4. Добавьте > ServiceCredentials в элемент > [ поведения.\<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)  
  
    5. Добавьте [> усернамеаусентикатион в > ServiceCredentials. \<](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)  
  
    6. Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.  
  
        > [!IMPORTANT]
        >  `userNamePasswordValidationMode` Если значение не задано, WCF использует проверку подлинности Windows вместо настраиваемого средства проверки имени пользователя и пароля.  
  
    7. Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.  
  
     В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля. Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Практическое руководство. Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [Authentication](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
