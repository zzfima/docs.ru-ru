---
title: Рекомендации по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5
ms.date: 03/30/2017
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
author: BrucePerlerMS
ms.openlocfilehash: ec66803edc21f186fa9a8c5bcb91b5181789893d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086870"
---
# <a name="guidelines-for-migrating-an-application-built-using-wif-35-to-wif-45"></a>Рекомендации по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5
## <a name="applies-to"></a>Применение  
  
-   Microsoft® Windows® Identity Foundation (WIF) 3.5 и 4.5.  
  
## <a name="overview"></a>Обзор  
 Платформа Windows Identity Foundation (WIF) была изначально выпущена одновременно с пакетом обновления 1 (SP1) для .NET 3.5. При первичном выпуске эта платформа получила версию WIF 3.5. Платформа была выпущена в виде отдельной среды выполнения и пакета SDK. Таким образом, на каждом компьютере, где выполняются приложения с поддержкой WIF, должна была быть установлена среда выполнения WIF. Кроме того, разработчикам было необходимо скачать и установить пакет SDK WIF для получения шаблонов и средств Visual Studio, необходимых для разработки приложений с поддержкой WIF. Начиная с .NET 4.5, платформа WIF полностью интегрирована в .NET Framework. Отдельная среда выполнения более не нужна, а средства WIF можно установить в Visual Studio 2012, используя диспетчер расширений Visual Studio. Эта версия WIF называется WIF 4.5.  
  
 Интеграция платформы WIF с .NET была связана с рядом изменений в поверхности API WIF. Версия WIF 4.5 включает новые пространства имен, определенные изменения в элементах конфигурации, а также новые средства для Visual Studio. В этом разделе приводятся рекомендации по переносу приложений, построенных с использованием версии WIF 3.5, на платформу WIF 4.5. В некоторых сценариях требуется выполнять прежние версии приложений, построенных с использованием WIF 3.5, на компьютерах под управлением ОС Windows 8 или Windows Server 2012. В этом разделе также приводятся рекомендации по обеспечению поддержки WIF 3.5 в этих операционных системах.  
  
## <a name="changes-required-for-wif-45"></a>Необходимые изменения для версии WIF 4.5  
 В этом разделе описаны изменения, которые необходимы для переноса приложения WIF 3.5 на платформу WIF 4.5.  
  
