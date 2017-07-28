---
title: "Рекомендации по миграции приложения, созданного с использованием WIF&#160;3.5, в WIF&#160;4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
caps.latest.revision: 12
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# Рекомендации по миграции приложения, созданного с использованием WIF&#160;3.5, в WIF&#160;4.5
## Применение  
  
-   Основой \(WIF\) 3.5 и 4.5 идентификатора Microsoft® Windows®.  
  
## Обзор  
 Основой \(WIF\) идентификатора Windows изначально выпускается в сроки .NET 3.5 SP1.  Эта версия WIF WIF — 3.5.  Она была освобождена в виде отдельного выполнения и SDK, что приводило к тому, что каждый компьютер, на котором запущено приложение, использующее WIF\- иметь выполнения WIF, но и разработчикам необходимо загрузить и установить WIF SDK для доступа к средствам и шаблоны Visual Studio, для которых WIF\- разработку приложений.  Начиная с .NET 4.5, WIF был полностью интегрирован в .NET Framework.  Отдельные выполнения больше не требуется и средствам WIF установлены в Visual Studio 2012 с помощью диспетчера расширений Visual Studio.  Эта версия WIF WIF — 4.5.  
  
 Интеграция WIF в .NET потребовала несколько изменений в рабочей области WIF API.  WIF 4.5 включает новые пространства имен, некоторые изменения элементов конфигурации и новый средствам для Visual Studio.  Этот раздел содержит рекомендации, которые можно использовать при необходимости переноса приложения, построенные с помощью WIF WIF 3.5 на 4.5. Возможны сценарии, в которых требуется выполнить приложения прежних версий, построенные с помощью WIF 3.5 на компьютерах, работающих под управлением Windows 8 или Windows Server 2012.  В этом разделе также приводятся указания о том, как включить WIF 3.5 для этих операционных систем.  
  
## Изменения, необходимые для WIF 4.5  
 В этом разделе описываются изменения, необходимые для миграции приложения WIF WIF 3.5 на 4.5.  
  
