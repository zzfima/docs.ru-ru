---
title: Служба AJAX без конфигурации
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: bf80f00bbca370c973dab9f20024284a465be521
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716195"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="d1942-102">Служба AJAX без конфигурации</span><span class="sxs-lookup"><span data-stu-id="d1942-102">AJAX Service Without Configuration</span></span>

<span data-ttu-id="d1942-103">В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания базовой асинхронной службы JavaScript и XML (AJAX) ASP.NET (службы, к которой можно получить доступ с помощью кода JavaScript из клиента веб-браузера) без использования конфигурации. Параметры.</span><span class="sxs-lookup"><span data-stu-id="d1942-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="d1942-104">Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.</span><span class="sxs-lookup"><span data-stu-id="d1942-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>

<span data-ttu-id="d1942-105">Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX через элемент управления `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="d1942-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="d1942-106">Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="d1942-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d1942-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="d1942-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="d1942-108">Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="d1942-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="d1942-109">Как описано в примере [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) , <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> используется для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="d1942-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

<span data-ttu-id="d1942-110">Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе.</span><span class="sxs-lookup"><span data-stu-id="d1942-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="d1942-111">Если в конфигурацию этой конечной точки не требуется вносить изменения, то раздел `<system.ServiceModel>` из файла Web.config для этой службы может быть полностью удален.</span><span class="sxs-lookup"><span data-stu-id="d1942-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="d1942-112">Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx.</span><span class="sxs-lookup"><span data-stu-id="d1942-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="d1942-113">Если дело обстоит иначе, то удалить можно весь файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="d1942-113">If that were not the case, the entire Web.config file could be removed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1942-114">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1942-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d1942-115">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d1942-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="d1942-116">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="d1942-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d1942-117">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d1942-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d1942-118">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d1942-118">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="d1942-119">Убедитесь, что инструкции по установке выполняются в ходе [однократной настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d1942-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="d1942-120">Создайте решение Конфигфриажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d1942-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="d1942-121">Перейдите к `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (не открывайте ConfigFreeClientPage. aspx в браузере в каталоге проекта).</span><span class="sxs-lookup"><span data-stu-id="d1942-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>

> [!NOTE]
> <span data-ttu-id="d1942-122">При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS.</span><span class="sxs-lookup"><span data-stu-id="d1942-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="d1942-123">Однако если они включены, отключите проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d1942-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="d1942-124">По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".</span><span class="sxs-lookup"><span data-stu-id="d1942-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>

## <a name="see-also"></a><span data-ttu-id="d1942-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1942-125">See also</span></span>

- [<span data-ttu-id="d1942-126">Базовая служба AJAX</span><span class="sxs-lookup"><span data-stu-id="d1942-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
