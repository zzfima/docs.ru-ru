---
title: Поддержка кэширования для веб-служб HTTP WCF
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: b6247dd6c178b355fa4de271415b7cac12f6c629
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116681"
---
# <a name="caching-support-for-wcf-web-http-services"></a>Поддержка кэширования для веб-служб HTTP WCF

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] позволяет использовать механизм декларативного кэширования, уже доступный в ASP.NET в веб-службах HTTP WCF. Это позволяет кэшировать ответы от операций службы WCF Web HTTP. Когда пользователь отправляет инструкцию HTTP GET службе, настроенной для кэширования, ASP.NET отправляет обратно кэшированный ответ, метод службы при этом не вызывается. По истечении срока действия кэш в следующий раз, когда пользователь отправит инструкцию HTTP GET, будет вызван метод службы и ответ будет снова кэширован. Дополнительные сведения о кэшировании ASP.NET см. в разделе [Общие сведения о кэшировании ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
## <a name="basic-web-http-service-caching"></a>Кэширование базовой службы Web HTTP  

  Чтобы включить кэширование веб-служб HTTP, необходимо сначала включить совместимость ASP.NET, применив <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> к параметру службы <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> или <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.  
  
 В .NET Framework 4 появился новый атрибут с именем <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, который позволяет указать имя профиля кэша. Этот атрибут применяется к операции службы. В следующем примере атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> применяется к службе для включения совместимости с ASP.NET, а операция `GetCustomer` настраивается для кэширования. Атрибут <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> задает профиль кэширования, содержащий используемые параметры кэширования.  
  
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
  
Также включите режим совместимости ASP.NET в файле Web. config, как показано в следующем примере.  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> Если режим совместимости с ASP.NET не включен и используется <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, то возникнет исключение.  
  
 Имя профиля кэша, заданное атрибутом <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, идентифицирует профиль кэша, добавленный в файл конфигурации Web.config. Профиль кэша определяется с помощью элемента <`outputCacheSetting`>, как показано в следующем примере конфигурации.  
  
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
  
 Этот же элемент конфигурации доступен приложениям ASP.NET. Дополнительные сведения о профилях кэша ASP.NET см. в разделе <xref:System.Web.Configuration.OutputCacheProfile>. Самыми важными атрибутами для служб Web HTTP в профиле кэша являются `cacheDuration` и `varyByParam`. Оба атрибута обязательные. `cacheDuration` задает время (в секундах), в течение которого ответ должен храниться в кэше. `varyByParam` позволяет задать параметр строки запроса, используемый для кэширования ответов. Все запросы, составленные с разными значениями параметра строки запроса, кэшируются отдельно. Например, после выполнения начального запроса к `http://MyServer/MyHttpService/MyOperation?param=10`все последующие запросы, выполненные с использованием того же URI, будут возвращаться в кэшированный ответ (при условии, что срок кэширования не истечет). Ответы для аналогичного запроса, имеющего другое значение для параметра строки запроса, кэшируются отдельно. Если такое раздельное кэширование нежелательно, установите параметр `varyByParam` в значение «none».  
  
## <a name="sql-cache-dependency"></a>Зависимость кэша SQL  

  Ответы службы Web HTTP также могут быть кэшироваться с зависимостью от кэша SQL. Если служба WCF Web HTTP зависит от данных, которые хранятся в базе данных SQL, можно кэшировать ответ службы и аннулировать кэшированный ответ при изменении данных в таблице базы данных SQL. Это полностью настраивается в файле Web.config. Сначала определите строку подключения в элементе <`connectionStrings`>.  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 Затем необходимо включить зависимость кэша SQL в элементе <`caching`> в элементе <`system.web`>, как показано в следующем примере конфигурации.  
  
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
  
 В данном случае зависимость кэша SQL включена и задан интервал опроса в 1000 миллисекунд. Каждый раз при истечении времени опроса таблица базы данных проверяется на предмет обновлений. Если найдены изменения, то содержимое кэша удаляется, при этом при следующем вызове операции службы новый ответ будет помещен в кэш. В элементе <`sqlCacheDependency`> Добавьте базы данных и сослаться на строки подключения в элементе <`databases`>, как показано в следующем примере.  
  
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
  
 Далее необходимо настроить параметры кэша вывода в элементе <`caching`>, как показано в следующем примере.  
  
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
  
 Здесь длительность кэширования устанавливается равным 60 секундам, `varyByParam` имеет значение None, а `sqlDependency` — разделенный точками с запятой список пар имен баз данных и таблиц, разделенных двоеточиями. При изменении данных в `MyTable` ответ для операции службы удаляется из кэша. При вызове операции формируется новый ответ (путем вызова операции службы), который помещается в кэш и возвращается клиенту.  
  
> [!IMPORTANT]
> Чтобы ASP.NET получить доступ к базе данных SQL, необходимо использовать [средство регистрации ASP.NET SQL Server](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90)). Помимо этого, необходимо разрешить соответствующей учетной записи пользователя доступ к базе данных и таблице. Дополнительные сведения см. в разделе [доступ к SQL Server из веб-приложения](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).  
  
## <a name="conditional-http-get-based-caching"></a>Условное кэширование на основе HTTP GET  

  В сценариях Web HTTP условный HTTP-запрос GET часто используется службами для реализации интеллектуального кэширования HTTP, как описано в [спецификации HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616.html). Для этого служба должна задать значение заголовка ETag в HTTP-ответе. Также необходимо посмотреть заголовок If-None-Match в запросе HTTP, чтобы проверить, совпадает ли какой-либо элемент ETag с текущим элементом ETag.  
  
 Для запросов GET и HEAD метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> получает значение ETag и сравнивает его с заголовком If-None-Match запроса. Если заголовок присутствует и имеется совпадение, выдается <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния HTTP 304 (не изменено) и заголовок ETag добавляется в ответ с соответствующим ETag.  
  
 Одна перегрузка метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> получает последнюю измененную дату и проверяет ее относительно заголовка If-Modified-Since запроса. Если заголовок присутствует и источник не был изменен, то возникает исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния HTTP 304 (нет изменений).  
  
 Для запросов PUT, POST и DELETE метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> получает текущее значение ETag источника. Если текущее значение ETag равно null, метод проверяет, что заголовок If-None-Match имеет значение "*".  Если текущее значение ETag не является значением по умолчанию, то метод проверяет текущее значение ETag относительно заголовка If-Match запроса. В обоих случаях метод выдает исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния HTTP 412 (предварительное условие не выполнено), если ожидаемый заголовок не присутствует в запросе либо его значение не проходит проверку условия, и задает заголовку ETag текущее значение ETag.  
  
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
  
## <a name="security-considerations"></a>Вопросы безопасности  
 Не должны кэшироваться ответы для запросов, требующих авторизации, так как авторизация не выполняется при получении ответа из кэша.  Кэширование таких ответов серьезно снижает безопасность.  Обычно запросы, требующие авторизации, содержат данные конкретного пользователя, в силу чего кэширование на стороне сервера просто не имеет смысла.  В таких ситуациях практичнее использовать кэширование на стороне клиента или вовсе не использовать кэширование.
