---
title: Поддержка кэширования для веб-служб HTTP WCF
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: 63c83cc1af9a3ccfdbdd79f8d0480e6c29eaf2f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185432"
---
# <a name="caching-support-for-wcf-web-http-services"></a>Поддержка кэширования для веб-служб HTTP WCF

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]позволяет использовать механизм декларативного кэширования, уже доступный в ASP.NET в службах WCF Web HTTP. Это позволяет кэшировать ответы от операций службы WCF Web HTTP. Когда пользователь отправляет инструкцию HTTP GET службе, настроенной для кэширования, ASP.NET отправляет обратно кэшированный ответ, метод службы при этом не вызывается. По истечении срока действия кэш в следующий раз, когда пользователь отправит инструкцию HTTP GET, будет вызван метод службы и ответ будет снова кэширован. Для получения дополнительной информации о ASP.NET кэширования, см [ASP.NET Обзор кэширования](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
## <a name="basic-web-http-service-caching"></a>Кэширование базовой службы Web HTTP  

  Для включения кэширования службы WEB HTTP необходимо включить ASP.NET <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> совместимость, <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> применяя настройки службы к или <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>к .  
  
 .NET Framework 4 вводит новый атрибут под названием, <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> который позволяет указать имя профиля кэша. Этот атрибут применяется к операции службы. В следующем примере атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> применяется к службе для включения совместимости с ASP.NET, а операция `GetCustomer` настраивается для кэширования. Атрибут <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> задает профиль кэширования, содержащий используемые параметры кэширования.  
  
```csharp
[ServiceContract]
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]
public class Service
{
    [WebGet(UriTemplate = "{id}")]
    [AspNetCacheProfile("CacheFor60Seconds")]
    public Customer GetCustomer(string id)
    {
        // ...
    }
}
```  
  
Кроме того, включите режим совместимости ASP.NET в файле Web.config, как показано в следующем примере.  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> Если режим совместимости с ASP.NET не включен и используется <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, то возникнет исключение.  
  
 Имя профиля кэша, заданное атрибутом <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, идентифицирует профиль кэша, добавленный в файл конфигурации Web.config. Профиль кэша определяется в `outputCacheSetting` <> элементом, как показано в следующем примере конфигурации.  
  
```xml
<!-- ...  -->
<system.web>  
   <caching>  
      <outputCacheSettings>  
         <outputCacheProfiles>  
            <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable"/>  
         </outputCacheProfiles>  
      </outputCacheSettings>  
   </caching>  
   <!-- ... -->  
</system.web>  
```  
  
 Этот же элемент конфигурации доступен приложениям ASP.NET. Для получения дополнительной информации о <xref:System.Web.Configuration.OutputCacheProfile>ASP.NET профилях кэша см. Самыми важными атрибутами для служб Web HTTP в профиле кэша являются `cacheDuration` и `varyByParam`. Оба атрибута обязательные. `cacheDuration` задает время (в секундах), в течение которого ответ должен храниться в кэше. `varyByParam` позволяет задать параметр строки запроса, используемый для кэширования ответов. Все запросы, составленные с разными значениями параметра строки запроса, кэшируются отдельно. Например, после того, как `http://MyServer/MyHttpService/MyOperation?param=10`первоначальный запрос будет сделан, все последующие запросы, сделанные с тем же URI, будут возвращены кэшированным ответом (до тех пор, пока продолжительность кэша не иссякнет). Ответы для аналогичного запроса, имеющего другое значение для параметра строки запроса, кэшируются отдельно. Если такое раздельное кэширование нежелательно, установите параметр `varyByParam` в значение «none».  
  
## <a name="sql-cache-dependency"></a>Зависимость кэша SQL  

  Ответы службы Web HTTP также могут быть кэшироваться с зависимостью от кэша SQL. Если служба WCF Web HTTP зависит от данных, которые хранятся в базе данных SQL, можно кэшировать ответ службы и аннулировать кэшированный ответ при изменении данных в таблице базы данных SQL. Это полностью настраивается в файле Web.config. Во-первых, определите строку соединения в элементе <`connectionStrings`>.  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 Затем необходимо включить зависимость кэша кэша в элементе кэша <`caching`> в элементе <`system.web`>, как показано в следующем примере конфигурации.  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>
    </sqlCacheDependency>
    <!-- ... -->
  </caching>
  <!-- ... -->
</system.web>
```  
  
 В данном случае зависимость кэша SQL включена и задан интервал опроса в 1000 миллисекунд. Каждый раз при истечении времени опроса таблица базы данных проверяется на предмет обновлений. Если найдены изменения, то содержимое кэша удаляется, при этом при следующем вызове операции службы новый ответ будет помещен в кэш. В <`sqlCacheDependency`> элемент добавить базы данных и `databases` ссылки строксоединения в <> элемент, как показано в следующем примере.  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>  
    </sqlCacheDependency>  
    <!-- ... -->  
  </caching>  
  <!-- ... -->  
</system.web>  
```  
  
 Далее необходимо настроить настройки кэша `caching` вывода в <> элемент, показанный в следующем примере.  
  
```xml
<system.web>
  <caching>  
    <!-- ...  -->
    <outputCacheSettings>
      <outputCacheProfiles>
        <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable" />
      </outputCacheProfiles>
    </outputCacheSettings>
  </caching>
  <!-- ... -->
</system.web>
```  
  
 Здесь продолжительность кэша установлена до `varyByParam` 60 секунд, `sqlDependency` установлена на нет, и устанавливается в запятой-делеограниченный список баз данных имя / таблица пар, разделенных толстой кишки. При изменении данных в `MyTable` ответ для операции службы удаляется из кэша. При вызове операции формируется новый ответ (путем вызова операции службы), который помещается в кэш и возвращается клиенту.  
  
> [!IMPORTANT]
> Для ASP.NET для доступа к базе данных S'L необходимо использовать [инструмент регистрации серверов ASP.NET S'L.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90)) Помимо этого, необходимо разрешить соответствующей учетной записи пользователя доступ к базе данных и таблице. Для получения дополнительной [информации см.](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100))  
  
