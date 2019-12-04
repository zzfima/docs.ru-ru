---
title: Базовая служба AJAX
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 334cc9e53d7d9746c204abe37e7c30d00baa824b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716125"
---
# <a name="basic-ajax-service"></a><span data-ttu-id="1b747-102">Базовая служба AJAX</span><span class="sxs-lookup"><span data-stu-id="1b747-102">Basic AJAX Service</span></span>

<span data-ttu-id="1b747-103">В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания базовой асинхронной службы JavaScript и XML (AJAX) ASP.NET (службы, к которой можно получить доступ с помощью кода JavaScript из клиента веб-браузера).</span><span class="sxs-lookup"><span data-stu-id="1b747-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="1b747-104">Служба использует атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, чтобы обеспечить ответы службы на запросы HTTP GET и настройку на использование при ответах формата данных JSON.</span><span class="sxs-lookup"><span data-stu-id="1b747-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>

<span data-ttu-id="1b747-105">Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX через элемент управления `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="1b747-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="1b747-106">Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="1b747-106">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1b747-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1b747-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="1b747-108">В следующем коде атрибут <xref:System.ServiceModel.Web.WebGetAttribute> применяется к операции `Add`, чтобы гарантировать ответ службы на запросы HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="1b747-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="1b747-109">Код использует GET в целях упрощения (запрос HTTP GET можно создать в любом веб-браузере).</span><span class="sxs-lookup"><span data-stu-id="1b747-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="1b747-110">GET также можно использовать для обеспечения кэширования.</span><span class="sxs-lookup"><span data-stu-id="1b747-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="1b747-111">HTTP POST используется по умолчанию в случае отсутствия атрибута `WebGetAttribute`.</span><span class="sxs-lookup"><span data-stu-id="1b747-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

<span data-ttu-id="1b747-112">Образец SVC-файла использует <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, которая добавляет стандартную конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе.</span><span class="sxs-lookup"><span data-stu-id="1b747-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="1b747-113">Конечная точка настраивается с пустым адресом относительно SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="1b747-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="1b747-114">Это означает, что адрес службы `http://localhost/ServiceModelSamples/service.svc`, без дополнительных суффиксов, отличных от имени операции.</span><span class="sxs-lookup"><span data-stu-id="1b747-114">This means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>

`<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>`

<span data-ttu-id="1b747-115"><xref:System.ServiceModel.Description.WebScriptEndpoint> предварительно настраивается таким образом, чтобы служба была доступна с клиентской страницы ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="1b747-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="1b747-116">Следующий раздел в Web.config может использоваться для дополнительных изменений конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1b747-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="1b747-117">Если дополнительных изменений не требуется, он может быть удален.</span><span class="sxs-lookup"><span data-stu-id="1b747-117">It can be removed if no extra changes are required.</span></span>

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

<span data-ttu-id="1b747-118"><xref:System.ServiceModel.Description.WebScriptEndpoint> задает формат данных по умолчанию для службы как JSON вместо XML.</span><span class="sxs-lookup"><span data-stu-id="1b747-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="1b747-119">Чтобы вызвать службу, перейдите к `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` после завершения действий по настройке и сборке, приведенных далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1b747-119">To invoke the service, navigate to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="1b747-120">Таки функциональные возможности тестирования обеспечиваются за счет запроса HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="1b747-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>

<span data-ttu-id="1b747-121">Клиентская веб-страница SimpleAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице.</span><span class="sxs-lookup"><span data-stu-id="1b747-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="1b747-122">Элемент управления `ScriptManager` используется для создания прокси-сервера для службы, доступной через JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1b747-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">
    <Services>
        <asp:ServiceReference Path="service.svc" />
    </Services>
</asp:ScriptManager>
```

<span data-ttu-id="1b747-123">Создается локальный прокси-сервер, и вызываются операции с помощью следующего кода JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1b747-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>

```javascript
// Code for extracting arguments n1 and n2 omitted…
// Instantiate a service proxy
var proxy = new SimpleAjaxService.ICalculator();
// Code for selecting operation omitted…
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);
```

<span data-ttu-id="1b747-124">Если вызов процедуры завершен успешно, код вызывает обработчик `onSuccess` и в текстовом поле показывается результат операции.</span><span class="sxs-lookup"><span data-stu-id="1b747-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>

```javascript
function onSuccess(mathResult){
     document.getElementById("result").value = mathResult;
}
```

> [!IMPORTANT]
> <span data-ttu-id="1b747-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1b747-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1b747-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1b747-126">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="1b747-127">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="1b747-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1b747-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1b747-128">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`
