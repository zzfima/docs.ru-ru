---
title: WIF и веб-фермы
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
ms.openlocfilehash: 2f95213390187648c9f58b9b2bf2d5e3f49fb860
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135360"
---
# <a name="wif-and-web-farms"></a><span data-ttu-id="dcffc-102">WIF и веб-фермы</span><span class="sxs-lookup"><span data-stu-id="dcffc-102">WIF and Web Farms</span></span>
<span data-ttu-id="dcffc-103">Если вы используете Windows Identity Foundation (WIF) для защиты ресурсов приложения проверяющей стороны, развернутого в веб-ферме, необходимо выполнить определенные действия, чтобы платформа WIF могла обрабатывать токены от экземпляров этого приложения, работающих на разных компьютерах в ферме.</span><span class="sxs-lookup"><span data-stu-id="dcffc-103">When you use Windows Identity Foundation (WIF) to secure the resources of a relying party (RP) application that is deployed in a web farm, you must take specific steps to ensure that WIF can process tokens from instances of the RP application running on different computers in the farm.</span></span> <span data-ttu-id="dcffc-104">Обработка включает в себя проверку подписей токенов сеансов, шифрование и расшифровку токенов сеансов, их кэширование, а также обнаружение повторно используемых маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="dcffc-104">This processing includes validating session token signatures, encrypting and decrypting session tokens, caching session tokens, and detecting replayed security tokens.</span></span>  
  
 <span data-ttu-id="dcffc-105">Как правило, при использовании WIF для защиты ресурсов приложения проверяющей стороны, которая может размещаться на отдельном компьютере или в веб-ферме, сеанс с клиентом устанавливается на основе токена безопасности, полученного из службы маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="dcffc-105">In the typical case, when WIF is used to secure resources of an RP application – whether the RP is running on a single computer or in a web farm -- a session is established with the client based on the security token that was obtained from the security token service (STS).</span></span> <span data-ttu-id="dcffc-106">Благодаря этому клиенту не приходится проходить проверку подлинности в службе STS при каждом запросе ресурса приложения, находящегося под защитой WIF.</span><span class="sxs-lookup"><span data-stu-id="dcffc-106">This is to avoid forcing the client to have to authenticate at the STS for every application resource that is secured using WIF.</span></span> <span data-ttu-id="dcffc-107">Дополнительные сведения о том, как WIF работает с сеансами, см. в разделе [Управление сеансами WIF](../../../docs/framework/security/wif-session-management.md).</span><span class="sxs-lookup"><span data-stu-id="dcffc-107">For more information about how WIF handles sessions, see [WIF Session Management](../../../docs/framework/security/wif-session-management.md).</span></span>  
  
 <span data-ttu-id="dcffc-108">При использовании параметров по умолчанию WIF выполняет указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dcffc-108">When default settings are used, WIF does the following:</span></span>  
  
-   <span data-ttu-id="dcffc-109">Использует экземпляр класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> для чтения и записи токена сеанса (экземпляра класса <xref:System.IdentityModel.Tokens.SessionSecurityToken>), с помощью которого передаются утверждения и другие сведения о токене безопасности, использовавшемся для проверки подлинности, а также сведения о самом сеансе.</span><span class="sxs-lookup"><span data-stu-id="dcffc-109">It uses an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class to read and write a session token (an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityToken> class) that carries the claims and other information about the security token that was used for authentication as well as information about the session itself.</span></span> <span data-ttu-id="dcffc-110">Токен сеанса упаковывается и сохраняется в файле cookie сеанса.</span><span class="sxs-lookup"><span data-stu-id="dcffc-110">The session token is packaged and stored in a session cookie.</span></span> <span data-ttu-id="dcffc-111">По умолчанию для защиты токена сеанса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> применяет класс <xref:System.IdentityModel.ProtectedDataCookieTransform>, который использует API защиты данных (DPAPI).</span><span class="sxs-lookup"><span data-stu-id="dcffc-111">By default, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> uses the <xref:System.IdentityModel.ProtectedDataCookieTransform> class, which uses the Data Protection API (DPAPI), to protect the session token.</span></span> <span data-ttu-id="dcffc-112">Интерфейс API защиты данных обеспечивает защиту с помощью учетных данных пользователя или компьютера и сохраняет данные ключей в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="dcffc-112">The DPAPI provides protection by using the user or machine credentials and stores the key data in the user profile.</span></span>  
  
