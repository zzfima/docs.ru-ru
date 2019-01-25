---
title: Обзор модуля аутентификации WSFederation
ms.date: 03/30/2017
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
author: BrucePerlerMS
ms.openlocfilehash: cebdb0e69ae151afd9a1cc422cf48a201176313a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703670"
---
# <a name="wsfederation-authentication-module-overview"></a>Обзор модуля аутентификации WSFederation
Windows Identity Foundation (WIF) поддерживает федеративную проверку подлинности в приложениях ASP.NET с помощью модуля проверки подлинности WS-Federated (WS-FAM). В этом разделе объясняются принципы работы федеративной проверки подлинности и способы ее применения.  
  
### <a name="overview-of-federated-authentication"></a>Общие сведения о федеративной проверке подлинности  
 Федеративная проверка подлинности позволяет службе маркеров безопасности (STS), находящейся в одном домене доверия, предоставлять сведения о проверке подлинности службе STS, находящейся в другом домене доверия, если между этими доменами установлено отношение доверия. Пример представлен на приведенном ниже рисунке.  
  
 ![Сценарий федеративной проверки подлинности](../../../docs/framework/security/media/federatedauthentication.gif "FederatedAuthentication")  
  
1.  Клиент в домене доверия Fabrikam отправляет запрос приложению проверяющей стороны в домене доверия Contoso.  
  
2.  Проверяющая сторона перенаправляет клиент в службу STS в домене доверия Contoso. Эта служба не имеет сведений о клиенте.  
  
3.  Служба STS Contoso перенаправляет клиент в службу STS в домене доверия Fabrikam, с которым у домена Contoso установлено отношение доверия.  
  
4.  Служба STS Fabrikam проверяет удостоверение клиента и выпускает токен безопасности для службы STS Contoso.  
  
5.  Служба STS Contoso создает на основе токена Fabrikam собственный токен, распознаваемый проверяющей стороной, и отправляет его проверяющей стороне.  
  
6.  Проверяющая сторона извлекает из токена безопасности утверждения клиента и принимает решение об авторизации.  
  
### <a name="using-the-federated-authentication-module-with-aspnet"></a>Использование модуля федеративной проверки подлинности с ASP.NET  
 Модуль <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WS-FAM) представляет собой HTTP-модуль, позволяющий добавить в приложение [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] поддержку федеративной проверки подлинности. Федеративная проверка подлинности позволяет делегировать обработку логики проверки подлинности службе STS, чтобы вы могли сосредоточиться на написании бизнес-логики.  
  
 При настройке модуля WS-FAM необходимо указать службу STS, в которую будут перенаправляться запросы, не прошедшие проверку подлинности. WIF позволяет проверять подлинность пользователя двумя способами.  
  
