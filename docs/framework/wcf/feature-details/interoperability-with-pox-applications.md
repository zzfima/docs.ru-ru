---
title: Взаимодействие с приложениями POX
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: b7fdb4e16bce52025515ced065d0f48cffb7fa3f
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778014"
---
# <a name="interoperability-with-pox-applications"></a>Взаимодействие с приложениями POX

«Plain Old XML» (POX) приложения взаимодействуют путем обмена необработанными сообщениями HTTP, которые содержат только данные приложения XML, не заключенные в конверт SOAP. Windows Communication Foundation (WCF) может предоставить службы и клиенты, использующие сообщения POX. В службе WCF можно использовать для реализации служб, предоставляющих конечные точки для клиентов, таких как веб-браузеры и языки сценариев, которые отправляют и принимают сообщения POX. На стороне клиента можно использовать модель программирования WCF для реализации клиентов, взаимодействующих со службами, основанными на POX.  
  
> [!NOTE]
> Данный документ первоначально был написан для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.  В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.5 имеется встроенная поддержка приложений POX. Дополнительные сведения см. в разделе [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).
  
## <a name="pox-programming-with-wcf"></a>Программирование POX с использованием WCF

Службы WCF, взаимодействующих по протоколу HTTP с помощью сообщений POX, используется [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

Эта пользовательская привязка содержит два элемента:

- [\<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

- [\<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)

Стандартный кодировщик текстовых сообщений WCF специально настроен для использования <xref:System.ServiceModel.Channels.MessageVersion.None%2A> значение, которое позволяет обрабатывать XML полезных данных сообщений, которые не поступят в конверт SOAP.

Клиенты WCF, взаимодействующих по протоколу HTTP с помощью сообщений POX, используют аналогичную привязку (показано в приведенном ниже императивном коде).

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

Так как клиенты POX должны явно задавать универсальные коды ресурса (URI), которым они отправляют сообщения, им обычно требуется настроить для элемента <xref:System.ServiceModel.Channels.HttpTransportBindingElement> режим ручной адресации, задав в этом элементе для свойства <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> значение `true`. Это обеспечивает явную адресацию сообщений в коде приложения, исключая необходимость создавать новую фабрику <xref:System.ServiceModel.ChannelFactory> каждый раз, когда приложение передает сообщение другому универсальному коду ресурса (URI) протокола HTTP.

Так как сообщения POX не используют заголовки SOAP для передачи важной информации о протоколе, клиенты и службы POX часто должны обрабатывать части базового запроса HTTP, использованного для отправки или приема сообщения. Сведения о протоколе относящимся с HTTP, такие как заголовки HTTP и коды состояния регистрируются в модели программирования WCF через два класса:

- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, содержащий информацию о запросе HTTP, такую как метод HTTP и заголовки запроса.

- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, содержащий информацию об ответе HTTP, такую как код состояния и описание состояния HTTP, а также все заголовки ответа HTTP.
  
В следующем примере кода показано, как создать сообщение запроса HTTP GET, адресованного `http://localhost:8100/customers`.

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

Сначала создается пустой запрос <xref:System.ServiceModel.Channels.Message> путем вызова метода <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>. Параметр <xref:System.ServiceModel.Channels.MessageVersion.None%2A> используется для указания того, что конверт SOAP не требуется, а параметр <xref:System.String.Empty> передается как действие. Затем сообщение запроса адресуется путем задания в заголовке <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> требуемого универсального кода ресурса (URI). Далее создается <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, для параметра <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> задается HTTP-команда GET, а для параметра <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> задается значение `true`, указывающее, что в теле исходящего сообщения запроса HTTP не должны передаваться никакие данные. Наконец, в коллекцию <xref:System.ServiceModel.Channels.Message.Properties%2A> сообщения запроса добавляется свойство запроса, чтобы можно было влиять на способ передачи запроса транспортом HTTP. После этого сообщение готово к отправке через соответствующий экземпляр класса <xref:System.ServiceModel.Channels.IRequestChannel>.

Аналогичные приемы могут использоваться в службе для извлечения свойства <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> из входящего сообщения и построения ответа.