-   <span data-ttu-id="dcffc-113">Он использует стандартную реализацию класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> в памяти для хранения и обработки токена сеанса.</span><span class="sxs-lookup"><span data-stu-id="dcffc-113">It uses a default, in-memory implementation of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class to store and process the session token.</span></span>  
  
 <span data-ttu-id="dcffc-114">Эти параметры по умолчанию подходят для случаев, когда приложение проверяющей стороны развернуто на отдельном компьютере. Однако если оно развернуто в веб-ферме, каждый HTTP-запрос может отправляться в экземпляры приложения проверяющей стороны, работающие на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="dcffc-114">These default settings work in scenarios in which the RP application is deployed on a single computer; however, when deployed in a web farm, each HTTP request may be sent to and processed by a different instance of the RP application running on a different computer.</span></span> <span data-ttu-id="dcffc-115">В такой ситуации описанные выше параметры WIF по умолчанию не подходят, так как защита и кэширование токенов привязаны к определенному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="dcffc-115">In this scenario, the default WIF settings described above will not work because both token protection and token caching are dependent on a specific computer.</span></span>  
  
 <span data-ttu-id="dcffc-116">Чтобы развернуть приложение проверяющей стороны в веб-ферме, необходимо сделать так, чтобы обработка токенов сеансов (а также воспроизводимых токенов) не зависела от приложения, работающего на определенном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dcffc-116">To deploy an RP application in a web farm, you must ensure that the processing of session tokens (as well as of replayed tokens) is not dependent on the application running on a specific computer.</span></span> <span data-ttu-id="dcffc-117">Один из способов — реализовать приложение проверяющей стороны так, чтобы оно использовало возможности, предоставляемые элементом конфигурации `<machineKey>` ASP.NET, и обеспечивало распределенное кэширование для обработки токенов сеансов и воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="dcffc-117">One way to do this is to implement your RP application so that it uses the functionality provided by the ASP.NET `<machineKey>` configuration element and provides distributed caching for processing session tokens and replayed tokens.</span></span> <span data-ttu-id="dcffc-118">Элемент `<machineKey>` позволяет указывать ключи, необходимые для проверки, шифрования и расшифровки токенов, в файле конфигурации, то есть указывать одни и те же ключи для разных компьютеров в веб-ферме.</span><span class="sxs-lookup"><span data-stu-id="dcffc-118">The `<machineKey>` element allows you to specify the keys needed to validate, encrypt, and decrypt tokens in a configuration file, which enables you to specify the same keys on different computers in the web farm.</span></span> <span data-ttu-id="dcffc-119">WIF предоставляет специальный обработчик токенов сеансов <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, который защищает токены с помощью ключей, указанных в элементе `<machineKey>`.</span><span class="sxs-lookup"><span data-stu-id="dcffc-119">WIF provides a specialized session token handler, the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, that protects tokens by using the keys specified in the `<machineKey>` element.</span></span> <span data-ttu-id="dcffc-120">Для реализации такого подхода следует придерживаться изложенных ниже правил.</span><span class="sxs-lookup"><span data-stu-id="dcffc-120">To implement this strategy, you can follow these guidelines:</span></span>  
  
