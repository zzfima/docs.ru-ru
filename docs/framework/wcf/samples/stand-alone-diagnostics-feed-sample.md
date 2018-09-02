---
title: Пример автономного веб-канала диагностики
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 64222297373f194a33b5520ecd71b0acc7755359
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418301"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Пример автономного веб-канала диагностики
В этом образце демонстрируется создание RSS/Atom-канал синдикации с помощью Windows Communication Foundation (WCF). Это простая программа «Hello, World!», которая показывает, с основами объектной модели и как настроить проверку подлинности в службе Windows Communication Foundation (WCF).  
  
 WCF моделирует веб-каналы синдикации как операции службы, возвращающие особый тип данных, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Экземпляры <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> могут сериализовать веб-канал в форматы RSS 2.0 и Atom 1.0. В следующем примере кода показан использованный контракт.  
  
```  
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
  
 `GetProcesses` Операции помечается с помощью <xref:System.ServiceModel.Web.WebGetAttribute> запрашивает атрибут, который позволяет управлять тем, как WCF отправляет HTTP GET к операции службы и указать формат отправляемых сообщений.  
  
 Как и любая служба WCF веб-каналы синдикации могут быть резидентными в любом управляемом приложении. Для правильной работы служб синдикации требуются особая привязка (<xref:System.ServiceModel.WebHttpBinding>) и специальное поведение конечной точки (<xref:System.ServiceModel.Description.WebHttpBehavior>). Новый класс <xref:System.ServiceModel.Web.WebServiceHost> обеспечивает удобный программный интерфейс для создания таких конечных точек без особой конфигурации.  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 В качестве альтернативного варианта можно использовать <xref:System.ServiceModel.Activation.WebServiceHostFactory> из размещенного в службах IIS файла SVC, чтобы обеспечить аналогичную функциональность (этот метод не показан в примере коде).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 Поскольку эта служба получает запросы с использованием стандартного метода HTTP GET, для доступа к службе можно использовать любой клиент, поддерживающий RSS или ATOM. Например, можно просмотреть выходные данные этой службы, перейдя по адресу http://localhost:8000/diagnostics/feed/?format=atom или http://localhost:8000/diagnostics/feed/?format=rss в это поддержкой RSS браузер как Internet Explorer 7.  
  
 Можно также использовать [как WCF синдикации объект модели сопоставляется с Atom и RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) чтения сводных данных и обработайте их с помощью императивного кода.  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что правильное разрешение регистрации адреса для HTTP и HTTPS на компьютере, как описано в инструкциям по установке в [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Постройте решение.  
  
3.  Запустите консольное приложение.  
  
4.  Пока выполняется в консольном приложении, перейдите к http://localhost:8000/diagnostics/feed/?format=atom или http://localhost:8000/diagnostics/feed/?format=rss с помощью браузера поддержкой RSS.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>См. также  
 [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Синдикация WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
