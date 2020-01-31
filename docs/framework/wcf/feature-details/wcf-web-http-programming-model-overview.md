---
title: Общие сведения о модели программирования WCF Web HTTP
ms.date: 03/30/2017
ms.assetid: 381fdc3a-6e6c-4890-87fe-91cca6f4b476
ms.openlocfilehash: 8a4b4ff6c0482ed8a09fe30b7d03afc1f84db581
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739901"
---
# <a name="wcf-web-http-programming-model-overview"></a>Общие сведения о модели программирования WCF Web HTTP
Модель программирования веб-сервера HTTP Windows Communication Foundation (WCF) предоставляет основные элементы, необходимые для сборки веб-служб HTTP с помощью WCF. Службы WCF WEB HTTP предназначены для доступа к широкому спектру возможных клиентов, включая веб-браузеры, и имеют следующие уникальные требования.  
  
- **URI и обработка URI** Универсальные коды ресурсов (URI) играют центральную роль в разработке веб-служб HTTP. Модель программирования WCF WEB HTTP использует классы <xref:System.UriTemplate> и <xref:System.UriTemplateTable> для предоставления возможностей обработки URI.  
  
- **Поддержка операций Get и POST** ВЕБ-службы HTTP используют команду GET для получения данных в дополнение к различным командам Invoke для изменения данных и удаленного вызова. Модель программирования WCF WEB HTTP использует <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute> для связывания операций службы с GET и другими командами HTTP, такими как помещение, публикация и удаление.  
  
- **Несколько форматов данных** Веб-службы обрабатывают множество типов данных в дополнение к сообщениям SOAP. Модель программирования WCF WEB HTTP использует <xref:System.ServiceModel.WebHttpBinding> и <xref:System.ServiceModel.Description.WebHttpBehavior> для поддержки различных форматов данных, включая XML-документы, объекты данных JSON и потоки двоичного содержимого, такие как изображения, видеофайлы или обычный текст.  
  
 Модель программирования WCF WEB HTTP расширяет возможности WCF для использования веб-сценариев, в том числе веб-служб HTTP, AJAX и служб JSON, а также каналов синдикации (ATOM и RSS). Дополнительные сведения о службах AJAX и JSON см. в разделе [Интеграция Ajax и поддержка JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md). Дополнительные сведения об синдикации см. в разделе [Обзор синдикации WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md).  
  
 Какие-либо дополнительные ограничения на типы данных, которые могут быть возвращены из веб-службы HTTP, отсутствуют. При работе веб-службы HTTP могут быть возвращены любые сериализуемые данные. Операции веб-службы HTTP могут быть вызваны веб-браузером, поэтому предусмотрены ограничения, касающиеся того, какие типы данных могут указываться в URL-адресах. Дополнительные сведения о типах, поддерживаемых по умолчанию, см. в разделе **Параметры строки запроса UriTemplate и URL-адреса** ниже. Это поведение по умолчанию можно изменить, предоставив собственную реализацию объекта T:System.ServiceModel.Dispatcher.QueryStringConverter, которая определяет, как преобразовывать параметры, заданные в URL-адресе, в фактические типы параметров. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Dispatcher.QueryStringConverter>.  
  
> [!CAUTION]
> Службы, написанные с помощью модели программирования WCF WEB HTTP, не используют сообщения SOAP. Поскольку протокол SOAP не используется, функции безопасности, предоставляемые WCF, использовать нельзя. Однако можно использовать безопасность уровня транспорта, разместив службу через HTTPS. Дополнительные сведения о безопасности WCF см. в разделе [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md) .  
  
