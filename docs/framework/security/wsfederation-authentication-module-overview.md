---
title: "Обзор модуля аутентификации WSFederation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Обзор модуля аутентификации WSFederation
Основой \(WIF\) идентификатора Windows включает поддержку федеративной проверки подлинности в приложениях ASP.NET через WS\- федеративный модуль проверки подлинности \(WS\-FAM\).  В этом разделе, позволяет понять, как работает федеративная проверки подлинности и его использования.  
  
### Общие сведения о федеративной проверки подлинности  
 Федеративная проверка подлинности позволяет службе маркеров безопасности \(STS\) в одном домене доверия, чтобы предоставить сведения о проверке подлинности в службе маркеров безопасности в другом домене доверия при отношение доверия между доменами 2.  Пример этого показан на следующем рисунке.  
  
 ![Сценарий аутентификации федерации](../../../docs/framework/security/media/federatedauthentication.png "FederatedAuthentication")  
  
1.  Клиент в домене доверия Fabrikam отправляет запрос в приложение \(RP\) проверяющей стороны в домене доверия Contoso.  
  
2.  Категория еще не присвоена перенаправляется к службе маркеров безопасности в домене доверия Contoso.  Эта служба маркеров безопасности не имеет статью клиента.  
  
3.  Служба маркеров безопасности Contoso перенаправляется к службе маркеров безопасности в домене доверия Fabrikam, с помощью которого домен доверия Contoso имеет отношение доверия.  
  
4.  Служба маркеров безопасности проверяет Fabrikam идентификатор клиента и выдает маркер безопасности в службе маркеров безопасности Contoso.  
  
5.  Служба маркеров безопасности Contoso использует токен Fabrikam, чтобы создать собственный токен, который может использоваться категорией еще не присвоена и отправляет его в категории еще не присвоена.  
  
6.  Категория еще не присвоена извлекает выдачи клиента из маркера безопасности и принимает решение авторизации.  
  
### Использование федеративный модуль проверки подлинности в ASP.NET  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(\), WS\-FAM HTTP\-модуля позволяет добавлять федеративная проверки подлинности в приложение [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  Федеративная проверка подлинности позволяет логики проверки подлинности обрабатываемые службой маркеров безопасности и позволяет сосредоточиться на бизнес\-логике материала.  
  
 При настройке WS\-FAM для определения службы маркеров безопасности, которой не удостоверил запросов быть перенаправлено.  WIF позволяет проверить подлинность пользователя в 2 вариантах.  
  
