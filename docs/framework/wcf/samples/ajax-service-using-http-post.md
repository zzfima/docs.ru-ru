---
title: Служба AJAX с использованием HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 560739c576965d597010a6885b53c7905aaeb8e7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716185"
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="35c59-102">Служба AJAX с использованием HTTP POST</span><span class="sxs-lookup"><span data-stu-id="35c59-102">AJAX Service Using HTTP POST</span></span>

<span data-ttu-id="35c59-103">В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания асинхронной службы JavaScript и XML (AJAX) ASP.NET, использующей HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="35c59-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="35c59-104">Обращаться к службе AJAX можно с использованием кода JavaScript из клиента на основе веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="35c59-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="35c59-105">Этот пример основан на образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ; Единственное различие между двумя примерами — использование HTTP POST вместо HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="35c59-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>

<span data-ttu-id="35c59-106">Поддержка AJAX в Windows Communication Foundation (WCF) оптимизирована для использования с ASP.NET AJAX через элемент управления `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="35c59-106">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="35c59-107">Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="35c59-107">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>

> [!NOTE]
> <span data-ttu-id="35c59-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="35c59-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="35c59-109">Служба в следующем примере представляет собой службу WCF без кода, зависящего от AJAX.</span><span class="sxs-lookup"><span data-stu-id="35c59-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>

<span data-ttu-id="35c59-110">Если атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> применяется к операции или атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию (POST).</span><span class="sxs-lookup"><span data-stu-id="35c59-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="35c59-111">Запросы POST строить тяжелее, чем запросы GET, однако они не кэшируются; запросы POST следует использовать для всех операций, в которых нельзя использовать кэширование.</span><span class="sxs-lookup"><span data-stu-id="35c59-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

<span data-ttu-id="35c59-112">Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.</span><span class="sxs-lookup"><span data-stu-id="35c59-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="35c59-113">В отличие от запросов GET вызывать службы POST из браузера нельзя.</span><span class="sxs-lookup"><span data-stu-id="35c59-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="35c59-114">Например, переход к `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` приведет к ошибке, так как служба POST ожидает, что параметры `n1` и `n2` отправляются в тексте сообщения в формате JSON, а не в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="35c59-114">For example, navigating to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body in the JSON format, and not in the URL.</span></span>

<span data-ttu-id="35c59-115">Клиентская веб-страница PostAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице.</span><span class="sxs-lookup"><span data-stu-id="35c59-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="35c59-116">Служба реагирует так же, как и в образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) , с запросом GET.</span><span class="sxs-lookup"><span data-stu-id="35c59-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35c59-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="35c59-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="35c59-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="35c59-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="35c59-119">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="35c59-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35c59-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="35c59-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="35c59-121">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="35c59-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="35c59-122">Убедитесь, что инструкции по установке выполняются [однократным образом для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35c59-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="35c59-123">Создайте решение Постажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35c59-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="35c59-124">Перейдите к `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (не открывайте Постажаксклиентпаже. aspx в браузере из каталога проекта).</span><span class="sxs-lookup"><span data-stu-id="35c59-124">Navigate to `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>
