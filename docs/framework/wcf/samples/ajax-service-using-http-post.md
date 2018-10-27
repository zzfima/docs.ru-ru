---
title: Служба AJAX с использованием HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: df199b40a4a9ebb9a36cea7234b484273348cd9e
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50036337"
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="9de3b-102">Служба AJAX с использованием HTTP POST</span><span class="sxs-lookup"><span data-stu-id="9de3b-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="9de3b-103">В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) службы, которая использует HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="9de3b-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="9de3b-104">Обращаться к службе AJAX можно с использованием кода JavaScript из клиента на основе веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="9de3b-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="9de3b-105">Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образец; единственное различие между двумя примерами является использование HTTP POST вместо HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="9de3b-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="9de3b-106">Поддержка AJAX в Windows Communication Foundation (WCF) оптимизирована для использования с ASP.NET AJAX с помощью `ScriptManager` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9de3b-106">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="9de3b-107">Пример использования WCF с ASP.NET AJAX, см. в разделе [образцы Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="9de3b-107">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9de3b-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="9de3b-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9de3b-109">Служба в следующем примере — это служба WCF без написания кода относящегося к AJAX.</span><span class="sxs-lookup"><span data-stu-id="9de3b-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="9de3b-110">Если <xref:System.ServiceModel.Web.WebInvokeAttribute> при выполнении операции применяется атрибут или <xref:System.ServiceModel.Web.WebGetAttribute> не применяется атрибут, используемый по умолчанию HTTP-команда («POST»).</span><span class="sxs-lookup"><span data-stu-id="9de3b-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="9de3b-111">Запросы POST строить тяжелее, чем запросы GET, однако они не кэшируются; запросы POST следует использовать для всех операций, в которых нельзя использовать кэширование.</span><span class="sxs-lookup"><span data-stu-id="9de3b-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 <span data-ttu-id="9de3b-112">Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.</span><span class="sxs-lookup"><span data-stu-id="9de3b-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="9de3b-113">В отличие от запросов GET вызывать службы POST из браузера нельзя.</span><span class="sxs-lookup"><span data-stu-id="9de3b-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="9de3b-114">Например, перейдя к `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` возникает ошибка, поскольку служба POST ожидает `n1` и `n2` параметры, которые будут отправляться в теле сообщения в формате JSON, а не в URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="9de3b-114">For example, navigating to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body in the JSON format, and not in the URL.</span></span>  
  
 <span data-ttu-id="9de3b-115">Клиентская веб-страница PostAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице.</span><span class="sxs-lookup"><span data-stu-id="9de3b-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="9de3b-116">Служба отвечает так же как и в [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца с помощью запроса GET.</span><span class="sxs-lookup"><span data-stu-id="9de3b-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9de3b-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9de3b-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9de3b-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9de3b-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9de3b-119">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="9de3b-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9de3b-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9de3b-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9de3b-121">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="9de3b-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9de3b-122">Убедитесь, что выполнены инструкции по настройке [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9de3b-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9de3b-123">Построение решения PostAjaxService.sln, как описано в разделе [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9de3b-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9de3b-124">Перейдите к `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (не открывайте страницу PostAjaxClientPage.aspx в браузере из каталога проекта).</span><span class="sxs-lookup"><span data-stu-id="9de3b-124">Navigate to `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>
