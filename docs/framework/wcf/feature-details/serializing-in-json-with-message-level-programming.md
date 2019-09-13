---
title: Сериализация в Json с помощью программирования на уровне сообщений
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: f50f6a699dff54e3d0950f5ce0e1049217b9dc45
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928730"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Сериализация в Json с помощью программирования на уровне сообщений
WCF поддерживает сериализацию данных в формате JSON. В этом разделе описывается, как в WCF выполнить сериализацию типов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Программирование типизированных сообщений  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используется, когда к операции службы применяется атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>. Оба атрибута позволяют задать формат запроса `RequestFormat` и формат ответа `ResponseFormat`. Для использования JSON в запросах и ответах. Задайте для `WebMessageFormat.Json`обоих свойств значение.  Чтобы использовать JSON, необходимо использовать <xref:System.ServiceModel.WebHttpBinding>, который автоматически настраивает. <xref:System.ServiceModel.Description.WebHttpBehavior> Дополнительные сведения о сериализации WCF см. в разделе [сериализация и десериализация](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Дополнительные сведения о JSON и WCF см. в разделе [служебная станция — введение в службы RESTful с помощью WCF](https://msdn.microsoft.com/magazine/dd315413.aspx).  
  
> [!IMPORTANT]
> Для использования с JSON требуется привязка <xref:System.ServiceModel.WebHttpBinding> и поведение <xref:System.ServiceModel.Description.WebHttpBehavior>, которые не поддерживают связь по протоколу SOAP. Службы, взаимодействующие <xref:System.ServiceModel.WebHttpBinding> с, не поддерживают предоставление метаданных службы, поэтому вы не сможете использовать функциональные возможности Visual Studio Добавление ссылки на службу или программу командной строки Svcutil для создания прокси на стороне клиента. Дополнительные сведения о программном вызове служб, использующих <xref:System.ServiceModel.WebHttpBinding>, см. в разделе Использование [служб RESTful с WCF](https://blogs.msdn.microsoft.com/pedram/2008/04/21/how-to-consume-rest-services-with-wcf/).  
  
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