1.  Passive перенаправляет: Пользователям, не прошедшим проверку, когда пользователь пытается получить доступ к защищенному ресурсу, и нужно просто перенаправить их в службу маркеров безопасности без необходимости страницы входа, то это правой подход.  Служба маркеров безопасности проверяет идентификатор пользователя, и выдает маркер безопасности, который содержит соответствующие, для этого пользователя.  Этот параметр требует WS\-FAM добавляется в конвейере HTTP\-модулей.  Можно использовать средство идентификатора и доступа для Visual Studio 2012 изменение файла конфигурации приложения для использования WS\-FAM и для слияния в федерацию со службой маркеров безопасности.  Для получения дополнительной информации см. [Средство Identity and Access Tool для Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
2.  Можно вызвать метод <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=fullName> или метод <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A> из файла кода программной части для страницы данных для входа в приложении категории еще не присвоена.  
  
 В passive перенаправление, все сообщение в ответ и выполняет перенаправление из клиента \(обычно браузера\).  Можно добавить WS\-FAM в конвейере HTTP приложения, где он проверяет, не прошедших проверку подлинности пользовательских запросов и перенаправляет пользователей к службе маркеров безопасности при определении.  
  
 WS\-FAM также создает несколько событий, которые позволяют настраивать его возможности в приложении [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
### Как работает WS\-FAM  
 WS\-FAM реализован в классе <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  Обычно добавляются WS\-FAM в конвейере HTTP приложения категории еще не присвоена [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  Пользователям, не прошедшим проверку, когда пользователь пытается получить доступ к защищенному ресурсу, категория еще не присвоена возвращает ответ «HTTP 401 авторизацией запрещен».  WS\-FAM перехватывает этот ответ вместо разрешить клиент для получения сборкой, он перенаправляет пользователя к определенной службе маркеров безопасности.  Проблемы службы маркеров безопасности маркер безопасности, который перехватывает WS\-FAM снова.  WS\-FAM использует токен для создания экземпляра <xref:System.Security.Claims.ClaimsPrincipal> для пользователей, прошедших проверку подлинности, включая обычные механизмы авторизации [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] функции.  
  
 Поскольку HTTP не имеет состояний, необходимо каким\-то образом избежать повторить этот весь процесс каждый раз, когда пользователь пытается получить доступ к защищенному ресурсу другой.  На этом этапе возникает <xref:System.IdentityModel.Services.SessionAuthenticationModule> поступает в.  При возникновении службы маркеров безопасности маркер безопасности пользователя, <xref:System.IdentityModel.Services.SessionAuthenticationModule> также создают маркер безопасности сеанса для пользователя и его лежат в COOKIE\-файле.  При последующих запросах, <xref:System.IdentityModel.Services.SessionAuthenticationModule> перехватывает это COOKIE\-файл и использует его для этой <xref:System.Security.Claims.ClaimsPrincipal> пользователя.  
  
 На следующей схеме показано, что общий поток сведений в passive перенаправляет регистр.  Запрос перенаправляется автоматически с помощью службы маркеров безопасности задать учетные данные без страницы входа в систему:  
  
 ![Временная схема для входа с помощью пассивного перенаправления](../../../docs/framework/security/media/signinusingpassiveredirect.png "SignInUsingPassiveRedirect")  
  
 На следующей схеме показаны подробные сведения о, что происходит, когда пользователь проверку подлинности в службе маркеров безопасности и их маркеры безопасности обрабатываются <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>:  
  
 ![Временной интервал для обработки токена с помощью пассивного перенаправления](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.png "SignInUsingPassiveRedirect\_TokenProcessing")  
  
 На следующей схеме показаны подробные сведения о том, что произойдет при маркеры безопасности пользователя были сериализованы в COOKIE\-файл и перехвачены <xref:System.IdentityModel.Services.SessionAuthenticationModule>:  
  
 ![Временная схема SAM, показывающая вход с помощью элементов управления](../../../docs/framework/security/media/signinusingconrols-sam.png "SignInUsingConrols\_SAM")  
  
### События  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>, <xref:System.IdentityModel.Services.SessionAuthenticationModule> и их родительский класс, <xref:System.IdentityModel.Services.HttpModuleBase>, создание событий на различных этапах обработки HTTP\-запроса.  Можно обработать эти события в файле `global.asax` приложения [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
-   Инфраструктура ASP.NET вызывает метод <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> модуля для инициализации модуля.  
  
-   Событие <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=fullName> возникает, когда инфраструктура ASP.NET вызывает метод <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> в первый раз в одном из модулей приложения, производные от <xref:System.IdentityModel.Services.HttpModuleBase>.  Этот метод доступ к статическому свойству <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>, что приведет конфигурацию загружается из файла web.config.  Это событие возникает только при первом это свойство доступно.  Объект <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>, инициализируется из конфигурации можно получить с помощью свойства <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> в обработчике событий.  Это событие можно использовать для изменения конфигурации, прежде чем она будет применяться к любым модули.  Можно добавить обработчик для этого события в методе Application\_Start:  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     Каждый модуль переопределяет методы допустимы <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=fullName> и <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=fullName>.  Первый из этих методов добавляет обработчики событий конвейера ASP.NET, представляющие интерес в модуль.  В большинстве случаев реализация по умолчанию модуля является достаточным.  Второй из этих методов инициализирует свойства модуля из свойства <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=fullName>. \(Эта копия конфигурации, которая ранее была загружена\). Можно переопределить этот второй метод, если требуется поддерживать инициализацию из новых свойств конфигурации, в классах, производных от <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> или <xref:System.IdentityModel.Services.SessionAuthenticationModule>.  В таких случаях требуется также будет требуется наследовать соответствующих объектов конфигурации для поддержки добавленные свойства конфигурации; например, в <xref:System.IdentityModel.Configuration.IdentityConfiguration>, <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> или <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>.  
  
-   WS\-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived> при его перехватывает маркер безопасности, который был выпущен службой маркеров безопасности.  
  
-   WS\-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated> после его проверило токен.  
  
-   <xref:System.IdentityModel.Services.SessionAuthenticationModule> создает событие <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated> при создании сеанса маркер безопасности для пользователя.  
  
-   <xref:System.IdentityModel.Services.SessionAuthenticationModule> создает событие <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived> при его перехватывает последующие запросы с COOKIE\-файл, который содержит маркер безопасности сеанса.  
  
-   Прежде чем WS\-FAM перенаправление пользователя на эмитенту, он создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>.  Запрос данных для входа WS\-Federation доступен через свойство <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A><xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs> передаваемого в обработчике событий.  Можно также изменить запрос перед отправкой это, в эмитенту.  
  
-   WS\-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn> когда COOKIE\-файл успешно записан, а пользователь подписан недопустимо.  
  
-   WS\-FAM создает событие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut> один раз для каждого сеанса, как закрыть сеанс вниз для каждого пользователя.  Это событие не вызывается при закрытии сеанса вниз на клиентском, \(например, путем удаления COOKIE\-файла сеанса\).  В этой среде единого входа, IP\-STS может запрашивать у каждой категории еще не присвоена выходила, слишком.  Это также вызывает это событие, с <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> устанавливается в значение `true`.  
  
> [!NOTE]
>  Не следует использовать свойство <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> во время любого события, вызванного объектом <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> или <xref:System.IdentityModel.Services.SessionAuthenticationModule>.  Это происходит потому, что <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> установлено после процесса проверки подлинности, а события вызываются в процессе проверки подлинности.  
  
### Конфигурация федеративной проверки подлинности  
 WS\-FAM и SAM настраивается с помощью элемента [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).  Дочерний элемент [\<wsFederation\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) настраивает значения по умолчанию для свойств WS\-FAM; например свойства <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A> и свойство <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A>. \(Эти значения можно изменить на " на основе запроса, обеспечивая обработчиков для некоторых событий WS\-FAM; например, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>\). Обработчик COOKIE\-файл, который используется элементом управления лицензиями настраивается с помощью дочернего элемента [\<cookieHandler\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md).  WIF предоставляет обработчик COOKIE\-файл равен реализован в классе <xref:System.IdentityModel.Services.ChunkedCookieHandler>, может иметь его размер блока, с помощью элемента [\<chunkedCookieHandler\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md).  Справочники по элементам `<federationConfiguration>`<xref:System.IdentityModel.Configuration.IdentityConfiguration>, которая предоставляет конфигурацию для других компонентов WIF используется в приложении, например <xref:System.Security.Claims.ClaimsAuthenticationManager> и <xref:System.Security.Claims.ClaimsAuthorizationManager>.  Конфигурация идентификатора может ссылаться из явно определяя именованный элемент [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) в атрибуте `identityConfigurationName` элемента `<federationConfiguration>`.  Если конфигурация идентификатора не используется явно, то конфигурация идентификатора по умолчанию будет использоваться.  
  
 Следующий код XML показывает конфигурацию приложения \(RP\) проверяющей стороны ASP.NET.  Разделы конфигурации <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> и <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> добавляются в элемент `<configSections>`.  SAM и WS\-FAM добавляются в HTTP\-модуля в элементе `<system.webServer>`\/`<modules>`.  Наконец WIF компоненты настраиваются в `<system.identityModel>`\/`<identityConfiguration>` и `<system.identityModel.services>`\/элементами `<federationConfiguration>`.  Эта конфигурация указывает chunked обработчик COOKIE\-файл, как это обработчик COOKIE\-файл по умолчанию и не является типом обработчика COOKIE\-файла, определенного в элементе `<cookieHandler>`.  
  
> [!WARNING]
>  В следующем примере, а атрибут `requireHttps` элемента `<wsFederation>` и атрибут `requireSsl` элемента `<cookieHandler>``false`.  Это представляет потенциальную угрозу безопасности.  В рабочей среде, оба этих значения должны быть предоставлена `true`.  
  
```  
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
  
## См. также  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)