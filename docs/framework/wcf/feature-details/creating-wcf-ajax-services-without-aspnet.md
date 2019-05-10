---
title: Создание служб WCF AJAX без использования ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: de7e5dc075a821518928514be532ea1940c1ff17
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627122"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Создание служб WCF AJAX без использования ASP.NET
Службы AJAX Windows Communication Foundation (WCF) может осуществляться из любой JavaScript с поддержкой веб-страницы без использования ASP.NET AJAX. В этом разделе описывается создание службы WCF.  
  
 Инструкции по использованию WCF с ASP.NET AJAX см. в разделе [создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Существует три части для создания службы WCF AJAX:  
  
- Создание конечной точки AJAX, доступ к которой можно получить из браузера.  
  
- Создание контракта службы, совместимого с технологией AJAX.  
  
- Доступ к службам AJAX WCF.  
  
## <a name="creating-an-ajax-endpoint"></a>Создание конечной точки AJAX  
 Самый простой способ включения поддержки AJAX в службе WCF является использование <xref:System.ServiceModel.Activation.WebServiceHostFactory> в файле .svc, связанном со службой, как показано в следующем примере.  
  
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
  
 Рабочий пример см. в разделе [служба AJAX с JSON и XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Создание контракта службы, совместимого с технологией AJAX  
 По умолчанию контракты служб, предоставляемые через конечную точку AJAX, возвращают данные в формате XML. Кроме того, по умолчанию доступ к операциям службы предоставляется через HTTP-запросы POST, поступающие в URL-адреса, содержащие адрес конечной точки, после которого следует имя операции, как показано в следующем примере.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Эта операция доступна с помощью HTTP POST для `http://serviceaddress/endpointaddress/GetCities` и возвращается сообщение XML.  
  
 Можно использовать полную модель веб-программирования, чтобы настроить эти основные аспекты. Например, можно использовать атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> для управления HTTP-командой, на которую отвечает операция, или использовать свойство `UriTemplate` этих соответствующих атрибутов для указания пользовательских универсальных кодов ресурсов (URI). Дополнительные сведения см. в разделе [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) раздела.  
  
 В службах AJAX часто используется формат данных JSON. Чтобы создать операцию, возвращающую JSON вместо XML, присвойте свойству <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (или свойству <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) значение <xref:System.ServiceModel.Web.WebMessageFormat.Json>. [Автономной сериализации JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) разделе показано, как встроенные .NET типов и данных контракта сопоставления типов в формат JSON.  
  
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
 Конечные точки WCF AJAX всегда принимать запросы JSON и XML.  
  
 HTTP-запросы POST с типом содержимого «application/JSON» обрабатываются как JSON, а с типом содержимого, указывающим на XML (например, «text/xml»), рассматриваются как XML.  
  
 HTTP-запросы GET содержат все параметры запросов в самом URL-адресе.  
  
 Пользователь определяет, как создавать HTTP-запрос в конечную точку. Кроме того, пользователь имеет полный контроль над созданием JSON, формирующим тело запроса. Пример создания запроса из JavaScript, см. в разделе [служба AJAX с JSON и XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).