1.  Пассивного перенаправления: Когда не прошедший проверку пользователь пытается получить доступ к защищенному ресурсу, и вы хотите просто перенаправить их в службу STS, без необходимости страницу входа, то это правильного подхода. Служба STS проверяет удостоверение пользователя и выпускает токен безопасности, содержащий необходимые утверждения для этого пользователя. Для реализации этого подхода необходимо добавить в конвейер модулей HTTP модуль WS-FAM. Чтобы настроить использование модуля WS-FAM и федерацию со службой STS, можно изменить файл конфигурации с помощью средства Identity and Access Tool для Visual Studio 2012. Дополнительные сведения см. в разделе [Средство Identity and Access Tool для Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
2.  Можно вызвать метод <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=nameWithType> или <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A> из кода программной части страницы входа в приложении проверяющей стороны.  
  
 При пассивном перенаправлении обмен данными происходит посредством ответа или перенаправления из клиента (как правило, браузера). Вы можете добавить модуль WS-FAM в конвейер HTTP приложения, где этот модуль будет отслеживать запросы не прошедших проверку пользователей и перенаправлять таких пользователей в указанную службу STS.  
  
 Модуль WS-FAM также создает несколько событий, позволяющих настроить его функции в приложении [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
### <a name="how-the-ws-fam-works"></a>Принципы работы модуля WS-FAM  
 Модуль WS-FAM реализован в классе <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>. Как правило, модуль WS-FAM добавляется в конвейер HTTP приложения проверяющей стороны [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Когда не прошедший проверку пользователь пытается получить доступ к защищенному ресурсу, проверяющая сторона возвращает ответ HTTP "401 в авторизации отказано". Модуль WS-FAM перехватывает этот ответ, не позволяя клиенту получить его, и перенаправляет пользователя в указанную службу STS. Служба STS выпускает токен безопасности, который опять перехватывается модулем WS-FAM. На основе этого токена модуль WS-FAM создает для прошедшего проверку пользователя экземпляр класса <xref:System.Security.Claims.ClaimsPrincipal>, который позволяет применить обычные механизмы авторизации [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
 Так как протокол HTTP не отслеживает состояние, необходимо предусмотреть механизм, позволяющий избежать повторения этого процесса при каждой попытке доступа пользователя к защищенному ресурсу. Для этого используется модуль <xref:System.IdentityModel.Services.SessionAuthenticationModule>. Когда служба STS выпускает для пользователя токен безопасности, модуль <xref:System.IdentityModel.Services.SessionAuthenticationModule> создает для пользователя токен безопасности сеанса и сохраняет этот токен в файле cookie. При последующих запросах модуль <xref:System.IdentityModel.Services.SessionAuthenticationModule> перехватывает этот файл cookie и восстанавливает с его помощью объект <xref:System.Security.Claims.ClaimsPrincipal> пользователя.  
  
 На приведенной ниже схеме показан поток данных при пассивном перенаправлении. Запрос автоматически перенаправляется через службу STS для установления учетных данных без использования страницы входа.  
  
 ![Временная диаграмма входа с использованием пассивного перенаправления](../../../docs/framework/security/media/signinusingpassiveredirect.gif "SignInUsingPassiveRedirect")  
  
 На приведенной ниже схеме подробно показано, что происходит при проверке подлинности пользователя в службе STS и обработке маркеров безопасности модулем <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
 ![Временная диаграмма обработки токенов с использованием пассивного перенаправления](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.gif "SignInUsingPassiveRedirect_TokenProcessing")  
  
 На приведенной ниже схеме подробно показано, что происходит при сериализации маркеров безопасности пользователя в файлы cookie, перехватываемые модулем <xref:System.IdentityModel.Services.SessionAuthenticationModule>.  
  
 ![Временная диаграмма SAM, отражающая вход с использованием элементов управления](../../../docs/framework/security/media/signinusingconrols-sam.gif "SignInUsingConrols_SAM")  
  
### <a name="events"></a>События  
 Классы <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> и <xref:System.IdentityModel.Services.SessionAuthenticationModule> и их родительский класс <xref:System.IdentityModel.Services.HttpModuleBase> создают события на разных этапах обработки HTTP-запроса. Эти события обрабатываются в файле `global.asax` приложения [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
-   Инфраструктура ASP.NET вызывает метод <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> модуля для его инициализации.  
  
-   Событие <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=nameWithType> создается, когда инфраструктура ASP.NET впервые вызывает метод <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> для одного из модулей приложения, производных от <xref:System.IdentityModel.Services.HttpModuleBase>. Этот метод обращается к статическому свойству <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>, что приводит к загрузке конфигурации из файла Web.config. Это событие создается только при первом обращении к свойству. Доступ к объекту <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>, который инициализируется на основе конфигурации, возможен посредством свойства <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> в обработчике событий. С помощью этого события можно изменить конфигурацию, прежде чем она будет применена к каким-либо модулям. Обработчик для этого события можно добавить в методе Application_Start:  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     Каждый модуль переопределяет абстрактные методы <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=nameWithType> и <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=nameWithType>. Первый из этих методов добавляет обработчики для событий конвейера ASP.NET, которые важны для модуля. В большинстве случаев достаточно реализации модуля по умолчанию. Второй метод инициализирует свойства модуля на основе его свойства <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=nameWithType>. (Это ранее загруженная копия конфигурации.) Если в классах, производных от <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> или <xref:System.IdentityModel.Services.SessionAuthenticationModule>, должна поддерживаться инициализация новых свойств на основе конфигурации, может потребоваться переопределить этот второй метод. В таких случаях для поддержки дополнительных свойств конфигурации также необходимо обеспечить наследование от соответствующих объектов конфигурации, например от <xref:System.IdentityModel.Configuration.IdentityConfiguration>, <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> или <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>.  
  
-   При перехвате токена безопасности, выпущенного службой STS, модуль WS-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived>.  
  
-   После проверки токена модуль WS-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated>.  
  
-   При создании для пользователя токена безопасности сеанса модуль <xref:System.IdentityModel.Services.SessionAuthenticationModule> создает событие <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated>.  
  
-   При перехвате последующих запросов с файлом cookie, который содержит токен безопасности сеанса, модуль <xref:System.IdentityModel.Services.SessionAuthenticationModule> создает событие <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived>.  
  
-   Перед тем как перенаправить пользователя издателю, модуль WS-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>. Запрос входа WS-Federation доступен посредством свойства <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A> объекта <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs>, переданного в событии. Перед отправкой издателю запрос можно изменить.  
  
-   При успешной записи файла cookie и входе пользователя в систему модуль WS-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn>.  
  
-   Модуль WS-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut> один раз за сеанс при закрытии сеанса для каждого пользователя. Это событие не создается, если сеанс закрывается на стороне клиента (например, при удалении файла cookie сеанса). В среде с единым входом служба STS поставщика удостоверений также может отправить каждой проверяющей стороне запрос на выход из системы. В этом случае также создается это событие, в котором свойству <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> присвоено значение `true`.  
  
> [!NOTE]
>  Свойство <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> не следует использовать во время событий, создаваемых модулями <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> и <xref:System.IdentityModel.Services.SessionAuthenticationModule>. Связано это с тем, что значение свойства <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> задается после проверки подлинности, а события вызываются во время этого процесса.  
  
### <a name="configuration-of-federated-authentication"></a>Настройка федеративной проверки подлинности  
 Модули WS-FAM и SAM настраиваются с помощью элемента [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md). Дочерний элемент [\<wsFederation>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) настраивает значения по умолчанию для свойств WS-FAM, таких как <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A> и <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A>. (Эти значения можно изменять для каждого отдельного запроса, предоставляя обработчики для некоторых событий WS-FAM, например <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>.) Обработчик файлов cookie, используемый SAM, настраивается с помощью дочернего элемента [\<cookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md). WIF предоставляет обработчик файлов cookie по умолчанию, реализованный в классе <xref:System.IdentityModel.Services.ChunkedCookieHandler>, размер блоков которого можно задать с помощью элемента [\<chunkedCookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md). Элемент `<federationConfiguration>` ссылается на объект <xref:System.IdentityModel.Configuration.IdentityConfiguration>, который предоставляет конфигурацию для других компонентов WIF, используемых в приложении, таких как <xref:System.Security.Claims.ClaimsAuthenticationManager> и <xref:System.Security.Claims.ClaimsAuthorizationManager>. На конфигурацию удостоверения можно ссылаться явно, указывая именованный элемент [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) в атрибуте `identityConfigurationName` элемента `<federationConfiguration>`. Если на конфигурацию удостоверения нет явной ссылки, используется конфигурация по умолчанию.  
  
 Ниже приведен код XML для конфигурации приложения проверяющей стороны ASP.NET. Разделы конфигурации <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> и <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> добавляются в элемент `<configSections>`. SAM и WS-FAM добавляются в список модулей HTTP в элементе `<system.webServer>`/`<modules>`. Наконец, компоненты WIF настраиваются в элементах `<system.identityModel>`/`<identityConfiguration>` и `<system.identityModel.services>`/`<federationConfiguration>`. Эта конфигурация задает поблочный обработчик файлов cookie, так как это обработчик файлов cookie по умолчанию, а в элементе `<cookieHandler>` не указан тип обработчика файлов cookie.  
  
> [!WARNING]
>  В приведенном ниже примере атрибут `requireHttps` элемента `<wsFederation>` и атрибут `requireSsl` элемента `<cookieHandler>` имеют значение `false`. Это может представлять угрозу безопасности. В рабочей среде обоим этим аргументам следует присваивать значение `true`.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  ...  
  
  <system.webServer>  
    <modules>  
      <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
    </modules>  
  </system.webServer>  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost:50969/" />  
      </audienceUris>  
      <certificateValidation certificateValidationMode="None" />  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
        <trustedIssuers>  
          <add thumbprint="9B74CB2F320F7AAFC156E1252270B1DC01EF40D0" name="LocalSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
    </identityConfiguration>  
  </system.identityModel>  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:15839/wsFederationSTS/Issue" realm="http://localhost:50969/" reply="http://localhost:50969/" requireHttps="false" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)