### <a name="assembly-and-namespace-changes"></a>Изменения сборок и пространств имен  
 В версии WIF 3.5 все классы платформы WIF находились в сборке `Microsoft.IdentityModel` (microsoft.identitymicrosoft.identitymodel.dll). В WIF 4.5 классы WIF размещаются в следующих сборках: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) и `System.ServiceModel` (System.ServiceModel.dll).  
  
 Классы WIF 3.5 ранее содержались в одном из пространств имен `Microsoft.IdentityModel`, например `Microsoft.IdentityModel`, `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Web` и т. д. В WIF 4.5 классы WIF размещаются в пространствах имен [System.IdentityModel](https://go.microsoft.com/fwlink/?LinkId=272004): <xref:System.Security.Claims?displayProperty=nameWithType> и <xref:System.ServiceModel.Security?displayProperty=nameWithType>. Помимо этих структурных изменений, в версии WIF 4.5 были исключены некоторые классы WIF 3.5.  
  
 В следующей таблице описываются основные пространства имен платформы WIF 4.5 и виды содержащихся в них классов. Дополнительные сведения о сопоставлении пространств имен между версиями WIF 3.5 и WIF 4.5, а также об исключенных из WIF 4.5 пространствах имен и классах см. в разделе [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
|Пространство имен WIF 4.5|Описание|  
|-----------------------|-----------------|  
|<xref:System.IdentityModel?displayProperty=nameWithType>|Содержит классы, представляющие преобразования файлов cookie, службы маркеров безопасности, а также средства чтения словарей XML. Содержит классы из следующих пространств имен WIF 3.5: `Microsoft.IdentityModel`, `Microsoft.IdentityModel.SecurityTokenService` и `Microsoft.IdentityModel.Threading`.|  
|<xref:System.Security.Claims?displayProperty=nameWithType>|Содержит классы, представляющие утверждения, удостоверения на основе утверждений, субъекты на основе утверждений, а также другие артефакты модели на основе утверждений. Содержит классы из пространства имен `Microsoft.IdentityModel.Claims`.|  
|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|Содержит классы, представляющие маркеры безопасности, обработчики маркеров безопасности, а также другие артефакты маркеров безопасности. Содержит классы из следующих пространств имен WIF 3.5: `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Tokens.Saml11` и `Microsoft.IdentityModel.Tokens.Saml2`.|  
|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|Содержит классы, используемые в пассивных сценариях (WS-Federation). Содержит классы из пространства имен `Microsoft.IdentityModel.Web`.|  
|<xref:System.ServiceModel.Security?displayProperty=nameWithType>|В это пространство имен теперь входят классы, представляющие контракты, каналы, узлы службы и другие артефакты WCF, которые используются в активных сценариях (WS-Trust). На платформе WIF 3.5 эти классы находились в пространстве имен `Microsoft.IdentityModel.Protocols.WSTrust`.|  
  
> [!IMPORTANT]
>  Следующие пространства имен `System.IdentityModel` содержат классы, которые реализуют модель удостоверений WCF на основе утверждений: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> и <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. Модель удостоверений WCF на базе утверждений заменяется WIF. При создании решений на основе WIF не следует использовать классы из этих трех пространств имен.  
  
### <a name="changes-due-to-net-integration"></a>Изменения в связи с интеграцией с .NET  
 Теперь платформа WIF интегрирована с .NET Framework. С этого момента большинство классов удостоверений и субъектов .NET являются производными от <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> и <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>. В связи с этим в версии WIF 4.5 были произведены следующие изменения:  
  
-   Классы WIF, представляющие утверждения, удостоверения и субъекты, теперь находятся в пространстве имен <xref:System.Security.Claims?displayProperty=nameWithType>.  
  
    > [!IMPORTANT]
    >  Пространство имен <xref:System.IdentityModel.Claims?displayProperty=nameWithType> содержит классы, представляющие артефакты в модели удостоверений WCF на основе утверждений. В большинстве случаев имена этих классов совпадают с именами классов WIF, например `Claims`. Не используйте эти классы при построении решений на основе WIF.  
  
-   Классы удостоверений и субъектов .NET теперь являются производными непосредственно от классов <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> и <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>, которые представляют удостоверения и субъекты на основе утверждений. По этой причине интерфейсы `IClaimsIdentity` и `IClaimsPrincipal` из версии WIF 3.5 больше не нужны и недоступны на платформе WIF 4.5.  
  
-   Поскольку классы удостоверений и субъектов .NET, такие как <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> и <xref:System.Security.Principal.WindowsPrincipal?displayProperty=nameWithType>, теперь являются производными от <xref:System.Security.Claims.ClaimsIdentity> и <xref:System.Security.Claims.ClaimsPrincipal>, они реализуют встроенные функции работы с утверждениями. По этой причине больше не нужны классы для работы с удостоверениями и субъектами на основе утверждений из версии WIF 3.5 (`WindowsClaimsIdentity` и `WindowsClaimsPrincipal`), которые исключены из WIF 4.5.  
  
### <a name="other-changes-to-wif-functionality"></a>Другие изменения в функциях WIF  
 Помимо изменений, связанных с пространствами имен и интеграцией с .NET, в версии WIF 4.5 реализованы следующие изменения функций WIF.  
  
-   Исключен класс `Microsoft.IdentityModel.ExceptionMapper`, в котором были представлены функции для сопоставления исключений с конкретными ошибками SOAP.  
  
-   Поверхность исключения значительно сокращена.  
  
-   Исключено большинство классов, в которых определялись специальные константы протокола или WS-*, например класс `Microsoft.IdentityModel.WSAddressing10Constants`, где были определены константы для WS-Addressing 1.0.  
  
-   Исключены служба утверждений для службы маркеров Windows (c2wts) и связанные с ней классы пространства имен `Microsoft.IdentityModel.WindowsTokenService`.  
  
### <a name="wif-configuration-changes"></a>Изменения конфигурации WIF  
 Основные изменения в файле конфигурации связаны с обновлениями пространств имен в WIF 4.5. Например, рассмотрим следующую запись WIF 3.5 в разделе `<httpModules>`, которая добавляет в приложение диспетчер проверки подлинности WS-Federation:  
  
```xml  
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />  
```  
  
 В версии WIF 4.5 эта запись обновлена и включает новые версии пространств имен и сборки:  
  
```xml  
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>  
```  
  
 В следующем списке перечислены основные изменения в файле конфигурации для WIF 4.5.  
  
-   Раздел `<microsoft.identityModel>` переименован в [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md).  
  
-   Элемент `<service>` переименован в [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).  
  
-   Добавлен новый раздел [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md), который определяет поведение в пассивных сценариях (WS-Federation).  
  
-   Элемент [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) и его дочерние элементы перенесены из элемента `<service>` (WIF 3.5) в новый элемент `<system.identityModel.services>`.  
  
-   Некоторые элементы, которые могли задаваться на уровне службы непосредственно в элементе `<service>` (WIF 3.5), были ограничены и теперь задаются в элементе [\<securityTokenHandlerConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md). (Для обеспечения обратной совместимости они по-прежнему могут задаваться в элементе [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) на платформе WIF 4.5.)  
  
 Полный список элементов конфигурации WIF 4.5 см. в разделе [Схема конфигурации WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md).  
  
### <a name="visual-studio-tooling-changes"></a>Изменения в средствах Visual Studio  
 В пакете SDK WIF 3.5 была представлена автономная служебная программа федерации FedUtil.exe (FedUtil), с помощью которой можно было передавать функции управления удостоверениями в приложениях с поддержкой WIF службе маркеров безопасности (STS). Это средство добавляло в файл конфигурации приложения параметры WIF, которые позволяли получать маркеры безопасности от одной или нескольких служб маркеров безопасности, и было представлено в Visual Studio кнопкой **Добавить ссылку на службу STS**. Служебная программа FedUtil не входит в состав WIF 4.5. Вместо нее платформа WIF 4.5 поддерживает новое расширение Visual Studio с именем Identity and Access Tool для Visual Studio 2012, которое позволяет добавлять в файл конфигурации приложения параметры WIF, необходимые для передачи функций управления удостоверениями службе маркеров безопасности. Средство Identity and Access Tool также реализует локальную службу маркеров безопасности, которую можно использовать для тестирования приложений с поддержкой WIF. Во многих случаях этот компонент избавляет от необходимости создавать настраиваемые службы маркеров безопасности, которые зачастую требовались в версии WIF 3.5 для тестирования разрабатываемых решений. По этой причине в Visual Studio 2012 больше не поддерживаются шаблоны службы маркеров безопасности, однако в версии WIF 4.5 по-прежнему доступны классы, обеспечивающие разработку служб маркеров безопасности.  
  
 Средство Identity and Access Tool можно установить с помощью диспетчера расширений и обновлений Visual Studio, а также скачать со следующей страницы в коллекции исходных кодов: [Средство Identity and Access Tool для Visual Studio 2012 в коллекции исходных кодов](https://go.microsoft.com/fwlink/?LinkID=245849). Ниже описываются изменения в средствах Visual Studio:  
  
-   Исключена функция "Добавить ссылку на службу STS". Вместо нее используется средство Identity and Access Tool.  
  
-   Исключены шаблоны служб маркеров безопасности Visual Studio STS. Для тестирования решений, разрабатываемых с поддержкой WIF, можно использовать локальную службу маркеров безопасности, которая доступна в средстве Identity and Access Tool. Можно изменить конфигурацию локальной службы маркеров безопасности для настройки обрабатываемых с ее помощью утверждений.  
  
-   В версии WIF 4.5 недоступна автономная служебная программа федерации (FedUtil). С помощью средства Identity and Access Tool можно изменить файлы конфигурации для передачи функций управления удостоверениями службе маркеров безопасности.  
  
 Дополнительные сведения см. в разделе [Средство Identity and Access Tool для Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
<a name="BKMK_ToolingChanges"></a>   
### <a name="passive-ws-federation-scenarios"></a>Пассивные сценарии (WS-Federation):  
  
-   Классы, поддерживающие пассивные сценарии, перенесены в пространство имен <xref:System.IdentityModel.Services?displayProperty=nameWithType>. На платформе WIF 3.5 эти классы находились в пространстве имен `Microsoft.IdentityModel.Web`.  
  
-   Классы из пространства имен `Microsoft.IdentityModel.Web.Configuration` перенесены в <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>. Эти классы представляют объекты, относящиеся к конфигурации в пассивных сценариях.  
  
-   `FederatedPasssiveSignInControl` больше не поддерживается. Из версии WIF 4.5 исключены все классы из пространства имен `Microsoft.IdentityModel.Web.Controls`.  
  
-   Функции выхода из модуля проверки подлинности WS-Federation (<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>) отличаются от представленных в WIF 3.5. Дополнительные сведения о функциях выхода на платформе WIF 4.5 см. в разделе, посвященном классу <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
### <a name="active-wcfws-trust-scenarios"></a>Активные сценарии (WCF/WS-Trust):  
  
-   В версии WIF 4.5 пространство имен `Microsoft.IdentityModel.Protocols.WSTrust` разбито на два пространства имен. Классы, представляющие связанные с протоколом WS-Trust артефакты, теперь находятся в <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>. К ним относятся такие классы, как <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>. Классы, которые представляют контракты служб, каналы, узлы служб и другие артефакты, связанные с применением WS-Trust в приложениях WCF, перенесены в <xref:System.ServiceModel.Security?displayProperty=nameWithType> (например, интерфейс <xref:System.ServiceModel.Security.IWSTrust13AsyncContract>).  
  
-   Значительно упрощена настройка приложения WCF для работы с платформой WIF. Ранее в качестве расширения поведения добавлялось `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement`, после чего эта функция использовалась для добавления возможностей WIF в службу с помощью элемента `<federatedServiceHostConfiguration>`. Версия WIF 4.5 обеспечивает более тесную интеграцию с WCF. Теперь функции WIF для службы WCF можно реализовать с помощью атрибута `useIdentityConfiguration` элемента `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`, как показано в следующем коде XML:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
-   В версии WIF 4.5 сертификат службы, используемый активной службой (WCF), необходимо указывать на узле службы. В файле конфигурации это можно сделать с помощью элемента `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`/`<serviceCertificate>`, как показано в предыдущем примере. В версии WIF 3.5 сертификат службы можно было указать с помощью дочернего элемента `<serviceCertificate>` в элементе WIF `<service>`. В версии WIF 4.5 эта функция отсутствует. Вместо нее элемент `<serviceCertificate>` следует задавать в элементе `<serviceCredentials>`.  
  
-   Классы, используемые для добавления возможностей WIF 3.5 в WCF, больше не существуют. К ним относятся следующие классы в пространстве имен `Microsoft.IdentityModel.Tokens`: `FederatedSecurityTokenManager`, `FederatedServiceCredentials` и `IdentityModelServiceAuthorizationManager`, а также класс `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement`.  
  
## <a name="enabling-wif-35-in-windows-8"></a>Поддержка WIF 3.5 в ОС Windows 8  
 Поскольку платформа WIF 4.5 входит в состав .NET 4.5, она автоматически поддерживается на компьютерах под управлением ОС Windows 8 и Windows Server 2012. Поэтому приложения, построенные с использованием WIF 4.5, по умолчанию будут выполняться в ОС Windows 8 или Windows Server 2012. В некоторых случаях требуется запускать приложения, созданные с помощью WIF 3.5, на компьютерах под управлением ОС Windows 8 или Windows Server 2012. В таких ситуациях на целевом компьютере необходимо включить поддержку WIF 3.5. На компьютере под управлением Windows 8 это можно сделать с помощью системы обслуживания образов развертывания и управления ими (DISM). На компьютере под управлением Windows Server 2012 для этих целей можно использовать средство DISM или командлет `Add-WindowsFeature` в Windows PowerShell. В обоих случаях соответствующие команды могут вызываться из командной строки или из среды Windows PowerShell.  
  
 Ниже показано, как использовать средство DISM из командной строки или среды Windows PowerShell. По умолчанию модуль DISM PowerShell входит в состав Windows 8 и Windows Server 2012. Импортировать его не требуется. Дополнительные сведения об использовании DISM в Windows PowerShell см. в разделе [Использование средства DISM в Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=254419).  
  
 Включение поддержки WIF 3.5 с помощью DISM:  
  
```  
dism /online /enable-feature:windows-identity-foundation  
```  
  
 Отключение поддержки WIF 3.5 с помощью DISM:  
  
```  
dism /online /disable-feature:windows-identity-foundation  
```  
  
 Проверка включаемых и выключаемых с помощью средства DISM функций:  
  
```  
dism /online /get-features  
```  
  
 Кроме того, на компьютерах под управлением Windows Server 2012 поддержку WIF 3.5 можно включить с помощью командлета `Add-WindowsFeature` в Windows PowerShell. Для этого введите следующую команду в командной строке:  
  
```  
powershell "add-windowsfeature windows-identity-foundation"  
```  
  
 В среде Windows PowerShell можно ввести следующую команду напрямую:  
  
```  
add-windowsfeature windows-identity-foundation  
```  
  
> [!NOTE]
>  Поскольку многие классы в WIF 3.5 и WIF 4.5 имеют одинаковые имена, для проведения различий между ними при совместном использовании версий WIF 3.5 и WIF 4.5 необходимо использовать полные имена классов или псевдонимы пространств имен.  
  
## <a name="see-also"></a>См. также  
 [Схема конфигурации WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)  
 [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)  
 [Новые возможности Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)  
 [Средство Identity and Access Tool для Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)
