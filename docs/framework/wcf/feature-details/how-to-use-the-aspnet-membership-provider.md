---
title: "Как использовать поставщик членства ASP.NET | Microsoft Docs"
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
  - "WCF и ASP.NET"
  - "WCF, авторизация"
  - "WCF, безопасность"
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Как использовать поставщик членства ASP.NET
Поставщик членства в среде [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] — это функция, которая позволяет разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб\-узлы с возможностью создания пользователями уникальных комбинаций имени пользователя и пароля.Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам.В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.Вместо этого любой пользователь, который предоставляет свои учетные данные \(сочетание имени пользователя и пароля\), может использовать узел и его службы.  
  
 Пример приложения см. в разделе [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).Сведения об использовании функции поставщика ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] см. в разделе [Как использовать поставщик ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 Функция членства требует использования базы данных SQL Server для хранения сведений о пользователе.Эта функция также включает методы напоминания пользователю его пароля с помощью специального вопроса.  
  
 Разработчики [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут воспользоваться преимуществами этих функций в целях безопасности.Когда эти функции интегрированы в приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], пользователи должны предоставлять сочетание имя\/пароль пользователя клиентскому приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Для передачи данных службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используйте привязку, которая поддерживает учетные данные \(имя и пароль пользователя\), например <xref:System.ServiceModel.WSHttpBinding> \(в конфигурации, [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\), и установите тип учетных данных клиента на `UserName`.В службе система безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет подлинность пользователя по имени и паролю пользователя и назначает роль, заданную ролью [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не предусмотрены какие\-либо методы для заполнения базы данных сочетаниями имени\/пароля пользователя или другими сведениями о пользователе.  
  
### Настройка поставщика участия  
  
1.  В элементе \<`system.web`\> файла Web.config создайте элемент \<`membership`\>.  
  
2.  В элементе `<membership>``<providers> создайте элемент` .  
  
3.  Добавьте элемент \<`providers`\> в качестве дочернего к элементу `<clear />`, чтобы записать коллекцию поставщиков.  
  
4.  В элементе `<clear />`\< `создайте элемент add`\>`name со следующими атрибутами, для которых заданы соответствующие значения:` `type,` `connectionStringName,` `applicationName,` `enablePasswordRetrieval,` `enablePasswordReset,` `requiresQuestionAndAnswer,` `requiresUniqueEmail,` `passwordFormat и` .Атрибут `name` используется далее в качестве значения в файле конфигурации.В следующем примере ему задается значение `SqlMembershipProvider`.  
  
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
  
### Настройка системы безопасности службы на прием сочетания имя\/пароль пользователя.  
  
1.  Добавьте элемент [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) в элемент  [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) файла конфигурации.  
  
2.  Добавьте элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) в раздел привязок.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] создании элемента привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Как задать привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Задайте для атрибута `mode` элемента `<security>``Message значение` .  
  
4.  Задайте для атрибута `clientCredentialType` элемента \<`message`\> значение `UserName`.В этом случае пара «имя пользователя и пароль» будет использоваться в качестве учетной записи клиента.  
  
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
  
### Настройка службы на использование поставщика участия  
  
1.  Добавьте элемент [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) в качестве дочернего для элемента `<system.serviceModel>`.  
  
2.  Добавьте элемент [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) в элемент \<`behaviors`\>.  
  
3.  Добавьте элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и задайте соответствующее значение для атрибута `name`.  
  
4.  Добавьте элемент [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)\<`behavior в элемент` \>.  
  
5.  Добавьте элемент [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) в элемент `<serviceCredentials>`.  
  
6.  Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Если значение `userNamePasswordValidationMode` не задано, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует проверку подлинности Windows вместо поставщика участия [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
7.  Задайте для атрибута `membershipProviderName` значение «имя поставщика» \(указывается при добавлении поставщика в первой процедуре данного раздела\).В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.  
  
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
  
## Пример  
 В следующем коде показана конфигурация службы, использующей функцию членства в ASP.  
  
```  
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
  
## См. также  
 [Как использовать поставщик ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)   
 [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)