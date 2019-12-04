---
title: Пример службы AJAX с JSON и XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: ca9bdbfa135ac7dc0b69589d4f8fce07bc4c4afe
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716219"
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Пример службы AJAX с JSON и XML

В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания асинхронной службы JavaScript и XML (AJAX), которая возвращает либо нотация объектов JavaScript (JSON), либо данные XML. К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера. Этот пример основан на образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) .

В отличие от других примеров AJAX, в данном примере не используется ASP.NET AJAX и управление <xref:System.Web.UI.ScriptManager>. С некоторой дополнительной конфигурацией доступ к службам WCF AJAX можно получить с любой HTML-страницы через JavaScript. Этот сценарий показан здесь. Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).

В данном разделе показано переключение типа отклика операции между JSON и XML. Данная функциональность доступна независимо от того, настроена служба для доступа через клиентскую страницу ASP.NET AJAX или через HTML/JavaScript.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Чтобы разрешить использование клиентов, не являющихся клиентами ASP.NET AJAX, используйте <xref:System.ServiceModel.Activation.WebServiceHostFactory> (а не <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) в SVC-файле. Объект <xref:System.ServiceModel.Activation.WebServiceHostFactory> добавляет стандартную конечную точку <xref:System.ServiceModel.Description.WebHttpEndpoint> в службу. Конечная точка настраивается по пустому адресу относительно SVC-файла; Это означает, что адрес службы `http://localhost/ServiceModelSamples/service.svc`, без дополнительных суффиксов, отличных от имени операции.

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>`

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

Формат данных по умолчанию для <xref:System.ServiceModel.Description.WebHttpEndpoint> — XML, а формат данных по умолчанию для <xref:System.ServiceModel.Description.WebScriptEndpoint> — JSON. Дополнительные сведения см. в разделе [Создание служб AJAX WCF без ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).

Служба в следующем примере представляет собой стандартную службу WCF с двумя операциями. Обе операции требуют использования основного стиля <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> в <xref:System.ServiceModel.Web.WebGetAttribute> или атрибутов <xref:System.ServiceModel.Web.WebInvokeAttribute>, которые относятся к поведению `webHttp` и не влияют на переключение формата данных JSON/XML.

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathXml(double n1, double n2);
```

Формат ответа для операции указан в формате XML, который является значением по умолчанию для\<поведения [> HTTP](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) . Тем не менее, рекомендуется явно указывать формат ответа.

Другая операция использует атрибут `WebInvokeAttribute` и явно указывает JSON вместо XML для ответа.

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathJson(double n1, double n2);
```

Обратите внимание, что в обоих случаях операции возвращают сложный тип, `MathResult`, который является стандартным типом контракта данных WCF.

Клиентская веб-страница Ксмлажаксклиентпаже. htm содержит код JavaScript, который вызывает одну из двух предыдущих операций, когда пользователь щелкает на странице команду **выполнить вычисление (вернуть JSON)** или **выполнить вычисление (возврат XML)** . Код, вызывающий службу, создает тело JSON и отправляет его с помощью HTTP POST. Запрос создается вручную в JavaScript, в отличие от примера [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) и других примеров, использующих ASP.NET AJAX.

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
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Создайте решение Ксмлажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Перейдите к `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (не открывайте Ксмлажаксклиентпаже. htm в браузере из каталога проекта).

## <a name="see-also"></a>См. также:

- [Служба AJAX с использованием HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
