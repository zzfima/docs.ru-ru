---
title: "Как использовать пользовательский проверяющий элемент управления для имени пользователя и пароля | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, имя пользователя и пароль"
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Как использовать пользовательский проверяющий элемент управления для имени пользователя и пароля
Когда для проверки подлинности используются имя пользователя и пароль, по умолчанию [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует Windows для проверки имени пользователя и пароля.Однако [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет применение пользовательских схем проверки подлинности имени пользователя и пароля, которые также известны как *проверяющие элементы управления*.Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.  
  
 Пример приложения см. в разделе [Проверяющий элемент управления для имен пользователей и паролей](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### Создание пользовательского проверяющего элемента управления для имени пользователя и пароля  
  
1.  Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.  
  
     Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля  
  
1.  Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP\(S\).  
  
     При использовании системы безопасности сообщений добавьте одну из привязок, предоставляемых системой, например [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), поддерживающих безопасность сообщений и тип учетных данных `UserName`.  
  
     При использовании безопасности на уровне транспорта по протоколу HTTP\(S\) добавьте элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) или [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), который использует протокол HTTP\(S\) и схему проверки подлинности `Basic`.  
  
    > [!NOTE]
    >  Если используется платформа [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] или более поздняя версия, на уровне безопасности сообщений и транспорта можно применять пользовательский модуль проверки имени пользователя и пароля.Если используется платформа [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], пользовательский модуль проверки имени пользователя и пароля можно использовать только на уровне безопасности сообщений.  
  
    > [!TIP]
    >  Дополнительные сведения об использовании привязки \<netTcpBinding\> в данном контексте см. в разделе [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md).  
  
    1.  Добавьте в раздел [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) файла конфигурации элемент [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
    2.  Добавьте элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязок.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] создании элемента привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Как задать привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3.  Присвойте атрибуту `mode` элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) значение `Message`, `Transport`, `or``TransportWithMessageCredential`.  
  
    4.  Задайте атрибут `clientCredentialType` элемента [\<сообщение\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [\<транспорт\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).  
  
         При использовании безопасности сообщений присвойте атрибуту `clientCredentialType` элемента [\<сообщение\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) значение `UserName`.  
  
         При использовании безопасности на уровне транспорта по HTTP\(S\) задайте для атрибута `clientCredentialType` элемента [\<транспорт\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [\<транспорт\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) значение `Basic`.  
  
        > [!NOTE]
        >  Если служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] размещена на сервере служб IIS, на котором используется безопасность на уровне транспорта, а свойству <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> присвоено значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>, в пользовательской схеме проверки подлинности используется подмножество возможностей проверки подлинности Windows.Это происходит потому, что в данном случае службы IIS выполняют проверку подлинности Windows перед вызовом службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] пользовательского модуля проверки подлинности.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] создании элемента привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Как задать привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
     В следующем примере показан код конфигурации для привязки.  
  
    ```  
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
  
2.  Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.  
  
    1.  Добавьте элемент [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) в качестве дочернего для элемента [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
    2.  Добавьте элемент [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) в элемент [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
    3.  Добавьте элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) и присвойте атрибуту `name` соответствующее значение.  
  
    4.  Добавьте элемент [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) в элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md).  
  
    5.  Добавьте элемент [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) в элемент [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
    6.  Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.  
  
        > [!IMPORTANT]
        >  Если значение `userNamePasswordValidationMode` не задано, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует проверку подлинности Windows вместо пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.  
  
    7.  Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.  
  
     В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.  
  
    ```  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## Пример  
 В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля.Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## См. также  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>   
 [Как использовать поставщик членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)   
 [Аутентификация](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)