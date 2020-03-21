---
title: Пример автономного веб-канала диагностики
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 29d8caee48925040db9f1812f015870e3a1272bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144010"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Пример автономного веб-канала диагностики
В этом примере показано, как создать канал RSS/Atom для синдикации с Фондом связи Windows (WCF). Это основная программа "Hello World", которая показывает основы модели объекта и как настроить ее на службу Windows Communication Foundation (WCF).  
  
 WCF моделирует синдикации каналов в качестве <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>сервисных операций, которые возвращают специальный тип данных, . Экземпляры <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> могут сериализовать веб-канал в форматы RSS 2.0 и Atom 1.0. В следующем примере кода показан использованный контракт.  
  
```csharp  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 Операция `GetProcesses` аннотирована атрибутом, <xref:System.ServiceModel.Web.WebGetAttribute> который позволяет контролировать, как WCF отправляет запросы HTTP GET на обслуживание операций и указать формат отправленных сообщений.  
  
 Как и любая служба WCF, каналы синдикации могут быть самостоятельно размещены в любом управляемом приложении. Для правильной работы служб синдикации требуются особая привязка (<xref:System.ServiceModel.WebHttpBinding>) и специальное поведение конечной точки (<xref:System.ServiceModel.Description.WebHttpBehavior>). Новый класс <xref:System.ServiceModel.Web.WebServiceHost> обеспечивает удобный программный интерфейс для создания таких конечных точек без особой конфигурации.  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 В качестве альтернативного варианта можно использовать <xref:System.ServiceModel.Activation.WebServiceHostFactory> из размещенного в службах IIS файла SVC, чтобы обеспечить аналогичную функциональность (этот метод не показан в примере коде).  
  
```xml
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>
```
  
 Поскольку эта служба получает запросы с использованием стандартного метода HTTP GET, для доступа к службе можно использовать любой клиент, поддерживающий RSS или ATOM. Например, вы можете просмотреть выход этой службы, перемещаясь в браузер RSS-информацию `http://localhost:8000/diagnostics/feed/?format=atom` или `http://localhost:8000/diagnostics/feed/?format=rss` в нее.
  
 Вы также можете использовать [как WCF Синдикации объект модели карты для atom и RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) для чтения синдицированных данных и обработки его с помощью императивного кода.  
  
```csharp
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",
    new XmlReaderSettings()
    {
        //MaxCharactersInDocument can be used to control the maximum amount of data
        //read from the reader and helps prevent OutOfMemoryException
        MaxCharactersInDocument = 1024 * 64
    } );

SyndicationFeed feed = SyndicationFeed.Load(reader);

foreach (SyndicationItem i in feed.Items)
{
    XmlSyndicationContent content = i.Content as XmlSyndicationContent;
    ProcessData pd = content.ReadContent<ProcessData>();

    Console.WriteLine(i.Title.Text);
    Console.WriteLine(pd.ToString());
}
```
  
## <a name="set-up-build-and-run-the-sample"></a>Настройка, создание и запуск образца
  
1. Убедитесь, что у вас есть правильное разрешение на регистрацию адреса для HTTP и HTTPS на компьютере, как это объясняется в инструкциях в [одноразовой настройке процедуры для образцов Фонда связи Windows.](one-time-setup-procedure-for-the-wcf-samples.md)

2. Создайте решение.

3. Запустите консольное приложение.

4. Во время работы консольного приложения перейдите к `http://localhost:8000/diagnostics/feed/?format=atom` браузеру, известному rsS, или `http://localhost:8000/diagnostics/feed/?format=rss` с помощью.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`

## <a name="see-also"></a>См. также раздел

- [Модель веб-программирования HTTP WCF](../feature-details/wcf-web-http-programming-model.md)
- [Синдикация WCF](../feature-details/wcf-syndication.md)
