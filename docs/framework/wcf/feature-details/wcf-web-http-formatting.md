---
title: ФорматИрование WCF Web HTTP
ms.date: 03/30/2017
ms.assetid: e2414896-5463-41cd-b0a6-026a713eac2c
ms.openlocfilehash: b6c9728fe40e26977366b73337e72b1514a12a19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184200"
---
# <a name="wcf-web-http-formatting"></a>ФорматИрование WCF Web HTTP
Модель веб-программирования HTTP WCF позволяет динамически определять лучший формат возвращаемого ответа операции службы. Поддерживается два метода для определения формата: автоматический и явный.  
  
## <a name="automatic-formatting"></a>Автоматическое форматирование  
 Если выбран этот метод, автоматическое форматирование выбирает наилучший формат возврата ответа. Наилучший формат определяется путем проверки в следующем порядке.  
  
1. Типы носителей в заголовке Accept сообщения запроса.  
  
2. Тип содержимого сообщения запроса.  
  
3. Параметр формата по умолчанию в операции.  
  
4. Параметр формата по умолчанию в WebHttpBehavior.  
  
 Если сообщение запроса содержит заголовок Accept, инфраструктура Windows Communication Foundation (WCF) выполняет поиск типа, который он поддерживает. Если заголовок `Accept` указывает приоритеты типов носителей, то они учитываются. Если в заголовке `Accept` не найден подходящий формат, используется тип содержимого сообщения запроса. Если не указан подходящий тип содержимого, используется параметр формата по умолчанию для операции. Формат по умолчанию задается с помощью параметра `ResponseFormat` атрибутов <xref:System.ServiceModel.Web.WebGetAttribute> и <xref:System.ServiceModel.Web.WebInvokeAttribute>. Если не указан формат по умолчанию для операции, используется значение свойства <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A>. Автоматическое форматирование основано на свойстве <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>. Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования. Автоматический выбор формата отключен по умолчанию в целях обратной совместимости. Автоматический выбор формата можно включить программно или через конфигурацию. В следующем примере показано включение автоматического выбора формата в коде.  
  
```csharp
// This code assumes the service name is MyService and the service contract is IMyContract
Uri baseAddress = new Uri("http://localhost:8000");  
  
WebServiceHost host = new WebServiceHost(typeof(MyService), baseAddress)  
try  
{  
   ServiceEndpoint sep = host.AddServiceEndpoint(typeof(IMyContract), new WebHttpBinding(), "");  
   // Check it see if the WebHttpBehavior already exists  
   WebHttpBehavior whb = sep.Behaviors.Find<WebHttpBehavior>();  
  
   if (whb != null)  
   {  
      whb.AutomaticFormatSelectionEnabled = true;  
   }  
   else  
   {  
      WebHttpBehavior webBehavior = new WebHttpBehavior();  
      webBehavior.AutomaticFormatSelectionEnabled = true;  
      sep.Behaviors.Add(webBehavior);  
   }  
         // Open host to start listening for messages  
   host.Open();
  
  // ...  
}  
  catch(CommunicationException ex)  
  {  
     Console.WriteLine("An exception occurred: " + ex.Message());  
  }  
```  
  
 Автоматический выбор формата также можно включить через конфигурацию. Можно задать свойство <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> напрямую в <xref:System.ServiceModel.Description.WebHttpBehavior> или с помощью <xref:System.ServiceModel.Description.WebHttpEndpoint>. В следующем примере показано включение автоматического выбора формата в <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <endpointBehaviors>  
      <behavior>  
        <webHttp automaticFormatSelectionEnabled="true" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
      <standardEndpoint name="" helpEnabled="true" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 В следующем примере показано включение автоматического выбора формата с помощью <xref:System.ServiceModel.Description.WebHttpEndpoint>.  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
      <webHttpEndpoint>  
        <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
        <standardEndpoint name="" helpEnabled="true" automaticFormatSelectionEnabled="true"  />  
      </webHttpEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```  
  
## <a name="explicit-formatting"></a>Явное форматирование  
 Как следует из названия, в явном форматировании разработчик определяет наилучший формат для использования внутри кода операции. Если лучшим форматом является формат XML или JSON, разработчик устанавливает <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> в формат <xref:System.ServiceModel.Web.WebMessageFormat.Xml> либо <xref:System.ServiceModel.Web.WebMessageFormat.Json>. Если свойство <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> явно не задано, то используется формат операции по умолчанию.  
  
 В следующем примере для определения формата, который нужно использовать, проверяется параметр строки запроса формата. Если этот параметр был указан, формат операции задается свойством <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.  
  
```csharp
public class Service : IService  
{  
    [WebGet]  
     public string EchoWithGet(string s)  
    {  
        // if a format query string parameter has been specified, set the response format to that. If no such
        // query string parameter exists the Accept header will be used
        string formatQueryStringValue = WebOperationContext.Current.IncomingRequest.UriTemplateMatch.QueryParameters["format"];  
        if (!string.IsNullOrEmpty(formatQueryStringValue))  
        {  
            if (formatQueryStringValue.Equals("xml", System.StringComparison.OrdinalIgnoreCase))  
            {
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Xml;
            }
            else if (formatQueryStringValue.Equals("json", System.StringComparison.OrdinalIgnoreCase))  
            {  
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Json;  
            }  
            else  
            {  
                throw new WebFaultException<string>($"Unsupported format '{formatQueryStringValue}'",   HttpStatusCode.BadRequest);
            }  
        }  
        return "You said " + s;  
    }  
```  
  
 Если необходимо поддерживать форматы, отличающиеся от XML или JSON, операцию нужно определить таким образом, чтобы она возвращала тип <xref:System.ServiceModel.Channels.Message>. Внутри кода операции определите соответствующий формат для использования и создайте объект <xref:System.ServiceModel.Channels.Message> с помощью одного из следующих методов:  
  
- `WebOperationContext.CreateAtom10Response`  
  
- `WebOperationContext.CreateJsonResponse`  
  
- `WebOperationContext.CreateStreamResponse`  
  
- `WebOperationContext.CreateTextResponse`  
  
- `WebOperationContext.CreateXmlResponse`  
  
 Каждый из этих методов принимает содержимое и создает сообщение соответствующего формата. Метод `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` можно использовать для получения списка форматов, предпочитаемых клиентом в порядке снижения предпочтения. В следующем примере показано применение `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` для определения используемого формата, а затем используется соответствующий метод создания ответа для создания ответного сообщения.  
  
```csharp
public class Service : IService  
{  
    public Message EchoListWithGet(string list)  
    {  
        List<string> returnList = new List<string>(list.Split(new char[] { ',' }, StringSplitOptions.RemoveEmptyEntries));  
        IList<ContentType> acceptHeaderElements = WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements();  
        for (int x = 0; x < acceptHeaderElements.Count; x++)  
        {  
            string normalizedMediaType = acceptHeaderElements[x].MediaType.ToLowerInvariant();  
            switch (normalizedMediaType)  
            {  
                case "image/jpeg": return CreateJpegResponse(returnList);  
                case "application/xhtml+xml": return CreateXhtmlResponse(returnList);  
                case "application/atom+xml": return CreateAtom10Response(returnList);  
                case "application/xml": return CreateXmlResponse(returnList);  
                case "application/json": return CreateJsonResponse(returnList);  
          }  
    }  
  
    // Default response format is XML  
    return CreateXmlResponse(returnList);  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.UriTemplate>
- <xref:System.UriTemplateMatch>
- [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [UriTemplate и UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)
- [Общие сведения о модели программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
- [Объектная модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
