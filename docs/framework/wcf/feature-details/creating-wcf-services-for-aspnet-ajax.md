---
title: "Создание служб WCF для ASP.NET AJAX | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Создание служб WCF для ASP.NET AJAX
Технология ASP.NET AJAX корпорации Майкрософт позволяет быстро создавать веб\-страницы, содержащие широкий набор средств взаимодействия с пользователем с известными элементами пользовательского интерфейса.Эта технология предоставляет библиотеки клиентских сценариев, включающие не зависящие от веб\-обозревателя технологии ECMAScript \(JavaScript\) и динамического HTML \(DHTML\), и интегрирует их с платформой разработки на базе сервера ASP.NET 2.0.Используя ASP.NET AJAX, можно улучшить взаимодействие веб\-приложений с пользователем и повысить их эффективность.  
  
 Технология ASP.NET AJAX состоит из библиотек клиентских сценариев и серверных компонентов, интегрированных для обеспечения надежной инфраструктуры разработки.Доступ к службе со страницы ASP.NET: если URL\-адрес службы добавляется в элемент управления диспетчера скриптов ASP.NET на странице, операции службы могут вызываться с помощью кода JavaScript, что выглядит абсолютно аналогично обычному вызову функции JavaScript.Дополнительные сведения об использовании веб\-служб в инфраструктуре AJAX см. в разделе [Дополнительные сведения о ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=186475).  
  
 Большинство служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно представить в виде службы, совместимой с технологией ASP.NET AJAX, добавив соответствующую конечную точку ASP.NET AJAX.  
  
 При использовании Visual Studio можно задействовать заранее созданный шаблон для служб WCF с поддержкой AJAX, которые доступны в диалоговом окне **Добавить новый элемент** при работе с веб\-сайтами или веб\-приложениями ASP.NET.  
  
 Если шаблоны Visual Studio не используются, конечную точку ASP.NET AJAX можно создать двумя указанными ниже способами.  
  
-   Создайте конечную точку, используя динамическую активацию основного приложения, не применяя никакой конфигурации.Это основной подход при незнании системы конфигурации WCF.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как добавить конечную точку ASP.NET AJAX без использования конфигурации](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
-   Добавьте конечную точку с поддержкой AJAX в службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], используя конфигурацию.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как использовать конфигурацию для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
 Со службами ASP.NET AJAX можно использовать модель веб\-программирования, описанную в разделе [Общие сведения о модели программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md).В частности:  
  
-   Для выбора команд HTTP GET и HTTP POST можно использовать атрибуты <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute>.При правильном применении это может существенно повысить производительность приложения.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).  
  
-   Для того, чтобы служба возвращала данные XML вместо нотации объектов JavaScript \(JSON\) по умолчанию, можно использовать свойства <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> и <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>.При использовании этой возможности с инфраструктурой ASP.NET AJAX клиент JavaScript будет принимать DOM\-объект XML.  
  
    > [!WARNING]
    >  Для правильной работы необходимо с помощью операции задать тип содержимого text\/xml.В противном случае клиент JavaScript будет принимать строку, содержащую XML вместо DOM\-объекта XML.  
  
     В следующем примере показана операция, возвращающая XML\-данные с типом содержимого, настроенным соответствующим образом.  
  
    ```  
    [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]  
    public XElement GetData()  
    {  
    XElement x;  
    //Get some data here...  
  
    WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";      
    return x;  
    }  
  
    ```  
  
-   Если требуется совместимость с ASP.NET AJAX, никакие другие свойства в атрибутах <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute> изменять нельзя.Можно использовать другие аспекты модели веб\-программирования, пока не нарушены соглашения о вызовах ASP.NET AJAX.  
  
 В более сложных сценариях требуется понимание некоторых дополнительных подробностей поддержки AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   сведения о передаче данных между клиентом страницы AJAX и службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с использованием JavaScript и подробности сопоставления типов платформы .NET Framework с типами JavaScript см. в разделе [Поддержка JSON и других форматов передачи данных](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md);  
  
-   чтобы воспользоваться преимуществами функций ASP.NET, например проверкой подлинности на основе URL\-адреса и доступом к данным сеансов ASP.NET, можно включить режим совместимости с ASP.NET с использованием конфигурации.  
  
 Конечные точки AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно использовать даже без инфраструктуры ASP.NET AJAX.Для этого необходимо понимать архитектуру поддержки технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Обсуждение этой архитектуры см. в разделе [Объектная модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md).Образец кода, демонстрирующий этот подход, приведен в разделе [Служба AJAX с JSON и XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## См. также  
 [Модель веб\-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [Как добавить конечную точку ASP.NET AJAX без использования конфигурации](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)   
 [Как использовать конфигурацию для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)   
 [Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)