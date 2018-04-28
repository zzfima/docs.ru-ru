---
title: Создание служб WCF AJAX без использования ASP.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b652bcd522a8eea81b3d1218fbd054ee0b2caea8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Создание служб WCF AJAX без использования ASP.NET
Доступ к службам AJAX [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно получить с любой веб-страницы, поддерживающей JavaScript, без использования ASP.NET AJAX. В данном разделе описывается, как создать такую службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Инструкции по использованию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [Создание службы WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Создание службы AJAX [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] выполняется за три этапа.  
  
-   Создание конечной точки AJAX, доступ к которой можно получить из браузера.  
  
-   Создание контракта службы, совместимого с технологией AJAX.  
  
-   Доступ к службам AJAX WCF.  
  
## <a name="creating-an-ajax-endpoint"></a>Создание конечной точки AJAX  
 Основным способом включения поддержки AJAX в службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является использование <xref:System.ServiceModel.Activation.WebServiceHostFactory> в файле .svc, связанном со службой, как показано в следующем примере.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 Также для добавления конечной точки AJAX можно использовать конфигурацию. Используйте <xref:System.ServiceModel.WebHttpBinding> в конечной точке службы и настройте эту конечную точку с помощью <xref:System.ServiceModel.Description.WebHttpBehavior>, как показано в следующем фрагменте кода.  
  
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
  
 Рабочий пример см. в разделе [службы AJAX с JSON и XML-](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Создание контракта службы, совместимого с технологией AJAX  
 По умолчанию контракты служб, предоставляемые через конечную точку AJAX, возвращают данные в формате XML. Кроме того, по умолчанию доступ к операциям службы предоставляется через HTTP-запросы POST, поступающие в URL-адреса, содержащие адрес конечной точки, после которого следует имя операции, как показано в следующем примере.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Эта операция доступна при использовании HTTP POST для `http://serviceaddress/endpointaddress/GetCities` и возвращается сообщение XML.  
  
 Можно использовать полную модель веб-программирования, чтобы настроить эти основные аспекты. Например, можно использовать атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> для управления HTTP-командой, на которую отвечает операция, или использовать свойство `UriTemplate` этих соответствующих атрибутов для указания пользовательских универсальных кодов ресурсов (URI). Дополнительные сведения см. в разделе [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) раздела.  
  
 В службах AJAX часто используется формат данных JSON. Чтобы создать операцию, возвращающую JSON вместо XML, присвойте свойству <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (или свойству <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) значение <xref:System.ServiceModel.Web.WebMessageFormat.Json>. [Автономной сериализации JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) разделе показано, как встроенные .NET типы и данные контракт сопоставление типов в JSON.  
  
 Обычно запросы и ответы JSON состоят из одного элемента. Для предыдущей операции `GetCities` запрос выглядит следующим образом.  
  
```  
"na"  
```  
  
 Ответ на этот запрос выглядит следующим образом.  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 Если операция принимает дополнительный параметр, стиль запроса необходимо поместить в оболочку, чтобы заключить в оболочку оба параметра в одном объекте JSON. Ниже приводится пример такого стиля сообщения JSON.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 Следующий контракт принимает это сообщение.  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>Доступ к службам AJAX  
 Конечные точки AJAX [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда принимают как запросы JSON, так и XML-запросы.  
  
 HTTP-запросы POST с content-type «application/json» обрабатываются как JSON и имеющих тип содержимого, указывающим на XML (например, «text/xml»), обрабатываются как XML.  
  
 HTTP-запросы GET содержат все параметры запросов в самом URL-адресе.  
  
 Пользователь определяет, как создавать HTTP-запрос в конечную точку. Кроме того, пользователь имеет полный контроль над созданием JSON, формирующим тело запроса. Пример создания запроса на основе JavaScript см. в разделе [службы AJAX с JSON и XML-](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).
