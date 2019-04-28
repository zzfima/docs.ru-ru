---
title: Создание служб WCF AJAX без использования ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: 77a850408c3d952dbd4f682ea704d3248ae17c3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857211"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="b71fb-102">Создание служб WCF AJAX без использования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b71fb-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="b71fb-103">Службы AJAX Windows Communication Foundation (WCF) может осуществляться из любой JavaScript с поддержкой веб-страницы без использования ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="b71fb-103">Windows Communication Foundation (WCF) AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="b71fb-104">В этом разделе описывается создание службы WCF.</span><span class="sxs-lookup"><span data-stu-id="b71fb-104">This topic describes how to create such a WCF service.</span></span>  
  
 <span data-ttu-id="b71fb-105">Инструкции по использованию WCF с ASP.NET AJAX см. в разделе [создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span><span class="sxs-lookup"><span data-stu-id="b71fb-105">For instructions on using WCF with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="b71fb-106">Существует три части для создания службы WCF AJAX:</span><span class="sxs-lookup"><span data-stu-id="b71fb-106">There are three parts to a creating a WCF AJAX service:</span></span>  
  
- <span data-ttu-id="b71fb-107">Создание конечной точки AJAX, доступ к которой можно получить из браузера.</span><span class="sxs-lookup"><span data-stu-id="b71fb-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
- <span data-ttu-id="b71fb-108">Создание контракта службы, совместимого с технологией AJAX.</span><span class="sxs-lookup"><span data-stu-id="b71fb-108">Creating an AJAX-compatible service contract.</span></span>  
  
- <span data-ttu-id="b71fb-109">Доступ к службам AJAX WCF.</span><span class="sxs-lookup"><span data-stu-id="b71fb-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="b71fb-110">Создание конечной точки AJAX</span><span class="sxs-lookup"><span data-stu-id="b71fb-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="b71fb-111">Самый простой способ включения поддержки AJAX в службе WCF является использование <xref:System.ServiceModel.Activation.WebServiceHostFactory> в файле .svc, связанном со службой, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b71fb-111">The most basic way to enable AJAX support in a WCF service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="b71fb-112">Также для добавления конечной точки AJAX можно использовать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b71fb-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="b71fb-113">Используйте <xref:System.ServiceModel.WebHttpBinding> в конечной точке службы и настройте эту конечную точку с помощью <xref:System.ServiceModel.Description.WebHttpBehavior>, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="b71fb-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="b71fb-114">Рабочий пример см. в разделе [служба AJAX с JSON и XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b71fb-114">For a working example, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="b71fb-115">Создание контракта службы, совместимого с технологией AJAX</span><span class="sxs-lookup"><span data-stu-id="b71fb-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="b71fb-116">По умолчанию контракты служб, предоставляемые через конечную точку AJAX, возвращают данные в формате XML.</span><span class="sxs-lookup"><span data-stu-id="b71fb-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="b71fb-117">Кроме того, по умолчанию доступ к операциям службы предоставляется через HTTP-запросы POST, поступающие в URL-адреса, содержащие адрес конечной точки, после которого следует имя операции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b71fb-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="b71fb-118">Эта операция доступна с помощью HTTP POST для `http://serviceaddress/endpointaddress/GetCities` и возвращается сообщение XML.</span><span class="sxs-lookup"><span data-stu-id="b71fb-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="b71fb-119">Можно использовать полную модель веб-программирования, чтобы настроить эти основные аспекты.</span><span class="sxs-lookup"><span data-stu-id="b71fb-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="b71fb-120">Например, можно использовать атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> для управления HTTP-командой, на которую отвечает операция, или использовать свойство `UriTemplate` этих соответствующих атрибутов для указания пользовательских универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="b71fb-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> <span data-ttu-id="b71fb-121">Дополнительные сведения см. в разделе [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="b71fb-121">For more information, see the [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="b71fb-122">В службах AJAX часто используется формат данных JSON.</span><span class="sxs-lookup"><span data-stu-id="b71fb-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="b71fb-123">Чтобы создать операцию, возвращающую JSON вместо XML, присвойте свойству <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (или свойству <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) значение <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="b71fb-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="b71fb-124">[Автономной сериализации JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) разделе показано, как встроенные .NET типов и данных контракта сопоставления типов в формат JSON.</span><span class="sxs-lookup"><span data-stu-id="b71fb-124">The [Stand-Alone JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="b71fb-125">Обычно запросы и ответы JSON состоят из одного элемента.</span><span class="sxs-lookup"><span data-stu-id="b71fb-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="b71fb-126">Для предыдущей операции `GetCities` запрос выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b71fb-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```  
"na"  
```  
  
 <span data-ttu-id="b71fb-127">Ответ на этот запрос выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b71fb-127">The response to that request resembles the following statement.</span></span>  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="b71fb-128">Если операция принимает дополнительный параметр, стиль запроса необходимо поместить в оболочку, чтобы заключить в оболочку оба параметра в одном объекте JSON.</span><span class="sxs-lookup"><span data-stu-id="b71fb-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="b71fb-129">Ниже приводится пример такого стиля сообщения JSON.</span><span class="sxs-lookup"><span data-stu-id="b71fb-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="b71fb-130">Следующий контракт принимает это сообщение.</span><span class="sxs-lookup"><span data-stu-id="b71fb-130">The following contract accepts this message.</span></span>  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="b71fb-131">Доступ к службам AJAX</span><span class="sxs-lookup"><span data-stu-id="b71fb-131">Accessing AJAX Services</span></span>  
 <span data-ttu-id="b71fb-132">Конечные точки WCF AJAX всегда принимать запросы JSON и XML.</span><span class="sxs-lookup"><span data-stu-id="b71fb-132">WCF AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="b71fb-133">HTTP-запросы POST с типом содержимого «application/JSON» обрабатываются как JSON, а с типом содержимого, указывающим на XML (например, «text/xml»), рассматриваются как XML.</span><span class="sxs-lookup"><span data-stu-id="b71fb-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="b71fb-134">HTTP-запросы GET содержат все параметры запросов в самом URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="b71fb-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="b71fb-135">Пользователь определяет, как создавать HTTP-запрос в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="b71fb-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="b71fb-136">Кроме того, пользователь имеет полный контроль над созданием JSON, формирующим тело запроса.</span><span class="sxs-lookup"><span data-stu-id="b71fb-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="b71fb-137">Пример создания запроса из JavaScript, см. в разделе [служба AJAX с JSON и XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b71fb-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>
