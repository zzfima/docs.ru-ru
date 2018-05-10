---
title: Пример службы AJAX с JSON и XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: 32964c287b0064daf529aa4c1e28f0927d29a6d5
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Пример службы AJAX с JSON и XML
В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания служб асинхронных сценариев JavaScript и XML (AJAX), возвращает JavaScript Object Notation (JSON) или XML-данные. К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера. Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца.  
  
 В отличие от других примеров AJAX, в данном примере не используется ASP.NET AJAX и управление <xref:System.Web.UI.ScriptManager>. С помощью дополнительной настройки служб WCF AJAX можно обращаться из любой HTML-страницы посредством JavaScript, и этот сценарий показан ниже. Пример использования WCF с помощью ASP.NET AJAX см. в разделе [примеров AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
 В данном разделе показано переключение типа отклика операции между JSON и XML. Данная функциональность доступна независимо от того, настроена служба для доступа через клиентскую страницу ASP.NET AJAX или через HTML/JavaScript.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Чтобы разрешить использование клиентов, не являющихся клиентами ASP.NET AJAX, используйте <xref:System.ServiceModel.Activation.WebServiceHostFactory> (а не <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) в SVC-файле. Объект <xref:System.ServiceModel.Activation.WebServiceHostFactory> добавляет стандартную конечную точку <xref:System.ServiceModel.Description.WebHttpEndpoint> в службу. Конечная точка настраивается с пустым адресом относительно SVC-файла; Это означает, что адрес службы http://localhost/ServiceModelSamples/service.svc, без дополнительных суффиксов, кроме имени операции.  
  
```svc
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
  
 Служба в следующем примере является стандартной службы WCF с двумя операциями. Обе операции требуют использования основного стиля <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> в <xref:System.ServiceModel.Web.WebGetAttribute> или атрибутов <xref:System.ServiceModel.Web.WebInvokeAttribute>, которые относятся к поведению `webHttp` и не влияют на переключение формата данных JSON/XML.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 Формат ответа для операции указан в формате XML, который используется по умолчанию для [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) поведение. Тем не менее, рекомендуется явно указывать формат ответа.  
  
 Другая операция использует атрибут `WebInvokeAttribute` и явно указывает JSON вместо XML для ответа.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 Обратите внимание, что в обоих случаях операции возвращают комплексный тип `MathResult`, который является стандартный тип контракта данных WCF.  
  
 Клиентская веб-страница XmlAjaxClientPage.htm содержит код JavaScript, вызывающий одну из двух предшествующих операций, когда пользователь щелкает **выполнить расчет (возвратить JSON)** или **выполнить расчет (возвратить XML)**  кнопок на странице. Код, вызывающий службу, создает тело JSON и отправляет его с помощью HTTP POST. Запрос создается вручную из JavaScript, в отличие от [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образец и других примеров с помощью ASP.NET AJAX.  

```csharp
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

```javascript
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Постройте решение XmlAjaxService.sln, как описано в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm (не открывайте XmlAjaxClientPage.htm в браузере из каталога проекта).  
  
## <a name="see-also"></a>См. также  
 [Служба AJAX с использованием HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