### Изменения сборки и пространства имен  
 В WIF 3.5 все классы WIF содержались в сборке `Microsoft.IdentityModel` \(microsoft.identitymicrosoft.identitymodel.dll\).  В WIF 4.5, классы WIF были разделены на следующие сборки: `mscorlib` \(mscorlib.dll\), `System.IdentityModel` \(System.IdentityModel.dll\), `System.IdentityModel.Services` \(System.IdentityModel.Services.dll\) и `System.ServiceModel` \(System.ServiceModel.dll\).  
  
 Все классы WIF 3.5 содержались в одном из пространств имен `Microsoft.IdentityModel`; например, `Microsoft.IdentityModel`, `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Web` и т д  В WIF 4.5, классы WIF теперь распространены на пространства имен [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004), пространство имен <xref:System.Security.Claims?displayProperty=fullName> и пространство имен <xref:System.ServiceModel.Security?displayProperty=fullName>.  В дополнение к этой реорганизации, классы определенного WIF 3.5 были удалены в WIF 4.5.  
  
 В следующей таблице показаны некоторые из наиболее важных пространств имен WIF 4.5 и типа классов в них.  Дополнительные сведения о сопоставлении пространств имен WIF между 3.5 и 4.5 и WIF по пространствам имен и классов, которые были удалены в WIF 4.5 см. в разделе [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
|Пространство имен WIF 4.5|Описание|  
|-------------------------------|--------------|  
|<xref:System.IdentityModel?displayProperty=fullName>|Содержит классы, представляющие COOKIE\-файл преобразования, службы маркеров безопасности и специализированные читатели словаря XML.  Содержит классы из следующих пространств имен WIF 3.5: `Microsoft.IdentityModel`, `Microsoft.IdentityModel.SecurityTokenService` и `Microsoft.IdentityModel.Threading`.|  
|<xref:System.Security.Claims?displayProperty=fullName>|Содержит классы, представляющие заявки, идентификатор, основанного на утверждениях, субъекты, заявок и другие артефакты модели является, основанного на утверждениях.  Содержит классы из пространства имен `Microsoft.IdentityModel.Claims`.|  
|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|Содержит классы, представляющие маркеры безопасности, обработчики маркера безопасности и другие артефакты маркера безопасности.  Содержит классы из следующих пространств имен WIF 3.5: `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Tokens.Saml11` и `Microsoft.IdentityModel.Tokens.Saml2`.|  
|<xref:System.IdentityModel.Services?displayProperty=fullName>|Содержит классы, используемые в сценариях пассивных \(WS\-Federation\).  Содержит классы из пространства имен `Microsoft.IdentityModel.Web`.|  
|<xref:System.ServiceModel.Security?displayProperty=fullName>|Классы, представляющие контракты WCF, каналы, узлы служб и других объектов, используемых в сценариях активных \(WS\- доверия\) теперь в этом пространстве имен.  В WIF 3.5, эти классы находились в пространстве имен `Microsoft.IdentityModel.Protocols.WSTrust`.|  
  
> [!IMPORTANT]
>  Следующие пространства имен `System.IdentityModel` содержат классы, которые реализуют модель удостоверение, основанного на утверждениях WCF: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> и <xref:System.IdentityModel.Selectors?displayProperty=fullName>.  Идентификатор модели, основанного на утверждениях WCF заменены WIF.  Не следует использовать классы в этих 3 пространств имен при построении решения на основе WIF.  
  
### Изменения медленным из\-за дополнительного интеграции .NET  
 WIF теперь интегрирован в .NET Framework.  Большинство классов идентификатора и субъекта .NET теперь являются производными от <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> и <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>.  Результаты в следующих изменений в WIF 4.5:  
  
-   Классы, представляющие WIF заявки, идентификаторы и субъекты теперь существует в пространстве имен <xref:System.Security.Claims?displayProperty=fullName>.  
  
    > [!IMPORTANT]
    >  Пространство имен <xref:System.IdentityModel.Claims?displayProperty=fullName> содержит классы, представляющие артефакты в модели является, основанного на утверждениях WCF.  Многие из этих классов, имеют имена, так же как классы WIF; например, `Claims`.  Не используйте эти классы построение решений на основе WIF.  
  
-   классы идентификатора и субъекта .NET теперь полученных непосредственно из <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> и <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>, которые представляют идентификаторы, основанного на утверждениях и субъекты.  По этой причине интерфейсы `IClaimsIdentity` WIF 3.5 и `IClaimsPrincipal` больше не требуются и недоступны в WIF 4.5.  
  
-   Классы идентификатора и субъекта Because.NET как <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName> и <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> теперь являются производными от <xref:System.Security.Claims.ClaimsIdentity> и <xref:System.Security.Claims.ClaimsPrincipal>, имеют встроенные функции заявок.  По этой причине классы идентификатора заявк\- параметрами и субъекта, например `WindowsClaimsIdentity` и `WindowsClaimsPrincipal`, которые присутствовали в WIF 3.5 больше не требуется и не существует в WIF 4.5.  
  
### Другие изменения в функции WIF  
 Помимо изменения пространства имен и изменениями должным в результате интеграции с .NET, следующие общие изменения функции WIF происходят в WIF 4.5.  
  
-   Класс `Microsoft.IdentityModel.ExceptionMapper`, который предоставляет функциональность, необходимо сопоставить позволила исключения в определенных ошибка SOAP, удаляется.  
  
-   Поверхность исключения была существенно уменьшается.  
  
-   Многие из классов, которые определяли протокол или константы WS\-\*, удалены; например, класс `Microsoft.IdentityModel.WSAddressing10Constants`, который определен как константы, связанные с WS\- слишком 1.0.  
  
-   Удалены, в службу Windows c2wts токена \(\) и его связанным классы в пространстве имен `Microsoft.IdentityModel.WindowsTokenService`.  
  
### Изменения в конфигурации WIF  
 Многие изменения в файле конфигурации, вызванные обновлениями пространства имен в WIF 4.5. Например, рассмотрим, что следующая запись WIF 3.5 в разделе `<httpModules>` добавляет диспетчер проверки подлинности WS\-Federation приложению.  
  
```  
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />  
```  
  
 Эта запись была обновлена в WIF 4.5 для включения новые пространства имен и версию сборки.  
  
```  
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>  
```  
  
 В следующем списке перечислены значительные изменения в файл конфигурации для WIF 4.5.  
  
-   Раздел `<microsoft.identityModel>` теперь раздел [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md).  
  
-   Элемент `<service>` теперь элемент [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).  
  
-   Новый раздел, [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) был добавлен, чтобы определить параметры это расширение функциональности элемента управления в сценариях пассивных \(WS\-Federation\).  
  
-   Элемент [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) и его дочерние элементы были перемещены из элемента `<service>` в WIF 3.5 к новому элементу `<system.identityModel.services>`.  
  
-   Несколько элементов, которые могли быть заданы на уровне служба\- непосредственно под элементом `<service>` в WIF 3.5 ограничивались определить в элементе [\<securityTokenHandlerConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md). \(Они все еще могут быть указаны в элементе [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) в WIF 4.5 для обеспечения обратной совместимости\).  
  
 Полный список элементов конфигурации WIF 4.5 см. в разделе [Схема конфигурации WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md).  
  
### Изменения средствам Visual Studio  
 WIF 3.5 SDK доступен самостоятельную программу федерации, FedUtil.exe \(FedUtil\), которое можно использовать, чтобы outsource элемент управления удостоверениями в приложениях WIF\- включается в службу маркеров безопасности \(STS\).  Это средство добавляет WIF параметры в файл конфигурации приложения для включения приложения к маркеры безопасности из одной или нескольких служб маркеров безопасности и было предоставлено в Visual Studio с помощью кнопки **Добавить STS\-ссылку**.  FedUtil не поставляется с WIF 4.5. Вместо этого WIF 4.5 поддерживает новое расширение Visual Studio средство с идентификатором и доступом для Visual Studio 2012, можно изменить файл конфигурации приложения с WIF параметров, необходимых outsource элемент управления удостоверениями в службу маркеров безопасности.  Средство идентификатора и доступа к также реализует службу маркеров безопасности с Локальной службой маркеров безопасности, который можно использовать для выполнения WIF\- разрешенные приложения.  Во многих случаях эта функция устраняет необходимость создавать пользовательские службы маркеров безопасности, которые часто требуются в WIF 3.5 для выполнения решения в разработке.  По этой причине шаблоны службы маркеров безопасности больше не поддерживаются в Visual Studio 2012; однако классы, поддерживающие разработку служб маркеров безопасности по\-прежнему доступны в WIF 4.5.  
  
 Можно будет задавать идентификатор и получить средство из расширения и обновляет диспетчер в Visual Studio или его можно загрузить со страницы сайта Code Gallery. [Средство идентификатора и доступа для Visual Studio 2012 на Code Gallery](http://go.microsoft.com/fwlink/?LinkID=245849).  Изменения средствам Visual Studio приведены в следующем списке:  
  
-   Функция ссылки на службу маркеров безопасности службы добавление удаляется.  Замена средство идентификатора и доступа.  
  
-   Шаблоны службы маркеров безопасности Visual Studio удаляются.  Можно использовать локальную службу маркеров безопасности, доступные через средство идентификатора и доступа к решениям идентификатора теста, разрабатывается с WIF.  Локальная конфигурация службы маркеров безопасности можно изменить, чтобы настраивать заявки, она служит.  
  
-   Изолированная программа федерации \(FedUtil\) недоступна в WIF 4.5. Можно использовать средство идентификатора доступа и изменять файлы конфигурации, чтобы outsource элемент управления удостоверениями в службу маркеров безопасности.  
  
 Дополнительные сведения о средстве идентификатора и доступа см. в разделе [Средство Identity and Access Tool для Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)  
  
<a name="BKMK_ToolingChanges"></a>   
### Пассивные сценарии \(WS\-Federation\).  
  
-   Классы, поддерживающие пассивные сценарии были перемещены в пространство имен <xref:System.IdentityModel.Services?displayProperty=fullName>.  В WIF 3.5 эти классы находились в пространстве имен `Microsoft.IdentityModel.Web`.  
  
-   Классы в пространстве имен `Microsoft.IdentityModel.Web.Configuration` были перемещены в <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>.  Эти классы представляют объекты, относящиеся к конфигурации в пассивных сценариях.  
  
-   `FederatedPasssiveSignInControl` больше не поддерживается. все классы в пространстве имен `Microsoft.IdentityModel.Web.Controls` удаленные из WIF 4.5.  
  
-   Модуль проверки подлинности WS\-Federation \(<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>\). функция отличается от WIF 3.5.  Дополнительные сведения о том, как работает оставлен в WIF 4.5 см. раздел класса <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
### Активных сценариев \(WCF\/WS\-Trust\).  
  
-   Пространство имен `Microsoft.IdentityModel.Protocols.WSTrust` было разделено главным образом в 2 пространства имен в WIF 4.5. Классы, представляющие артефакты, относящиеся к протоколу WS\- доверия теперь в <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>.  Это включает классы как <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>.  Классы, представляющие подряды на обслуживание, каналы, узлы служб и других объектов, участвующих в использовать WS\- доверия в приложениях WCF были перемещены в <xref:System.ServiceModel.Security?displayProperty=fullName>; например, интерфейс <xref:System.ServiceModel.Security.IWSTrust13AsyncContract>.  
  
-   Настройка приложения WCF использовать WIF значительно был упрощен.  Ранее `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` необходимо добавить в качестве расширения расширения функциональности и затем эта функция использовалась, чтобы заклинить WIF в расширение функциональности службы путем указания элемента `<federatedServiceHostConfiguration>`.  WIF 4.5 было более тесно интегрирована с WCF.  Теперь необходимо включить WIF на службу WCF с помощью атрибута `useIdentityConfiguration` на `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/элементе `<serviceCredentials>`, как в следующем коде XML:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
-   В WIF 4.5 сертификат службы, используемый службой активной \(WCF\) необходимо указать в узле службы.  В конфигурации можно сделать это с помощью `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/`<serviceCredentials>`\/элемент `<serviceCertificate>`, как показано в предыдущем примере.  В WIF 3.5 сертификат службы может быть определено с помощью дочернего элемента `<serviceCertificate>` элемента WIF `<service>`.  Эта функция не существует в WIF 4.5; укажите элемент `<serviceCertificate>` под элементом `<serviceCredentials>` вместо.  
  
-   Классы, используемые для заклинить WIF 3.5 в WCF больше не существуют.  Это включает следующие классы в пространстве имен `Microsoft.IdentityModel.Tokens` : `FederatedSecurityTokenManager`, `FederatedServiceCredentials` и `IdentityModelServiceAuthorizationManager`, так и класс `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement`.  
  
## Включение WIF 3.5 в Windows 8  
 Поскольку WIF 4.5 является частью платформы .NET 4.5, он автоматически включено на компьютерах, работающих под управлением Windows 8 и Windows Server 2012 и приложения, построенные с помощью WIF 4.5 запущены в Windows 8 или Windows Server 2012 по умолчанию.  Однако может возникнуть необходимость в выполнении приложения, созданные с помощью WIF 3.5 на компьютере под управлением Windows 8 или Windows Server 2012.  В этом случае необходимо включить WIF 3.5 на целевом компьютере.  На компьютере под управлением Windows 8, это можно выполнить с помощью средства обслуживания Система образов развертывания и управления ими \(DISM\).  На компьютере под управлением Windows Server 2012, можно использовать средство DISM или использовать командлет Windows PowerShell `Add-WindowsFeature`.  В обоих случаях соответствующие команды могут вызываться или в командной строке или внутри среды Windows PowerShell.  
  
 Следующие команды показывают, как использовать средство DISM из командной строки или внутри среды Windows PowerShell.  По умолчанию модуль DISM PowerShell включен в Windows 8 и Windows Server 2012 и не обязательно будут импортированы.  Дополнительные сведения о с помощью DISM с Windows PowerShell см. в разделе [Использование DISM в Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=254419).  
  
 Включить WIF 3.5 с помощью DISM:  
  
```  
dism /online /enable-feature:windows-identity-foundation  
```  
  
 Отключение WIF 3.5 с помощью DISM:  
  
```  
dism /online /disable-feature:windows-identity-foundation  
```  
  
 Проверять, включены или функции CLR с помощью DISM:  
  
```  
dism /online /get-features  
```  
  
 Кроме того, на компьютерах, работающих под управлением Windows Server 2012, можно включить WIF 3.5 с помощью командлета Windows PowerShell `Add-WindowsFeature`.  Поэтому задача из командной строки можно ввести следующую команду:  
  
```  
powershell "add-windowsfeature windows-identity-foundation"  
```  
  
 Внутри среды Windows PowerShell можно вводить команды непосредственно.  
  
```  
add-windowsfeature windows-identity-foundation  
```  
  
> [!NOTE]
>  Поскольку многие классов в общей папке WIF 3.5 и 4.5 WIF те же имена, при использовании и WIF 3.5 и 4.5 WIF вместе, необходимо либо использовать полным именам класса или псевдонимам пространства имен можно использовать для различения между классами в WIF WIF 3.5 и 4.5.  
  
## См. также  
 [Схема конфигурации WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)   
 [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)   
 [Новые возможности Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)   
 [Средство Identity and Access Tool для Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)