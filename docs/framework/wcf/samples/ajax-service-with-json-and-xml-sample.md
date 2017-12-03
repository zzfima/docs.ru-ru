---
title: "Пример службы AJAX с JSON и XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6d60bec8c3b69d9fd094f59b1f4d8c9ec4d8dff
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Пример службы AJAX с JSON и XML
Данный образец демонстрирует использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания служб асинхронных сценариев JavaScript и XML (AJAX), возвращающих нотацию объектов JavaScript (JSON) или XML-данные. К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера. Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца.  
  
 В отличие от других примеров AJAX, в данном примере не используется ASP.NET AJAX и управление <xref:System.Web.UI.ScriptManager>. С помощью дополнительной настройки доступ к службам AJAX [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно получить с любой HTML-страницы посредством JavaScript. В данном разделе показан данный сценарий. Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [примеров AJAX](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
 В данном разделе показано переключение типа отклика операции между JSON и XML. Данная функциональность доступна независимо от того, настроена служба для доступа через клиентскую страницу ASP.NET AJAX или через HTML/JavaScript.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Чтобы разрешить использование клиентов, не являющихся клиентами ASP.NET AJAX, используйте <xref:System.ServiceModel.Activation.WebServiceHostFactory> (а не <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) в SVC-файле. Объект <xref:System.ServiceModel.Activation.WebServiceHostFactory> добавляет стандартную конечную точку <xref:System.ServiceModel.Description.WebHttpEndpoint> в службу. Конечная точка настраивается в пустом адресе, который является относительным для SVC-файла; это означает, что адресом службы является http://localhost/ServiceModelSamples/service.svc без каких-либо дополнительных суффиксов, за исключением имени операции.  
  
```html  
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 Следующий раздел в Web.config может использоваться для дополнительных изменений конфигурации конечной точки. Если дополнительных изменений не требуется, он может быть удален.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name="" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Форматом данных по умолчанию для <xref:System.ServiceModel.Description.WebHttpEndpoint> является XML, во время форматирования данных по умолчанию для <xref:System.ServiceModel.Description.WebScriptEndpoint> является JSON. Дополнительные сведения см. в разделе [создание служб WCF AJAX без использования ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).  
  
 Служба в следующем примере является стандартной службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с двумя операциями. Обе операции требуют использования основного стиля <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> в <xref:System.ServiceModel.Web.WebGetAttribute> или атрибутов <xref:System.ServiceModel.Web.WebInvokeAttribute>, которые относятся к поведению `webHttp` и не влияют на переключение формата данных JSON/XML.  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```  
  
 Формат ответа для операции указан в формате XML, который используется по умолчанию для [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) поведение. Тем не менее, рекомендуется явно указывать формат ответа.  
  
 Другая операция использует атрибут `WebInvokeAttribute` и явно указывает JSON вместо XML для ответа.  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```  
  
 Обратите внимание, что в обоих случаях операции возвращают комплексный тип `MathResult`, являющийся стандартным типом контракта данных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Клиентская веб-страница XmlAjaxClientPage.htm содержит код JavaScript, вызывающий одну из двух предшествующих операций, когда пользователь щелкает **выполнить расчет (возвратить JSON)** или **выполнить расчет (возвратить XML)**  кнопок на странице. Код, вызывающий службу, создает тело JSON и отправляет его с помощью HTTP POST. Запрос создается вручную из JavaScript, в отличие от [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образец и других примеров с помощью ASP.NET AJAX.  
  
```  
// Create HTTP request  
var xmlHttp;  
// Request instantiation code omitted…  
// Result handler code omitted…  
  
// Build the operation URL  
var url = "service.svc/ajaxEndpoint/";  
url = url + operation;  
  
// Build the body of the JSON message  
var body = '{"n1":';  
body = body + document.getElementById("num1").value + ',"n2":';  
body = body + document.getElementById("num2").value + '}';  
  
// Send the HTTP request  
xmlHttp.open("POST", url, true);  
xmlHttp.setRequestHeader("Content-type", "application/json");  
xmlHttp.send(body);  
```  
  
 При ответе службы ответ отображается без какой-либо дополнительной обработки в текстовом поле страницы. Это реализовано с целью демонстрации и дает возможность непосредственно ознакомиться с используемыми форматами данных XML и JSON.  
  
```  
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Постройте решение XmlAjaxService.sln, как описано в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к странице http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm (не открывайте страницу XmlAjaxClientPage.htm в браузере из каталога проекта).  
  
## <a name="see-also"></a>См. также  
 [AJAX службы с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
