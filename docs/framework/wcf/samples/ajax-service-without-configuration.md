---
title: "Служба AJAX без конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 32879c2b618f3e22960a7828d29601f502a55585
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="cb62a-102">Служба AJAX без конфигурации</span><span class="sxs-lookup"><span data-stu-id="cb62a-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="cb62a-103">В этом примере показано использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания базовой службы асинхронных скриптов JavaScript и XML (AJAX) ASP.NET (службы, которую можно использовать из клиента на основе веб-браузера с помощью кода JavaScript) без применения каких-либо параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cb62a-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="cb62a-104">Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.</span><span class="sxs-lookup"><span data-stu-id="cb62a-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="cb62a-105">Поддержка технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="cb62a-105">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="cb62a-106">Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [примеров Ajax](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="cb62a-106">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb62a-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cb62a-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cb62a-108">Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="cb62a-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="cb62a-109">Как описано в [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образце <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> используется для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="cb62a-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```  
  
 <span data-ttu-id="cb62a-110">Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе.</span><span class="sxs-lookup"><span data-stu-id="cb62a-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="cb62a-111">Если необходимо сделать для конечной точки, без изменения конфигурации \<системы. ServiceModel > можно полностью удалить раздел из файла Web.config для службы.</span><span class="sxs-lookup"><span data-stu-id="cb62a-111">If no configuration changes need to be made to the endpoint, the \<system.ServiceModel> section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="cb62a-112">Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx.</span><span class="sxs-lookup"><span data-stu-id="cb62a-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="cb62a-113">Если дело обстоит иначе, то удалить можно весь файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="cb62a-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cb62a-114">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cb62a-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cb62a-115">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cb62a-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cb62a-116">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb62a-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cb62a-117">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cb62a-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cb62a-118">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cb62a-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cb62a-119">Убедитесь, что настройка инструкциям [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cb62a-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="cb62a-120">Постройте решение ConfigFreeAjaxService.sln, как описано в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cb62a-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="cb62a-121">Перейдите по адресу http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (не открывайте ConfigFreeClientPage.aspx в браузере из каталога проекта).</span><span class="sxs-lookup"><span data-stu-id="cb62a-121">Navigate to http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb62a-122">При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS.</span><span class="sxs-lookup"><span data-stu-id="cb62a-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="cb62a-123">Однако если они включены, отключите проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cb62a-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="cb62a-124">По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".</span><span class="sxs-lookup"><span data-stu-id="cb62a-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb62a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="cb62a-125">See Also</span></span>  
 [<span data-ttu-id="cb62a-126">Базовая служба AJAX</span><span class="sxs-lookup"><span data-stu-id="cb62a-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