## <a name="conditional-http-get-based-caching"></a>Условное кэширование на основе HTTP GET  

  В сценариях Web HTTP условный HTTP GET часто используется службами для реализации интеллектуального кэширования HTTP, как описано в [спецификации HTTP.](https://www.w3.org/Protocols/rfc2616/rfc2616.html) Для этого служба должна установить значение заголовка ETag в ответе HTTP. Также необходимо посмотреть заголовок If-None-Match в запросе HTTP, чтобы проверить, совпадает ли какой-либо элемент ETag с текущим элементом ETag.  
  
 Для запросов GET и HEAD метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> получает значение ETag и сравнивает его с заголовком If-None-Match запроса. Если заголовок присутствует и есть совпадение, <xref:System.ServiceModel.Web.WebFaultException> код статуса HTTP 304 (не изменен) брошен и заголовок ETag добавляется в ответ с соответствующим ETag.  
  
 Одна перегрузка метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> получает последнюю измененную дату и проверяет ее относительно заголовка If-Modified-Since запроса. Если заголовок присутствует и источник не был изменен, то возникает исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния HTTP 304 (нет изменений).  
  
 Для запросов PUT, POST и DELETE метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> получает текущее значение ETag источника. Если текущее значение ETag является нулевым, метод проверяет, что заголовок If-None- Match имеет значение "К".  Если текущее значение ETag не является значением по умолчанию, то метод проверяет текущее значение ETag относительно заголовка If-Match запроса. В обоих случаях метод выдает исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния HTTP 412 (предварительное условие не выполнено), если ожидаемый заголовок не присутствует в запросе либо его значение не проходит проверку условия, и задает заголовку ETag текущее значение ETag.  
  
 Методы `CheckConditional` и <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> гарантируют, что значение ETag, заданное для заголовка ответа, является допустимым значением ETag в соответствии со спецификацией протокола HTTP. Это предполагает заключение значения ETag в двойные кавычки (если они отсутствуют) и правильное экранирование символов двойных кавычек внутри строки. Нестрогое сравнение ETag не поддерживается.  
  
 В следующем примере показано использование этих методов.  
  
```csharp
[WebGet(UriTemplate = "{id}"), Description("Returns the specified customer from customers collection. Returns NotFound if there is no such customer. Supports conditional GET.")]
public Customer GetCustomer(string id)
{
    lock (writeLock)
    {
        // return NotFound if there is no item with the specified id.
        object itemEtag = customerEtags[id];
        if (itemEtag == null)
        {
            throw new WebFaultException(HttpStatusCode.NotFound);
        }
  
        // return NotModified if the client did a conditional GET and the customer item has not changed
        // since when the client last retrieved it
        WebOperationContext.Current.IncomingRequest.CheckConditionalRetrieve((long)itemEtag);
        Customer result = this.customers[id] as Customer;

        // set the customer etag before returning the result
        WebOperationContext.Current.OutgoingResponse.SetETag((long)itemEtag);
        return result;
    }
}
```  
  
## <a name="security-considerations"></a>Соображения безопасности  
 Не должны кэшироваться ответы для запросов, требующих авторизации, так как авторизация не выполняется при получении ответа из кэша.  Кэширование таких ответов серьезно снижает безопасность.  Обычно запросы, требующие авторизации, содержат данные конкретного пользователя, в силу чего кэширование на стороне сервера просто не имеет смысла.  В таких ситуациях практичнее использовать кэширование на стороне клиента или вовсе не использовать кэширование.
