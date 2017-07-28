---
title: "Сериализация в Json с помощью программирования на уровне сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Сериализация в Json с помощью программирования на уровне сообщений
WCF поддерживает сериализацию данных в формате JSON.В этом разделе описывается, как в WCF выполнить сериализацию типов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## Программирование типизированных сообщений  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используется, когда к операции службы применяется атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>.Оба атрибута позволяют задать формат запроса `RequestFormat` и формат ответа `ResponseFormat`.Для использования формата JSON для запросов и ответов установите для обоих атрибутов значение `WebMessageFormat.Json`.Для применения формата JSON необходимо использовать привязку <xref:System.ServiceModel.WebHttpBinding>, которая автоматически настраивает поведение <xref:System.ServiceModel.Description.WebHttpBehavior>.Дополнительные сведения о сериализации WCF см. в разделе [Сериализация и десериализация](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Сериализация в Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).Дополнительные сведения о JSON и WCF см. в разделе [Введение в RESTfull\-службы в WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Создание служб WCF, использующих формат JSON, в .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx) и [Обзор применения технологии REST в WCF](http://msdn.microsoft.com/netframework/dd547388).  
  
> [!IMPORTANT]
>  Для использования с JSON требуется привязка <xref:System.ServiceModel.WebHttpBinding> и поведение <xref:System.ServiceModel.Description.WebHttpBehavior>, которые не поддерживают связь по протоколу SOAP.В службах, взаимодействующих с поведением <xref:System.ServiceModel.WebHttpBinding>, не поддерживается предоставление метаданных службы, таким образом, для создания клиентского прокси\-объекта вы не сможете использовать функцию Visual Studio «Добавить ссылку на службу» или программу командной строки svcutil.Дополнительные сведения о программном способе вызова служб, использующих привязку <xref:System.ServiceModel.WebHttpBinding>, см. в разделе [Как использовать REST\-службы в WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## Программирование нетипизированных сообщений  
 При работе напрямую с объектами нетипизированного сообщения следует явно задать свойства нетипизированного сообщения для его сериализации в виде JSON.В следующем фрагменте кода показано, как это сделать.  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
  
```  
  
## См. также  
 [Интеграция с AJAX и поддержка JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [Изолированная сериализация JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)   
 [Сериализация JSON](../../../../docs/framework/wcf/samples/json-serialization.md)