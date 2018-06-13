---
title: Новые возможности Windows Identity Foundation 4.5
ms.date: 03/30/2017
ms.assetid: 3b381f04-593b-471f-bd33-0362be1aade5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0a5bc7d53405966bcb86750780473c4060d7ced3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400423"
---
# <a name="what39s-new-in-windows-identity-foundation-45"></a>Новые возможности Windows Identity Foundation 4.5
Первая версия Windows Identity Foundation (WIF) поставлялась в виде отдельного загружаемого файла и называлась WIF 3.5, поскольку она вышла одновременно с .NET 3.5 с пактом обновления 1 (SP1). Начиная с версии .NET 4.5 WIF является частью .NET framework. Прямая доступность классов WIF на этой платформе обеспечивает гораздо более глубокую интеграцию удостоверения на базе утверждений с платформой .NET, благодаря которой использовать утверждения становится проще. Приложения, написанные для WIF 3.5, должны быть изменены для использования новой модели. Дополнительные сведения см. в разделе [Рекомендации по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
 Ниже описаны некоторые особенности основных изменений.  
  
## <a name="wif-is-now-part-of-the-net-framework"></a>Теперь WIF является частью .NET Framework  
 Классы WIF теперь распределены между несколькими сборками, основными из которых являются `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services` и `System.ServiceModel`. Кроме того, классы WIF распределены между несколькими пространствами имен: <xref:System.Security.Claims?displayProperty=nameWithType>, несколькими пространствами имен [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) и <xref:System.ServiceModel.Security?displayProperty=nameWithType>. Пространство имен <xref:System.Security.Claims?displayProperty=nameWithType> содержит новые классы <xref:System.Security.Claims.ClaimsPrincipal> и <xref:System.Security.Claims.ClaimsIdentity> (см. ниже). Все субъекты в .NET теперь являются производными от <xref:System.Security.Claims.ClaimsPrincipal>. Дополнительные сведения о пространствах имен WIF и типах классов, которые они содержат, см. в разделе [Справочник по API WIF](../../../docs/framework/security/wif-api-reference.md). Сведения о сопоставлении пространств имен между WIF 3.5 и WIF 4.5 см. в разделе [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
## <a name="new-claims-model-and-principal-object"></a>Новая модель утверждений и объект-участник  
 Утверждения лежат в основе .NET Framework 4.5. Базовые классы утверждений (<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes> и <xref:System.Security.Claims.ClaimValueTypes>) находятся непосредственно в `mscorlib` в пространстве имен <xref:System.Security.Claims?displayProperty=nameWithType>. Больше нет необходимости использовать интерфейсы для подключения утверждений к системе удостоверений .NET: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal> и <xref:System.Web.Security.RolePrincipal> теперь являются производными от класса <xref:System.Security.Claims.ClaimsPrincipal>; а <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity> и <xref:System.Web.Security.FormsIdentity> теперь являются производными от <xref:System.Security.Claims.ClaimsIdentity>. Иными словами, каждый класс субъекта теперь обслуживает утверждения. Поэтому классы и интерфейсы интеграции WIF 3.5 (`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`) были удалены. Кроме того, теперь класс <xref:System.Security.Claims.ClaimsIdentity> предоставляет методы, которые упрощают запрос коллекции утверждений удостоверения.  
  
## <a name="changes-to-the-wif-45-visual-studio-experience"></a>Изменения Visual Studio, связанные с WIF 4.5  
  
-   Функция Visual Studio **Добавить ссылку STS…** (программа командной строки FedUtil) была исключена. Вместо нее можно использовать новое расширение **Средство Identity and Access Tool для Visual Studio 2012**. Оно позволяет использовать существующую службу STS или тестировать решение с помощью локальной службы STS. После установки расширения можно щелкнуть проект правой кнопкой мыши и найти в контекстом меню пункт **Удостоверения и доступ**.  
  
-   Шаблоны ASP.NET и STS больше не предоставляются, поскольку утверждения можно использовать непосредственно в существующих шаблонах проектов для ASP.NET, веб-сайтов и WCF.  
  
-   Элементы управления в пространстве имен `Microsoft.IdentityModel.Web.Controls` (`SignInControl`, `FederatedPassiveSignInControl` и `FederatedPassiveSignInStatus`) не переносятся в WIF 4.5.  
  
## <a name="changes-to-the-wif-45-api"></a>Изменения в API WIF 4.5  
  
-   Как правило, классы, связанные с утверждениями, принадлежат к пространству имен <xref:System.Security.Claims?displayProperty=nameWithType>, классы, связанные с WCF, — контракты служб, каналы, фабрики каналов и узлы служб, которые используются для сценариев WS-Trust — принадлежат к пространству имен <xref:System.ServiceModel.Security?displayProperty=nameWithType>, а все остальные классы WIF находятся в различных пространствах имен [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004). К ним относятся, например, классы, представляющие артефакты WS-* и SAML, обработчики токенов и связанные классы, а также классы, используемые в сценариях WS-Federation. Дополнительные сведения см. в разделах [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) и [Справочник по API WIF](../../../docs/framework/security/wif-api-reference.md).  
  
-   Для использования в файлах cookie сеансов в сценариях с веб-фермами был включен ключ компьютера. Дополнительные сведения см. в разделе [WIF и веб-фермы](../../../docs/framework/security/wif-and-web-farms.md).  
  
-   Декларативная настройка WIF теперь выполняется в элементах [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) и [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Дополнительные сведения о настройке WIF см. в разделе [Справочник по конфигурации WIF](../../../docs/framework/security/wif-configuration-reference.md).  
  
## <a name="other-notable-net-changes-or-features-that-are-caused-by-the-integration-of-wif-into-net"></a>Другие важные изменения .NET и возможности, связанные с интеграцией WIF с .NET  
  
-   Возможность выполнения авторизации на основе утверждений теперь является частью .NET Framework. Можно настроить объект <xref:System.Security.Claims.ClaimsAuthorizationManager>, а затем использовать классы <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> и <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> для осуществления императивной и декларативной проверки доступа к коду. Авторизация на основе утверждений обеспечивает большую гибкость и детализацию по сравнению с обычной проверкой доступа на основе ролей. Кроме того, она позволяет лучше отделить политику авторизации от бизнес-логики, так как в бизнес-логике можно использовать проверку доступа на базе конкретного утверждения или набора утверждений, а политику авторизации для этих утверждений можно настроить декларативно в элементе [\<claimsAuthorizationManager>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md).  
  
## <a name="wcf-changes-as-a-result-of-wif-integration"></a>Изменения WCF, связанные с интеграцией WIF:  
  
-   Модель удостоверений WCF на базе утверждений заменяется WIF. Это означает, что от классов <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> и пространства имен <xref:System.IdentityModel.Selectors?displayProperty=nameWithType> следует отказаться в пользу использования классов WIF.  
  
-   WIF теперь включается в службе WCF с помощью атрибута `useIdentityConfiguration` в элементе `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`, как показано в следующем коде XML:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
     При использовании **средства Identity and Access Tool для Visual Studio 2012** (см. выше раздел **Изменения Visual Studio**) это средство добавляет элемент `<serviceCredentials>` с атрибутом `useIdentityConfiguration` с автоматически заданным файлом конфигурации. Кроме того, оно добавляет соответствующий элемент [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md), который содержит параметры конфигурации WIF, и добавляет привязку и другие параметры, необходимые для передачи проверки подлинности соответствующей службе STS.  
  
## <a name="see-also"></a>См. также  
 [Руководства по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)  
 [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)  
 [Справочник по API WIF](../../../docs/framework/security/wif-api-reference.md)  
 [Справочник по конфигурации WIF](../../../docs/framework/security/wif-configuration-reference.md)
