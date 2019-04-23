---
title: Базовая служба AJAX
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 8bcfb9a751670d3d1c32de6d8e6f7dc1b84ea30d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979502"
---
# <a name="basic-ajax-service"></a>Базовая служба AJAX
В этом примере показано, как использовать Windows Communication Foundation (WCF), чтобы создать базовую службу ASP.NET асинхронных скриптов JavaScript и XML (AJAX) (службы, доступны с помощью кода JavaScript из веб-браузера клиента). Служба использует атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, чтобы обеспечить ответы службы на запросы HTTP GET и настройку на использование при ответах формата данных JSON.  
  
 Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX с помощью `ScriptManager` элемента управления. Пример использования WCF с ASP.NET AJAX, см. в разделе [образцы AJAX](ajax.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В следующем коде атрибут <xref:System.ServiceModel.Web.WebGetAttribute> применяется к операции `Add`, чтобы гарантировать ответ службы на запросы HTTP GET. Код использует GET в целях упрощения (запрос HTTP GET можно создать в любом веб-браузере). GET также можно использовать для обеспечения кэширования. HTTP POST используется по умолчанию в случае отсутствия атрибута `WebGetAttribute`.  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 Образец SVC-файла использует <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, которая добавляет стандартную конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе. Конечная точка настраивается с пустым адресом относительно SVC-файла. Это означает, что адресом службы является `http://localhost/ServiceModelSamples/service.svc`, без дополнительных суффиксов, за исключением имени операции.  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 <xref:System.ServiceModel.Description.WebScriptEndpoint> предварительно настраивается таким образом, чтобы служба была доступна с клиентской страницы ASP.NET AJAX. Следующий раздел в Web.config может использоваться для дополнительных изменений конфигурации конечной точки. Если дополнительных изменений не требуется, он может быть удален.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint> задает формат данных по умолчанию для службы как JSON вместо XML. Чтобы вызвать службу, перейдите к `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` после завершения настройки и шагов, описанных далее в этом разделе. Таки функциональные возможности тестирования обеспечиваются за счет запроса HTTP GET.  
  
 Клиентская веб-страница SimpleAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице. Элемент управления `ScriptManager` используется для создания прокси-сервера для службы, доступной через JavaScript.  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 Создается локальный прокси-сервер, и вызываются операции с помощью следующего кода JavaScript.  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 Если вызов процедуры завершен успешно, код вызывает обработчик `onSuccess` и в текстовом поле показывается результат операции.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
