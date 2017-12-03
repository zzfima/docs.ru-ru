---
title: "Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1ec4dc2d7f066d79b2cf54c3d474b47e769b626c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
Когда для проверки подлинности используются имя пользователя и пароль, по умолчанию [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует Windows для проверки имени пользователя и пароля. Тем не менее [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет пользовательского имени и пароля схем проверки подлинности, также известный как *проверяющие элементы управления*. Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.  
  
 Пример приложения см. в разделе [проверяющий элемент управления пароль для имени пользователя](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a>Создание пользовательского проверяющего элемента управления для имени пользователя и пароля  
  
1.  Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.  
  
     Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля  
  
1.  Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).  
  
     При использовании безопасности сообщений, добавьте одну из привязок, предоставляемых системой, такие как [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), или [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) безопасность сообщений поддерживает и `UserName` тип учетных данных.  
  
     При использовании безопасности на уровне транспорта по HTTP (S), либо добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) или [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , использующий HTTP (S) и `Basic` схему проверки подлинности.  
  
    > [!NOTE]
    >  Если используется платформа [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] или более поздняя версия, на уровне безопасности сообщений и транспорта можно применять пользовательский модуль проверки имени пользователя и пароля. Если используется платформа [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], пользовательский модуль проверки имени пользователя и пароля можно использовать только на уровне безопасности сообщений.  
  
    > [!TIP]
    >  Дополнительные сведения об использовании \<netTcpBinding > в этом контексте. в разделе [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1.  В файле конфигурации в разделе [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемента.  
  
    2.  Добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемент для раздела привязок. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] элемент привязки в разделе [как: задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3.  Задать `mode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) для `Message`, `Transport`, `or``TransportWithMessageCredential`.  
  
    4.  Задать `clientCredentialType` атрибут [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [ \<транспорта >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).  
  
         При использовании безопасности сообщений, установить `clientCredentialType` атрибут [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) для `UserName`.  
  
         При использовании безопасности на уровне транспорта по HTTP (S), установить `clientCredentialType` атрибут [ \<транспорта >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [ \<транспорта >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) для `Basic`.  
  
        > [!NOTE]
        >  Если служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] размещена на сервере служб IIS, на котором используется безопасность на уровне транспорта, а свойству <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> присвоено значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, в пользовательской схеме проверки подлинности используется подмножество возможностей проверки подлинности Windows. Это происходит потому, что в данном случае службы IIS выполняют проверку подлинности Windows перед вызовом службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] пользовательского модуля проверки подлинности.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] элемент привязки в разделе [как: задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
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
  
2.  Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.  
  
    1.  Как дочерние для [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента.  
  
    2.  Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента.  
  
    3.  Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) и присвойте `name` соответствующее значение атрибута.  
  
    4.  Добавить [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) для [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемента.  
  
    5.  Добавить [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) для [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
    6.  Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.  
  
        > [!IMPORTANT]
        >  Если значение `userNamePasswordValidationMode` не задано, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует проверку подлинности Windows вместо пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.  
  
    7.  Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.  
  
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
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>  
 [Как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 [Проверка подлинности](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