-   <span data-ttu-id="dcffc-121">Используйте элемент `<machineKey>` ASP.NET в файле конфигурации, чтобы явно указать ключи подписания и шифрования, которые можно использовать на разных компьютерах в ферме.</span><span class="sxs-lookup"><span data-stu-id="dcffc-121">Use the ASP.NET `<machineKey>` element in configuration to explicitly specify signing and encryption keys that can be used across computers in the farm.</span></span> <span data-ttu-id="dcffc-122">Ниже приведен пример кода XML со спецификацией элемента `<machineKey>` внутри элемента `<system.web>` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dcffc-122">The following XML shows the specification of the `<machineKey>` element under the `<system.web>` element in a configuration file.</span></span>  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   <span data-ttu-id="dcffc-123">Настройте в приложении использование обработчика <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, добавив его в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="dcffc-123">Configure the application to use the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> by adding it to the token handler collection.</span></span> <span data-ttu-id="dcffc-124">Сначала из коллекции обработчиков токенов нужно удалить обработчик <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (или любой другой обработчик, производный от класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>), если он имеется.</span><span class="sxs-lookup"><span data-stu-id="dcffc-124">You must first remove the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (or any handler derived from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class) from the token handler collection if such a handler is present.</span></span> <span data-ttu-id="dcffc-125">Обработчик <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> использует класс <xref:System.IdentityModel.Services.MachineKeyTransform>, который защищает файл cookie сеанса с помощью криптографических данных, указанных в файле `<machineKey>`.</span><span class="sxs-lookup"><span data-stu-id="dcffc-125">The <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> uses the <xref:System.IdentityModel.Services.MachineKeyTransform> class, which protects the session cookie data by using the cryptographic material specified in the `<machineKey>` element.</span></span> <span data-ttu-id="dcffc-126">Ниже приведен код XML, демонстрирующий добавление <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="dcffc-126">The following XML shows how to add the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> to a token handler collection.</span></span>  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   <span data-ttu-id="dcffc-127">Выполните наследование от класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> и реализуйте распределенное кэширование, то есть кэш, доступный со всех компьютеров в ферме, на которых может размещаться проверяющая сторона.</span><span class="sxs-lookup"><span data-stu-id="dcffc-127">Derive from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and implement distributed caching, that is, a cache that is accessible from all computers in the farm on which the RP might run.</span></span> <span data-ttu-id="dcffc-128">Настройте проверяющую сторону так, чтобы она использовала распределенный кэш, добавив элемент [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dcffc-128">Configure the RP to use your distributed cache by specifying the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element in the configuration file.</span></span> <span data-ttu-id="dcffc-129">Вы можете переопределить метод <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> в производном классе, чтобы реализовать дочерние элементы элемента `<sessionSecurityTokenCache>`, если они необходимы.</span><span class="sxs-lookup"><span data-stu-id="dcffc-129">You can override the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> method in your derived class to implement child elements of the `<sessionSecurityTokenCache>` element if they are required.</span></span>  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!--optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     <span data-ttu-id="dcffc-130">Один из способов реализации распределенного кэширования — предоставить внешний интерфейс WCF для пользовательского кэша.</span><span class="sxs-lookup"><span data-stu-id="dcffc-130">One way to implement distributed caching is to provide a WCF front end for your custom cache.</span></span> <span data-ttu-id="dcffc-131">Дополнительные сведения о реализации службы кэширования WCF см. в разделе [Служба кэширования WCF](#BKMK_TheWCFCachingService).</span><span class="sxs-lookup"><span data-stu-id="dcffc-131">For more information about implementing a WCF caching service, see [The WCF Caching Service](#BKMK_TheWCFCachingService).</span></span> <span data-ttu-id="dcffc-132">Дополнительные сведения о реализации клиента WCF, который приложение проверяющей стороны может использовать для вызова службы кэширования, см. в разделе [Клиент кэширования WCF](#BKMK_TheWCFClient).</span><span class="sxs-lookup"><span data-stu-id="dcffc-132">For more information about implementing a WCF client that the RP application can use to call the caching service, see [The WCF Caching Client](#BKMK_TheWCFClient).</span></span>  
  
-   <span data-ttu-id="dcffc-133">Если приложение обнаруживает воспроизводимые токены, необходимо использовать аналогичный подход, реализовав распределенное кэширование для кэша воспроизведения токенов. Для этого выполните наследование от класса <xref:System.IdentityModel.Tokens.TokenReplayCache> и укажите службу кэширования воспроизводимых токенов в элементе конфигурации [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).</span><span class="sxs-lookup"><span data-stu-id="dcffc-133">If your application detects replayed tokens you must follow a similar distributed caching strategy for the token replay cache by deriving from <xref:System.IdentityModel.Tokens.TokenReplayCache> and pointing to your token replay caching service in the [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) configuration element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dcffc-134">Пример XML-кода и кода в этом разделе берется из [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) образца.</span><span class="sxs-lookup"><span data-stu-id="dcffc-134">All of the example XML and code in this topic is taken from the [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dcffc-135">Примеры в этой статье предоставляются как есть и не предназначены для использования в рабочем коде без изменения.</span><span class="sxs-lookup"><span data-stu-id="dcffc-135">The examples in this topic are provided as-is and are not intended to be used in production code without modification.</span></span>  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a><span data-ttu-id="dcffc-136">Служба кэширования WCF</span><span class="sxs-lookup"><span data-stu-id="dcffc-136">The WCF Caching Service</span></span>  
 <span data-ttu-id="dcffc-137">Приведенный ниже интерфейс определяет контракт между службой кэширования WCF и клиентом WCF, который используется приложением проверяющей стороны для взаимодействия с этой службой.</span><span class="sxs-lookup"><span data-stu-id="dcffc-137">The following interface defines the contract between the WCF caching service and the WCF client used by the relying party application to communicate with it.</span></span> <span data-ttu-id="dcffc-138">Он предоставляет методы класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> как операции службы.</span><span class="sxs-lookup"><span data-stu-id="dcffc-138">It essentially exposes the methods of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class as service operations.</span></span>  
  
```  
[ServiceContract()]  
public interface ISessionSecurityTokenCacheService  
{  
    [OperationContract]  
    void AddOrUpdate(string endpointId, string contextId, string keyGeneration, SessionSecurityToken value, DateTime expiryTime);  
  
    [OperationContract]  
    IEnumerable<SessionSecurityToken> GetAll(string endpointId, string contextId);  
  
    [OperationContract]  
    SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration);  
  
    [OperationContract(Name = "RemoveAll")]  
    void RemoveAll(string endpointId, string contextId);  
  
    [OperationContract(Name = "RemoveAllByEndpointId")]  
    void RemoveAll(string endpointId);  
  
    [OperationContract]  
    void Remove(string endpointId, string contextId, string keyGeneration);  
}  
```  
  
 <span data-ttu-id="dcffc-139">В приведенном ниже коде показана реализация службы кэширования WCF.</span><span class="sxs-lookup"><span data-stu-id="dcffc-139">The following code shows the implementation of the WCF caching service.</span></span> <span data-ttu-id="dcffc-140">В этом примере используется кэш токенов сеансов в памяти, реализуемый по умолчанию платформой WIF.</span><span class="sxs-lookup"><span data-stu-id="dcffc-140">In this example, the default, in-memory session token cache implemented by WIF is used.</span></span> <span data-ttu-id="dcffc-141">В качестве альтернативы можно использовать устойчивый кэш на основе базы данных.</span><span class="sxs-lookup"><span data-stu-id="dcffc-141">Alternatively, you could implement a durable cache backed by a database.</span></span> `ISessionSecurityTokenCacheService` <span data-ttu-id="dcffc-142">Определяет интерфейс, показанный выше.</span><span class="sxs-lookup"><span data-stu-id="dcffc-142">defines the interface shown above.</span></span> <span data-ttu-id="dcffc-143">В этом примере для краткости показаны не все методы, требуемые для реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dcffc-143">In this example, not all of the methods required to implement the interface are shown for brevity.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace WcfSessionSecurityTokenCacheService  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class SessionSecurityTokenCacheService : ISessionSecurityTokenCacheService  
    {  
        SessionSecurityTokenCache internalCache;  
  
        // sets the internal cache used by the service to the default WIF in-memory cache.  
        public SessionSecurityTokenCacheService()  
        {  
            internalCache = new IdentityModelCaches().SessionSecurityTokenCache;  
        }  
  
        ...  
  
        public SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration)  
        {  
            // Delegates to the default, in-memory MruSessionSecurityTokenCache used by WIF  
            SessionSecurityToken token = internalCache.Get(new SessionSecurityTokenCacheKey(endpointId, GetContextId(contextId), GetKeyGeneration(keyGeneration)));  
            return token;  
        }  
  
        ...  
  
        private static UniqueId GetContextId(string contextIdString)  
        {  
            return contextIdString == null ? null : new UniqueId(contextIdString);  
        }  
  
        private static UniqueId GetKeyGeneration(string keyGenerationString)  
        {  
            return keyGenerationString == null ? null : new UniqueId(keyGenerationString);  
        }  
    }  
}  
```  
  
<a name="BKMK_TheWCFClient"></a>   
## <a name="the-wcf-caching-client"></a><span data-ttu-id="dcffc-144">Клиент кэширования WCF</span><span class="sxs-lookup"><span data-stu-id="dcffc-144">The WCF Caching Client</span></span>  
 <span data-ttu-id="dcffc-145">В этом разделе показана реализация класса, производного от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>, который делегирует вызовы к службе кэширования.</span><span class="sxs-lookup"><span data-stu-id="dcffc-145">This section shows the implementation of a class that derives from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and that delegates calls to the caching service.</span></span> <span data-ttu-id="dcffc-146">Чтобы настроить приложение для использования этого класса, используется элемент [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md), как показано в приведенном ниже коде XML.</span><span class="sxs-lookup"><span data-stu-id="dcffc-146">You configure the RP application to use this class through the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element as in the following XML</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 <span data-ttu-id="dcffc-147">Этот класс переопределяет метод <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> для получения конечной точки службы из пользовательского дочернего элемента `<cacheServiceAddress>` элемента `<sessionSecurityTokenCache>`.</span><span class="sxs-lookup"><span data-stu-id="dcffc-147">The class overrides the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> method to get the service endpoint from the custom `<cacheServiceAddress>` child element of the `<sessionSecurityTokenCache>` element.</span></span> <span data-ttu-id="dcffc-148">С помощью этой конечной точки инициализируется канал `ISessionSecurityTokenCacheService`, по которому класс может взаимодействовать со службой.</span><span class="sxs-lookup"><span data-stu-id="dcffc-148">It uses this endpoint to initialize an `ISessionSecurityTokenCacheService` channel over which it can communicate with the service.</span></span>  <span data-ttu-id="dcffc-149">В этом примере для краткости показаны не все методы, требуемые для реализации класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>.</span><span class="sxs-lookup"><span data-stu-id="dcffc-149">In this example, not all of the methods required to implement the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class are shown for brevity.</span></span>  
  
```  
using System;  
using System.Configuration;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace CacheLibrary  
{  
    /// <summary>  
    /// This class acts as a proxy to the WcfSessionSecurityTokenCacheService.  
    /// </summary>  
    public class SharedSessionSecurityTokenCache : SessionSecurityTokenCache, ICustomIdentityConfiguration  
    {  
        private ISessionSecurityTokenCacheService WcfSessionSecurityTokenCacheServiceClient;  
  
        internal SharedSessionSecurityTokenCache()  
        {  
        }  
  
        /// <summary>  
        /// Creates a client channel to call the service host.  
        /// </summary>  
        protected void Initialize(string cacheServiceAddress)  
        {  
            if (this.WcfSessionSecurityTokenCacheServiceClient != null)  
            {  
                return;  
            }  
  
            ChannelFactory<ISessionSecurityTokenCacheService> cf = new ChannelFactory<ISessionSecurityTokenCacheService>(  
                new WS2007HttpBinding(SecurityMode.None),  
                new EndpointAddress(cacheServiceAddress));  
            this.WcfSessionSecurityTokenCacheServiceClient = cf.CreateChannel();  
        }  
  
        #region SessionSecurityTokenCache Members  
        // Delegates the following operations to the centralized session security token cache service in the web farm.  
  
        ...  
  
        public override SessionSecurityToken Get(SessionSecurityTokenCacheKey key)  
        {  
            return this.WcfSessionSecurityTokenCacheServiceClient.Get(key.EndpointId, GetContextIdString(key), GetKeyGenerationString(key));  
        }  
  
        ...  
  
        #endregion  
  
        #region ICustomIdentityConfiguration Members  
        // Called from configuration infrastructure to load custom elements  
        public void LoadCustomConfiguration(XmlNodeList nodeList)  
        {  
            // Retrieve the endpoint address of the centralized session security token cache service running in the web farm  
            if (nodeList.Count == 0)  
            {  
                throw new ConfigurationException("No child config element found under <sessionSecurityTokenCache>.");  
            }  
  
            XmlElement cacheServiceAddressElement = nodeList.Item(0) as XmlElement;  
            if (cacheServiceAddressElement.LocalName != "cacheServiceAddress")  
            {  
                throw new ConfigurationException("First child config element under <sessionSecurityTokenCache> is expected to be <cacheServiceAddress>.");  
            }  
  
            string cacheServiceAddress = null;  
            if (cacheServiceAddressElement.Attributes["url"] != null)  
            {  
                cacheServiceAddress = cacheServiceAddressElement.Attributes["url"].Value;  
            }  
            else  
            {  
                throw new ConfigurationException("<cacheServiceAddress> is expected to contain a 'url' attribute.");  
            }  
  
            // Initialize the proxy to the WebFarmSessionSecurityTokenCacheService  
            this.Initialize(cacheServiceAddress);  
        }  
        #endregion  
  
        private static string GetKeyGenerationString(SessionSecurityTokenCacheKey key)  
        {  
            return key.KeyGeneration == null ? null : key.KeyGeneration.ToString();  
        }  
  
        private static string GetContextIdString(SessionSecurityTokenCacheKey key)  
        {  
            return GetContextIdString(key.ContextId);  
        }  
  
        private static string GetContextIdString(UniqueId contextId)  
        {  
            return contextId == null ? null : contextId.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcffc-150">См. также</span><span class="sxs-lookup"><span data-stu-id="dcffc-150">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>
- <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>
- [<span data-ttu-id="dcffc-151">Управление сеансами WIF</span><span class="sxs-lookup"><span data-stu-id="dcffc-151">WIF Session Management</span></span>](../../../docs/framework/security/wif-session-management.md)