> [!WARNING]
> Установка расширения WebDAV для служб IIS может привести к тому, что веб-службы HTTP будут возвращать ошибку HTTP 405, поскольку расширение WebDAV пытается обрабатывать все запросы PUT. Для решения этой проблемы расширение WebDAV можно удалить либо отключить его для данного веб-узла. Дополнительные сведения см. в разделе [IIS и WebDAV](https://learn.iis.net/page.aspx/357/webdav-for-iis-70/) .  
  
## <a name="uri-processing-with-uritemplate-and-uritemplatetable"></a>Обработка универсального кода ресурса (URI) с помощью UriTemplate и UriTemplateTable  
 Шаблоны URI предоставляют эффективный синтаксис представления больших наборов URI или схожих по структуре URI. Например, следующий шаблон представляет набор всех трехсегментных URI, начинающихся с "a" и заканчивающихся на "c", независимо от значения промежуточного сегмента: a/{segment}/c.  
  
 Данный шаблон описывает универсальные коды ресурса, подобные следующим:  
  
- a/x/c  
  
- a/y/c  
  
- a/z/c  
  
- и т. д.  
  
 В этом шаблоне запись в фигурных скобках ("{segment}") обозначает переменный сегмент, а не литеральное значение.  
  
 Платформа .NET Framework предусматривает API для работы с шаблонами URI, который называется <xref:System.UriTemplate>. `UriTemplates` позволяет выполнять следующие действия.  
  
- Можно вызвать один из `Bind` методов с набором параметров, чтобы получить *полностью закрытый URI* , соответствующий шаблону. Это означает, что все переменные в шаблоне URI заменяются фактическими значениями.  
  
- Можно вызвать `Match`() с потенциальным URI, который использует шаблон для разбиения потенциального URI на составные части и возвращает словарь, содержащий различные части URI, помеченные в соответствии с переменными в шаблоне.  
  
- `Bind`() и `Match`() являются инверсиями, поэтому можно вызвать `Match`( `Bind`( x ) ) и вернуться к той среде, в которой была начата работа.  
  
 Очень часто (особенно на стороне сервера, где необходимо направить запрос операции службы на основе URI), бывает необходимо отслеживать набор объектов <xref:System.UriTemplate> в структуре данных, которые могут независимо обращаться к каждому из включенных шаблонов. <xref:System.UriTemplateTable> представляет набор шаблонов URI и выбирает самый подходящий заданный набор шаблонов и потенциальный URI. Это не связано с каким-либо конкретным сетевым стеком (включенным в WCF), поэтому его можно использовать везде, где это необходимо.  
  
 Для связывания операций службы с набором URI, который описывается шаблоном <xref:System.UriTemplate>, модель службы WCF использует шаблон <xref:System.UriTemplateTable> и таблицу шаблонов <xref:System.UriTemplate>. Операция службы связывается с шаблоном <xref:System.UriTemplate> с помощью атрибута <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>. Дополнительные сведения о <xref:System.UriTemplate> и <xref:System.UriTemplateTable>см. в разделе [UriTemplate и UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md) .  
  
## <a name="webget-and-webinvoke-attributes"></a>Атрибуты WebGet и WebInvoke  
 Службы WCF WEB HTTP используют команды извлечения (например, HTTP GET) в дополнение к различным командам вызова (например, HTTP POST, WHERE и DELETE). Модель программирования WCF WEB HTTP позволяет разработчикам служб управлять шаблоном и командой URI, связанными с операциями службы, с помощью <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute>. Атрибуты <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute> позволяют управлять привязкой отдельных операций к URI и методам HTTP, связанным с этими URI. Например, добавление атрибутов <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute> продемонстрировано в следующем примере кода.  
  
```csharp
[ServiceContract]  
interface ICustomer  
{  
  //"View It"  
  
  [WebGet]  
  Customer GetCustomer():  
  
  //"Do It"  
    [WebInvoke]  
  Customer UpdateCustomerName( string id,   
                               string newName );  
}  
```  
  
 Предыдущий код позволяет создавать следующие HTTP-запросы.  
  
 `GET /GetCustomer`  
  
 `POST /UpdateCustomerName`  
  
 Атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> по умолчанию имеет значение POST, но его можно использовать и для других команд.  
  
```csharp
[ServiceContract]  
interface ICustomer  
{  
  //"View It" -> HTTP GET  
    [WebGet( UriTemplate="customers/{id}" )]  
  Customer GetCustomer( string id ):  
  
  //"Do It" -> HTTP PUT  
  [WebInvoke( UriTemplate="customers/{id}", Method="PUT" )]  
  Customer UpdateCustomer( string id, Customer newCustomer );  
}  
```  
  
 Полный пример службы WCF, использующей модель программирования WCF WEB HTTP, см. в разделе [как создать базовую веб-службу HTTP WCF](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
  
## <a name="uritemplate-query-string-parameters-and-urls"></a>Параметры строки запроса UriTemplate и URL-адреса  
 Веб-службы можно вызвать из веб-браузера, введя URL-адрес, связанный с операцией службы. Эти операции службы могут принимать параметры строки запроса, которые необходимо указывать в URL-адресе в строковом формате. В таблице ниже представлены типы, которые могут передаваться внутри URL-адреса и используемого формата.  
  
|Тип|Формат|  
|----------|------------|  
|<xref:System.Byte>|0 - 255|  
|<xref:System.SByte>|-128 - 127|  
|<xref:System.Int16>|-32768 - 32767|  
|<xref:System.Int32>|-2,147,483,648 - 2,147,483,647|  
|<xref:System.Int64>|-9,223,372,036,854,775,808 - 9,223,372,036,854,775,807|  
|<xref:System.UInt16>|0 - 65535|  
|<xref:System.UInt32>|0 - 4,294,967,295|  
|<xref:System.UInt64>|0 - 18,446,744,073,709,551,615|  
|<xref:System.Single>|-3.402823e38–3.402823e38 (экспоненциальная запись не требуется)|  
|<xref:System.Double>|-1.79769313486232e308–1.79769313486232e308 (экспоненциальная запись не требуется)|  
|<xref:System.Char>|Любой отдельный знак|  
|<xref:System.Decimal>|Любое десятичное число в стандартной записи (без экспоненты)|  
|<xref:System.Boolean>|True или False (с учетом регистра)|  
|<xref:System.String>|Любая строка (пустая строка не поддерживается, преобразование не производится)|  
|<xref:System.DateTime>|ММ/ДД/ГГГГ<br /><br /> ММ/дд/гггг чч: мм: СС [AM&#124;PM]<br /><br /> Месяц, день, год<br /><br /> Месяц, год, чч: мм: СС [&#124;AM]|  
|<xref:System.TimeSpan>|ДД.ЧЧ:ММ:СС,<br /><br /> где ДД = дни, ЧЧ = часы, ММ = минуты, СС = секунды.|  
|<xref:System.Guid>|Например, идентификатор GUID:<br /><br /> 936DA01F-9ABD-4d9d-80C7-02AF85C822A8|  
|<xref:System.DateTimeOffset>|ММ/ДД/ГГГГ ЧЧ:ММ:СС ММ:СС,<br /><br /> где ДД = дни, ЧЧ = часы, ММ = минуты, СС = секунды.|  
|Перечисления|Значение перечисления, которое, например, определяет перечисление, как показано в следующем примере кода.<br /><br /> `public enum Days{ Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };`<br /><br /> В строке запроса можно указать любое отдельное значение перечисления (или соответствующее ему целочисленное значение).|  
|Типы, содержащие `TypeConverterAttribute`, который может преобразовать типы в строковое представление и обратно.|Зависит от преобразователя типов.|  
  
## <a name="formats-and-the-wcf-web-http-programming-model"></a>Форматы и модель программирования WCF WEB HTTP  
 Модель программирования WCF WEB HTTP обладает новыми возможностями для работы с различными форматами данных. На уровне привязки <xref:System.ServiceModel.WebHttpBinding> может считывать и записывать следующие различные типы данных.  
  
- XML  
  
- JSON  
  
- Непрозрачные двоичные потоки  
  
 Это означает, что модель программирования WCF WEB HTTP может обрабатывать данные любого типа, но вы можете программировать на <xref:System.IO.Stream>.  
  
 .NET Framework 3,5 обеспечивает поддержку данных JSON (AJAX), а также каналов синдикации (включая ATOM и RSS). Дополнительные сведения об этих возможностях см. в статье [Интернет-форматирование веб-протокола HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)[: обзор синдикации](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md) и [Интеграция с AJAX и поддержка JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md).  
  
## <a name="wcf-web-http-programming-model-and-security"></a>Модель программирования WCF WEB HTTP и безопасность  

Так как модель программирования WCF WEB HTTP не поддерживает протоколы WS-*, единственным способом защиты веб-службы HTTP WCF является предоставление службы по протоколу HTTPS с помощью SSL. Дополнительные сведения о настройке SSL с помощью IIS 7,0 см. в статье [Реализация SSL в IIS](https://support.microsoft.com/help/299875/how-to-implement-ssl-in-iis).
  
## <a name="troubleshooting-the-wcf-web-http-programming-model"></a>Устранение неполадок в модели программирования WCF WEB HTTP  
 Когда службы WCF WEB HTTP вызываются с помощью <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> для создания канала, <xref:System.ServiceModel.Description.WebHttpBehavior> использует адрес <xref:System.ServiceModel.EndpointAddress>, заданный в файле конфигурации, даже в случае, когда в <xref:System.ServiceModel.EndpointAddress> передается другой <xref:System.ServiceModel.Channels.ChannelFactoryBase%601>.  
  
## <a name="see-also"></a>См. также:

- [Синдикация WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
- [Объектная модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
