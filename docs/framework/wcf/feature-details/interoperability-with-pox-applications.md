---
title: "Взаимодействие с приложениями POX"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6dbdd72dce196ea58550cff956a7b0e6fe0b1a73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="a685f-102">Взаимодействие с приложениями POX</span><span class="sxs-lookup"><span data-stu-id="a685f-102">Interoperability with POX Applications</span></span>
<span data-ttu-id="a685f-103">«Plain Old XML» (POX) приложениям взаимодействовать, обмениваясь необработанные сообщения HTTP, которые содержат только XML-приложения данные, не заключенные в конверт SOAP.</span><span class="sxs-lookup"><span data-stu-id="a685f-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a685f-104"> может предоставлять как службы, так и клиенты, использующие сообщения POX.</span><span class="sxs-lookup"><span data-stu-id="a685f-104"> can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="a685f-105">В случае службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может использоваться для реализации служб, предоставляющих конечные точки таким клиентам, как веб-браузеры и языки сценариев, которые передают и принимают сообщения POX.</span><span class="sxs-lookup"><span data-stu-id="a685f-105">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="a685f-106">В случае клиента модель программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может использоваться для реализации клиентов, взаимодействующих со службами, основанными на POX.</span><span class="sxs-lookup"><span data-stu-id="a685f-106">On the client, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a685f-107">Данный документ первоначально был написан для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="a685f-107">This document was originally written for the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span></span>  <span data-ttu-id="a685f-108">В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.5 имеется встроенная поддержка приложений POX.</span><span class="sxs-lookup"><span data-stu-id="a685f-108">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.5 has built-in support for working with POX applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a685f-109">в разделе [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)</span><span class="sxs-lookup"><span data-stu-id="a685f-109"> see [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)</span></span>  
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="a685f-110">Программирование POX с использованием WCF</span><span class="sxs-lookup"><span data-stu-id="a685f-110">POX Programming with WCF</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a685f-111">службы, которые обмениваются данными по протоколу HTTP с помощью сообщений POX, используйте [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="a685f-111"> services that communicate over HTTP using POX messages use a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
```xml  
<customBinding>  
   <binding name="poxServerBinding">  
       <textMessageEncoding messageVersion="None" />  
       <httpTransport />  
   </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="a685f-112">Эта пользовательская привязка содержит два элемента:</span><span class="sxs-lookup"><span data-stu-id="a685f-112">This custom binding contains two elements:</span></span>  
  
-   <span data-ttu-id="a685f-113">[ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) и</span><span class="sxs-lookup"><span data-stu-id="a685f-113">The [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) and</span></span>  
  
-   <span data-ttu-id="a685f-114">[ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="a685f-114">The [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
 <span data-ttu-id="a685f-115">Стандартный кодировщик текстовых сообщений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] специально настроен для использования значения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>, которое позволяет обрабатывать полезную нагрузку сообщений XML, поступающую не внутри конвертов SOAP.</span><span class="sxs-lookup"><span data-stu-id="a685f-115">The standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>  
  
 <span data-ttu-id="a685f-116">Клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], взаимодействующие по протоколу HTTP с помощью сообщений POX, используют аналогичную привязку (показанную в приведенном ниже императивном коде).</span><span class="sxs-lookup"><span data-stu-id="a685f-116">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>  
  
```  
private static Binding CreatePoxBinding()  
{  
    TextMessageEncodingBindingElement encoder =   
    new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );  
    HttpTransportBindingElement transport = new HttpTransportBindingElement();  
    transport.ManualAddressing = true;  
    return new CustomBinding( new BindingElement[] { encoder, transport } );  
}   
```  
  
 <span data-ttu-id="a685f-117">Так как клиенты POX должны явно задавать универсальные коды ресурса (URI), которым они отправляют сообщения, им обычно требуется настроить для элемента <xref:System.ServiceModel.Channels.HttpTransportBindingElement> режим ручной адресации, задав в этом элементе для свойства <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a685f-117">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="a685f-118">Это обеспечивает явную адресацию сообщений в коде приложения, исключая необходимость создавать новую фабрику <xref:System.ServiceModel.ChannelFactory> каждый раз, когда приложение передает сообщение другому универсальному коду ресурса (URI) протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="a685f-118">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>  
  
 <span data-ttu-id="a685f-119">Так как сообщения POX не используют заголовки SOAP для передачи важной информации о протоколе, клиенты и службы POX часто должны обрабатывать части базового запроса HTTP, использованного для отправки или приема сообщения.</span><span class="sxs-lookup"><span data-stu-id="a685f-119">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="a685f-120">Специфичная для HTTP информация о протоколе, такая как заголовки HTTP и коды состояния, отображается в модели программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью двух классов.</span><span class="sxs-lookup"><span data-stu-id="a685f-120">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model through two classes:</span></span>  
  
-   <span data-ttu-id="a685f-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, содержащий информацию о запросе HTTP, такую как метод HTTP и заголовки запроса.</span><span class="sxs-lookup"><span data-stu-id="a685f-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>  
  
-   <span data-ttu-id="a685f-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, содержащий информацию об ответе HTTP, такую как код состояния и описание состояния HTTP, а также все заголовки ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="a685f-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>  
  
 <span data-ttu-id="a685f-123">В следующем примере кода показано, как создать сообщения запроса HTTP GET, направляемое по адресу http://localhost:8100/customers.</span><span class="sxs-lookup"><span data-stu-id="a685f-123">The following code example shows how to create an HTTP GET request message that is addressed to http://localhost:8100/customers.</span></span>  
  
```  
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );  
request.Headers.To = "http://localhost:8100/customers";  
  
HttpRequestMessageProperty property = new HttpRequestMessageProperty();  
property.Method = "GET";  
property.SuppressEntityBody = true;  
request.Properties.Add( HttpRequestMessageProperty.Name, property );  
```  
  
 <span data-ttu-id="a685f-124">Сначала создается пустой запрос <xref:System.ServiceModel.Channels.Message> путем вызова метода <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="a685f-124">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="a685f-125">Параметр <xref:System.ServiceModel.Channels.MessageVersion.None%2A> используется для указания того, что конверт SOAP не требуется, а параметр <xref:System.String.Empty> передается как действие.</span><span class="sxs-lookup"><span data-stu-id="a685f-125">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="a685f-126">Затем сообщение запроса адресуется путем задания в заголовке <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> требуемого универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="a685f-126">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="a685f-127">Далее создается <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, для параметра <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> задается HTTP-команда GET, а для параметра <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> задается значение `true`, указывающее, что в теле исходящего сообщения запроса HTTP не должны передаваться никакие данные.</span><span class="sxs-lookup"><span data-stu-id="a685f-127">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="a685f-128">Наконец, в коллекцию <xref:System.ServiceModel.Channels.Message.Properties%2A> сообщения запроса добавляется свойство запроса, чтобы можно было влиять на способ передачи запроса транспортом HTTP.</span><span class="sxs-lookup"><span data-stu-id="a685f-128">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="a685f-129">После этого сообщение готово к отправке через соответствующий экземпляр класса <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="a685f-129">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>  
  
 <span data-ttu-id="a685f-130">Аналогичные приемы могут использоваться в службе для извлечения свойства <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> из входящего сообщения и построения ответа.</span><span class="sxs-lookup"><span data-stu-id="a685f-130">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>
