---
title: WIF и веб-фермы
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
ms.openlocfilehash: e6806971bd2260785d66bfdb54a3e2938043c746
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967190"
---
# <a name="wif-and-web-farms"></a>WIF и веб-фермы
Если вы используете Windows Identity Foundation (WIF) для защиты ресурсов приложения проверяющей стороны, развернутого в веб-ферме, необходимо выполнить определенные действия, чтобы платформа WIF могла обрабатывать токены от экземпляров этого приложения, работающих на разных компьютерах в ферме. Обработка включает в себя проверку подписей токенов сеансов, шифрование и расшифровку токенов сеансов, их кэширование, а также обнаружение повторно используемых маркеров безопасности.  
  
 Как правило, при использовании WIF для защиты ресурсов приложения проверяющей стороны, которая может размещаться на отдельном компьютере или в веб-ферме, сеанс с клиентом устанавливается на основе токена безопасности, полученного из службы маркеров безопасности (STS). Благодаря этому клиенту не приходится проходить проверку подлинности в службе STS при каждом запросе ресурса приложения, находящегося под защитой WIF. Дополнительные сведения о том, как WIF работает с сеансами, см. в разделе [Управление сеансами WIF](../../../docs/framework/security/wif-session-management.md).  
  
 При использовании параметров по умолчанию WIF выполняет указанные ниже действия.  
  
- Использует экземпляр класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> для чтения и записи токена сеанса (экземпляра класса <xref:System.IdentityModel.Tokens.SessionSecurityToken>), с помощью которого передаются утверждения и другие сведения о токене безопасности, использовавшемся для проверки подлинности, а также сведения о самом сеансе. Токен сеанса упаковывается и сохраняется в файле cookie сеанса. По умолчанию для защиты токена сеанса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> применяет класс <xref:System.IdentityModel.ProtectedDataCookieTransform>, который использует API защиты данных (DPAPI). Интерфейс API защиты данных обеспечивает защиту с помощью учетных данных пользователя или компьютера и сохраняет данные ключей в профиле пользователя.  
  
- Он использует стандартную реализацию класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> в памяти для хранения и обработки токена сеанса.  
  
 Эти параметры по умолчанию подходят для случаев, когда приложение проверяющей стороны развернуто на отдельном компьютере. Однако если оно развернуто в веб-ферме, каждый HTTP-запрос может отправляться в экземпляры приложения проверяющей стороны, работающие на разных компьютерах. В такой ситуации описанные выше параметры WIF по умолчанию не подходят, так как защита и кэширование токенов привязаны к определенному компьютеру.  
  
 Чтобы развернуть приложение проверяющей стороны в веб-ферме, необходимо сделать так, чтобы обработка токенов сеансов (а также воспроизводимых токенов) не зависела от приложения, работающего на определенном компьютере. Один из способов — реализовать приложение проверяющей стороны так, чтобы оно использовало возможности, предоставляемые элементом конфигурации `<machineKey>` ASP.NET, и обеспечивало распределенное кэширование для обработки токенов сеансов и воспроизводимых токенов. Элемент `<machineKey>` позволяет указывать ключи, необходимые для проверки, шифрования и расшифровки токенов, в файле конфигурации, то есть указывать одни и те же ключи для разных компьютеров в веб-ферме. WIF предоставляет специальный обработчик токенов сеансов <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, который защищает токены с помощью ключей, указанных в элементе `<machineKey>`. Для реализации такого подхода следует придерживаться изложенных ниже правил.  
  
- Используйте элемент `<machineKey>` ASP.NET в файле конфигурации, чтобы явно указать ключи подписания и шифрования, которые можно использовать на разных компьютерах в ферме. Ниже приведен пример кода XML со спецификацией элемента `<machineKey>` внутри элемента `<system.web>` в файле конфигурации.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
- Настройте в приложении использование обработчика <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, добавив его в коллекцию обработчиков токенов. Сначала из коллекции обработчиков токенов нужно удалить обработчик <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (или любой другой обработчик, производный от класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>), если он имеется. Обработчик <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> использует класс <xref:System.IdentityModel.Services.MachineKeyTransform>, который защищает файл cookie сеанса с помощью криптографических данных, указанных в файле `<machineKey>`. Ниже приведен код XML, демонстрирующий добавление <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> в коллекцию обработчиков токенов.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
- Выполните наследование от класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> и реализуйте распределенное кэширование, то есть кэш, доступный со всех компьютеров в ферме, на которых может размещаться проверяющая сторона. Настройте проверяющую сторону так, чтобы она использовала распределенный кэш, добавив элемент [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) в файл конфигурации. Вы можете переопределить метод <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> в производном классе, чтобы реализовать дочерние элементы элемента `<sessionSecurityTokenCache>`, если они необходимы.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!--optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Один из способов реализации распределенного кэширования — предоставить внешний интерфейс WCF для пользовательского кэша. Дополнительные сведения о реализации службы кэширования WCF см. в разделе [Служба кэширования WCF](#BKMK_TheWCFCachingService). Дополнительные сведения о реализации клиента WCF, который приложение проверяющей стороны может использовать для вызова службы кэширования, см. в разделе [Клиент кэширования WCF](#BKMK_TheWCFClient).  
  
- Если приложение обнаруживает воспроизводимые токены, необходимо использовать аналогичный подход, реализовав распределенное кэширование для кэша воспроизведения токенов. Для этого выполните наследование от класса <xref:System.IdentityModel.Tokens.TokenReplayCache> и укажите службу кэширования воспроизводимых токенов в элементе конфигурации [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).  
  
> [!IMPORTANT]
> Все примеры XML и код в этом разделе взяты из примера [клаимсаваревебфарм](https://go.microsoft.com/fwlink/?LinkID=248408) .  
  
> [!IMPORTANT]
> Примеры в этой статье предоставляются как есть и не предназначены для использования в рабочем коде без изменения.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a>Служба кэширования WCF  
 Приведенный ниже интерфейс определяет контракт между службой кэширования WCF и клиентом WCF, который используется приложением проверяющей стороны для взаимодействия с этой службой. Он предоставляет методы класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> как операции службы.  
  
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
  
 В приведенном ниже коде показана реализация службы кэширования WCF. В этом примере используется кэш токенов сеансов в памяти, реализуемый по умолчанию платформой WIF. В качестве альтернативы можно использовать устойчивый кэш на основе базы данных. `ISessionSecurityTokenCacheService` определяет приведенный выше интерфейс. В этом примере для краткости показаны не все методы, требуемые для реализации интерфейса.  
  
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
## <a name="the-wcf-caching-client"></a>Клиент кэширования WCF  
 В этом разделе показана реализация класса, производного от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>, который делегирует вызовы к службе кэширования. Чтобы настроить приложение для использования этого класса, используется элемент [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md), как показано в приведенном ниже коде XML.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 Этот класс переопределяет метод <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> для получения конечной точки службы из пользовательского дочернего элемента `<cacheServiceAddress>` элемента `<sessionSecurityTokenCache>`. С помощью этой конечной точки инициализируется канал `ISessionSecurityTokenCacheService`, по которому класс может взаимодействовать со службой.  В этом примере для краткости показаны не все методы, требуемые для реализации класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>
- <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>
- [Управление сеансами WIF](../../../docs/framework/security/wif-session-management.md)
