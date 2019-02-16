---
title: Сериализация в Json с помощью программирования на уровне сообщений
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 7f4f9a136c3e6261c7e5fca516c42f83c3ea4403
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332914"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Сериализация в Json с помощью программирования на уровне сообщений
WCF поддерживает сериализацию данных в формате JSON. В этом разделе описывается, как в WCF выполнить сериализацию типов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Программирование типизированных сообщений  
 
  <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используется, когда к операции службы применяется атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>. Оба атрибута позволяют задать формат запроса `RequestFormat` и формат ответа `ResponseFormat`. Для использования формата JSON для запросов и ответов установите для обоих атрибутов значение `WebMessageFormat.Json`.  Для применения формата JSON необходимо использовать привязку <xref:System.ServiceModel.WebHttpBinding>, которая автоматически настраивает <xref:System.ServiceModel.Description.WebHttpBehavior>. Дополнительные сведения о сериализации WCF см. в разделе [сериализации и десериализации](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Дополнительные сведения о JSON и WCF см. в разделе [введение в службы RESTfull с WCF](https://msdn.microsoft.com/magazine/dd315413.aspx) и [Создание JSON-совместимых служб WCF в .NET 3.5](https://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx).  
  
> [!IMPORTANT]
>  Для использования с JSON требуется привязка <xref:System.ServiceModel.WebHttpBinding> и поведение <xref:System.ServiceModel.Description.WebHttpBehavior>, которые не поддерживают связь по протоколу SOAP. Службы, взаимодействующие с <xref:System.ServiceModel.WebHttpBinding> не поддерживают предоставление метаданных службы, поэтому вы не сможете использовать функции добавления служебной ссылки Visual Studio или средство командной строки svcutil для создания клиентского прокси. Дополнительные сведения, как возможности программного вызова служб, использующих <xref:System.ServiceModel.WebHttpBinding>, см. в разделе [как использовать службы REST с WCF](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## <a name="untyped-message-programming"></a>Программирование нетипизированных сообщений  
 При работе напрямую с объектами нетипизированного сообщения следует явно задать свойства нетипизированного сообщения для его сериализации в виде JSON. В следующем фрагменте кода показано, как это сделать.  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a>См. также
- [Интеграция с AJAX и поддержка JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [Автономная сериализация JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [Сериализация JSON](../../../../docs/framework/wcf/samples/json-serialization.md)
