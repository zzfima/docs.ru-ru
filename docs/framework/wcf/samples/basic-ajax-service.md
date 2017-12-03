---
title: "Базовая служба AJAX"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1890bd52d3d71ab7419cf1b89f582c3d0efbe9f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="basic-ajax-service"></a><span data-ttu-id="1bbcb-102">Базовая служба AJAX</span><span class="sxs-lookup"><span data-stu-id="1bbcb-102">Basic AJAX Service</span></span>
<span data-ttu-id="1bbcb-103">В этом образце показано использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания базовой службы асинхронных скриптов JavaScript и XML (AJAX) ASP.NET (службу, которую можно использовать из клиента на основе веб-браузера с помощью кода JavaScript).</span><span class="sxs-lookup"><span data-stu-id="1bbcb-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="1bbcb-104">Служба использует атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, чтобы обеспечить ответы службы на запросы HTTP GET и настройку на использование при ответах формата данных JSON.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>  
  
 <span data-ttu-id="1bbcb-105">Поддержка технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-105">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="1bbcb-106">Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [примеров AJAX](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="1bbcb-106">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bbcb-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1bbcb-108">В следующем коде атрибут <xref:System.ServiceModel.Web.WebGetAttribute> применяется к операции `Add`, чтобы гарантировать ответ службы на запросы HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="1bbcb-109">Код использует GET в целях упрощения (запрос HTTP GET можно создать в любом веб-браузере).</span><span class="sxs-lookup"><span data-stu-id="1bbcb-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="1bbcb-110">GET также можно использовать для обеспечения кэширования.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="1bbcb-111">HTTP POST используется по умолчанию в случае отсутствия атрибута `WebGetAttribute`.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>  
  
```  
[ServiceContract(Namespace = "SimpleAjaxService")]  
public interface ICalculator  
{  
  
    [WebGet]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}  
```  
  
 <span data-ttu-id="1bbcb-112">Образец SVC-файла использует <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, которая добавляет стандартную конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="1bbcb-113">Конечная точка настраивается с пустым адресом относительно SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="1bbcb-114">Это означает, что адресом службы будет http://localhost/ServiceModelSamples/service.svc без дополнительных суффиксов, кроме имени операции.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-114">This means that the address of the service is http://localhost/ServiceModelSamples/service.svc, with no additional suffixes other than the operation name.</span></span>  
  
```  
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>  
```  
  
 <span data-ttu-id="1bbcb-115"><xref:System.ServiceModel.Description.WebScriptEndpoint> предварительно настраивается таким образом, чтобы служба была доступна с клиентской страницы ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="1bbcb-116">Следующий раздел в Web.config может использоваться для дополнительных изменений конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="1bbcb-117">Если дополнительных изменений не требуется, он может быть удален.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-117">It can be removed if no extra changes are required.</span></span>  
  
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
  
 <span data-ttu-id="1bbcb-118"><xref:System.ServiceModel.Description.WebScriptEndpoint> задает формат данных по умолчанию для службы как JSON вместо XML.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="1bbcb-119">Чтобы вызвать службу, перейдите по адресу http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 после завершения настройки и выполнения шагов, описанных далее в этой теме.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-119">To invoke the service, navigate to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="1bbcb-120">Таки функциональные возможности тестирования обеспечиваются за счет запроса HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>  
  
 <span data-ttu-id="1bbcb-121">Клиентская веб-страница SimpleAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="1bbcb-122">Элемент управления `ScriptManager` используется для создания прокси-сервера для службы, доступной через JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>  
  
```  
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```  
  
 <span data-ttu-id="1bbcb-123">Создается локальный прокси-сервер, и вызываются операции с помощью следующего кода JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>  
  
```  
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```  
  
 <span data-ttu-id="1bbcb-124">Если вызов процедуры завершен успешно, код вызывает обработчик `onSuccess` и в текстовом поле показывается результат операции.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>  
  
```  
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="1bbcb-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1bbcb-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1bbcb-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1bbcb-127">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bbcb-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1bbcb-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1bbcb-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="1bbcb-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1bbcb-129">See Also</span></span>
