---
title: Служба AJAX с использованием HTTP POST
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1446fadeb249d91f0eb3e65b1155f00090441a5a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="eebd2-102">Служба AJAX с использованием HTTP POST</span><span class="sxs-lookup"><span data-stu-id="eebd2-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="eebd2-103">В этом примере показано, как с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] создать службу [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] асинхронных скриптов JavaScript и XML (AJAX), использующую HTTP-метод POST.</span><span class="sxs-lookup"><span data-stu-id="eebd2-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="eebd2-104">Обращаться к службе AJAX можно с использованием кода JavaScript из клиента на основе веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="eebd2-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="eebd2-105">Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образец; единственное различие между двумя образцы является использование HTTP POST, а не HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="eebd2-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="eebd2-106">Поддержка технологии AJAX в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="eebd2-106">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="eebd2-107">Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [примеров Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="eebd2-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eebd2-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="eebd2-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="eebd2-109">Служба в следующем примере является службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без кода, относящегося к AJAX.</span><span class="sxs-lookup"><span data-stu-id="eebd2-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="eebd2-110">Если <xref:System.ServiceModel.Web.WebInvokeAttribute> при выполнении операции применяется атрибут или <xref:System.ServiceModel.Web.WebGetAttribute> не применяется атрибут, используется HTTP-команда по умолчанию («POST»).</span><span class="sxs-lookup"><span data-stu-id="eebd2-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="eebd2-111">Запросы POST строить тяжелее, чем запросы GET, однако они не кэшируются; запросы POST следует использовать для всех операций, в которых нельзя использовать кэширование.</span><span class="sxs-lookup"><span data-stu-id="eebd2-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 <span data-ttu-id="eebd2-112">Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.</span><span class="sxs-lookup"><span data-stu-id="eebd2-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="eebd2-113">В отличие от запросов GET вызывать службы POST из браузера нельзя.</span><span class="sxs-lookup"><span data-stu-id="eebd2-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="eebd2-114">Например, переход к http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 приводит к ошибке, поскольку служба POST ожидает `n1` и `n2` параметры, отправляемые в тексте сообщения — в формате JSON —, а не в URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="eebd2-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="eebd2-115">Клиентская веб-страница PostAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице.</span><span class="sxs-lookup"><span data-stu-id="eebd2-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="eebd2-116">Эта служба отвечает таким же образом, как и в [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) примера с помощью запроса GET.</span><span class="sxs-lookup"><span data-stu-id="eebd2-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eebd2-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eebd2-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="eebd2-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="eebd2-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eebd2-119">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="eebd2-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eebd2-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="eebd2-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eebd2-121">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="eebd2-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="eebd2-122">Убедитесь, что инструкции по установке [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="eebd2-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="eebd2-123">Постройте решение PostAjaxService.sln, как описано в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="eebd2-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="eebd2-124">Перейдите к http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (не открывайте PostAjaxClientPage.aspx в браузере из каталога проекта).</span><span class="sxs-lookup"><span data-stu-id="eebd2-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eebd2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="eebd2-125">See Also</span></span>
