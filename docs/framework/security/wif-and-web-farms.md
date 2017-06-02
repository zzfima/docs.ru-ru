---
title: "WIF и веб-фермы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WIF и веб-фермы
При использовании Foundation удостоверение Windows \(WIF\) для защиты ресурсов доверяющей стороной \(RP\) приложения, которое развертывается в веб\-ферме необходимо предпринять конкретные действия, чтобы убедиться, что WIF может обрабатывать маркеры из экземпляров приложения RP, работающими на разных компьютерах в ферме.  Эта обработка включает проверки подписей маркеров сеанса, шифрование и расшифровка маркеров сеанса и кэширование маркеров сеансов обнаружение воспроизводятся маркеров безопасности.  
  
 Типичный случай когда WIF используется для защиты ресурсов приложения RP – RP выполняется на одном компьютере или на веб\-ферме\-\-ли установления сеанса с клиентом, в зависимости от маркера безопасности, который был получен от службы маркеров безопасности \(STS\).  Это позволяет избежать принудительного клиент должен пройти проверку подлинности на STS для каждого ресурса приложения, защищенные с помощью WIF.  Дополнительные сведения о как WIF обрабатывает сеансов см. [Управление сеансами WIF](../../../docs/framework/security/wif-session-management.md).  
  
 При использовании параметров по умолчанию WIF выполняет следующие функции:  
  
-   Используется экземпляр класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса для чтения и записи маркера сеанса \(экземпляр <xref:System.IdentityModel.Tokens.SessionSecurityToken> класс\), выполняет заявок и другие сведения о маркер безопасности, который был использован для проверки подлинности, а также сведения о сеансе, сам.  Маркер сеанса упаковываются и хранятся в файле cookie сеанса.  По умолчанию <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> использует <xref:System.IdentityModel.ProtectedDataCookieTransform> класс, который использует API защиты данных \(DPAPI\), чтобы защитить маркер сеанса.  DPAPI обеспечивает защиту с помощью учетных данных пользователя или компьютера и сохраняет ключевые данные в профиле пользователя.  
  
-   Используется по умолчанию, реализация в памяти <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса для хранения и обработки маркер сеанса.  
  
 Эти параметры по умолчанию работают в сценариях, в которых развернуто приложение RP на одном компьютере; Однако при развертывании веб\-фермы, каждый HTTP\-запрос может отправляться и обрабатываются другого экземпляра приложения RP, на другом компьютере.  В этом случае описанные выше параметры WIF по умолчанию не будут работать, поскольку защита маркера и кэширования маркеров, зависят от конкретного компьютера.  
  
 Для развертывания приложения RP веб\-фермы, необходимо убедиться, обработка маркеров сеанса \(а также преобразованных маркеров\) не зависит от приложения, запущенного на конкретном компьютере.  Один из способов добиться этого является реализация RP приложения таким образом, он использует функциональные возможности, предоставляемые ASP.NET `<machineKey>` элемента конфигурации и обеспечивает распределенное кэширование для обработки маркеров сеансов и воспроизведены маркеры.  `<machineKey>` Элемент позволяет задавать ключи, необходимые для проверки, шифрования и расшифровки маркеры в файле конфигурации, который позволяет задать одинаковые ключи на разных компьютерах в веб\-ферме.  WIF предоставляет обработчик маркеров специализированные сеанса, <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, который защищает маркеры с помощью клавиш, указанные в `<machineKey>` элемент.  Для реализации этой стратегии, необходимо выполнить следующее:  
  
-   Используйте ASP.NET `<machineKey>` элемента конфигурации для явного указания подписи и ключей шифрования, которые могут использоваться на компьютерах в ферме.  Следующий код XML показывает спецификации `<machineKey>` элемента под `<system.web>` элемент в файле конфигурации.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   Настройка приложения для использования <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> , добавьте его в коллекцию обработчиков маркеров.  Необходимо сначала удалить <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> \(или любого обработчика производного от <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класс\) из коллекции обработчиков маркеров, если такой обработчик.  <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> Использует <xref:System.IdentityModel.Services.MachineKeyTransform> класс, который обеспечивает защиту данных cookie сеанса с помощью криптографического материала, указанного в `<machineKey>` элемент.  Следующий код XML показывает, как добавить <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> коллекцию обработчика маркера.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   Производные от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> и реализовать распределенное кэширование, то есть кэш, который доступен со всех компьютеров в ферме, на которой может выполняться RP.  Настройте RP использовать распределенном кэше, указав [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) элемент в файле конфигурации.  Можно переопределить <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=fullName> метода в производном классе, чтобы реализовать дочерних элементов `<sessionSecurityTokenCache>` элемент, если они необходимы.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Одним из способов реализации распределенное кэширование является предоставление WCF клиентской части для пользовательского кэша.  Дополнительные сведения о реализации WCF службу кэширования см. [Кэширование службы WCF](#BKMK_TheWCFCachingService).  Дополнительные сведения о реализации клиента WCF, RP приложения можно использовать для вызова службы кэширования см. [Кэширование клиента WCF](#BKMK_TheWCFClient).  
  
-   Если приложение обнаруживает преобразованных маркеры, выполните аналогичные распределенное кэширование стратегию кэширования маркеров воспроизведения, производные от <xref:System.IdentityModel.Tokens.TokenReplayCache> и указатель на маркер воспроизвести службы кэширования в [\<tokenReplayCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемента конфигурации.  
  
> [!IMPORTANT]
>  Пример XML\-файла и кода в этом разделе взяты из [ClaimsAwareWebFarm](см.?LinkID%20=%20248408) \(см.?LinkID \= 248408\) образца.  
  
> [!IMPORTANT]
>  Примеры в этом разделе предоставляются как\-это и не предназначен для использования в рабочем коде без изменения.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## Кэширование службы WCF  
 Следующий интерфейс определяет контракт между кэширования службы WCF и клиент WCF, используемый для связи с ним доверяющая сторона приложения.  По сути, открывает методы <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса как операции службы.  
  
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
  
 Следующий код показывает реализацию WCF службу кэширования.  В этом примере по умолчанию используется реализованных WIF кэша маркеров сеанса в памяти.  Кроме того можно реализовать долговременный кэш резервной базы данных.  `ISessionSecurityTokenCacheService`Определяет интерфейс, показанного выше.  В этом примере не все методы, необходимые для реализации интерфейса отображаются для краткости.  
  
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
## Кэширование клиента WCF  
 В этом разделе показана реализация класса, производного от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> и что делегаты вызывает службу кэширования.  Настройте RP приложения с помощью этого класса через [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) элемент, как показано в следующем XML  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 Класс переопределяет <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> метод, чтобы получить конечную точку службы из настраиваемых `<cacheServiceAddress>` дочерним элементом, `<sessionSecurityTokenCache>` элемент.  Он использует эту конечную точку для инициализации `ISessionSecurityTokenCacheService` канал, по которому он может взаимодействовать со службой.  В этом примере не все методы, необходимые для реализации <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> показан класс для краткости.  
  
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
  
## См. также  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>   
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>   
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>   
 [Управление сеансами WIF](../../../docs/framework/security/wif-session-management.md)