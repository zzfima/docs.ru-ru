---
title: "Поведение отладки службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cb609857dbe3aaee0014e284d80af3b93ac395e5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="service-debug-behavior"></a><span data-ttu-id="1185d-102">Поведение отладки службы</span><span class="sxs-lookup"><span data-stu-id="1185d-102">Service Debug Behavior</span></span>
<span data-ttu-id="1185d-103">В этом образце показано, как могут настраиваться параметры поведения отладки службы.</span><span class="sxs-lookup"><span data-stu-id="1185d-103">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="1185d-104">Пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует `ICalculator` контракт службы.</span><span class="sxs-lookup"><span data-stu-id="1185d-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="1185d-105">Этот образец явно определяет поведение отладки службы в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1185d-105">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="1185d-106">Это также можно выполнить императивно в коде.</span><span class="sxs-lookup"><span data-stu-id="1185d-106">It can also be done imperatively in code.</span></span>  
  
 <span data-ttu-id="1185d-107">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="1185d-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1185d-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1185d-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1185d-109">Файл Web.config для сервера определяет поведение отладки службы для включения страницы справки и обработки исключений, как показано в следующем образце.</span><span class="sxs-lookup"><span data-stu-id="1185d-109">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="1185d-110">[\<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) элемент конфигурации, который позволяет изменять свойства поведения отладки службы.</span><span class="sxs-lookup"><span data-stu-id="1185d-110">[\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="1185d-111">Пользователь может изменять это поведение для достижения следующих целей.</span><span class="sxs-lookup"><span data-stu-id="1185d-111">The user can modify this behavior to achieve the following:</span></span>  
  
-   <span data-ttu-id="1185d-112">Это позволяет службе возвращать любое исключение, вызванное кодом приложения, даже если это исключение не объявлено с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1185d-112">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="1185d-113">Для этого необходимо присвоить параметру `includeExceptionDetailInFaults` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1185d-113">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="1185d-114">Этот параметр полезен при отладке в тех случаях, когда сервер создает непредвиденное исключение.</span><span class="sxs-lookup"><span data-stu-id="1185d-114">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1185d-115">Включать этот параметр в производственной среде небезопасно.</span><span class="sxs-lookup"><span data-stu-id="1185d-115">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="1185d-116">В непредвиденном исключении сервера может содержаться информация, не предназначенная для клиента, поэтому присвоение параметру `includeExceptionDetailsInFaults` значения `true` может привести к утечке информации.</span><span class="sxs-lookup"><span data-stu-id="1185d-116">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>  
  
-   <span data-ttu-id="1185d-117">[ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) также позволяет пользователю включить или отключить страницу справки.</span><span class="sxs-lookup"><span data-stu-id="1185d-117">The [\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="1185d-118">Каждая служба может предоставлять страницу справки, которая содержит данные о службе, включая сведения о конечной точке для получения WSDL для службы.</span><span class="sxs-lookup"><span data-stu-id="1185d-118">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="1185d-119">Эту возможность можно включить, присвоив параметру `httpHelpPageEnabled` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1185d-119">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="1185d-120">Это позволяет возвращать страницу справки в ответ на запрос GET к базовому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="1185d-120">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="1185d-121">Этот адрес можно изменить, задав другой атрибут `httpHelpPageUrl`.</span><span class="sxs-lookup"><span data-stu-id="1185d-121">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="1185d-122">Можно сделать этот процесс безопасным, если использовать транспорт HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="1185d-122">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="1185d-123">Для этого необходимо задать `httpsHelpPageEnabled` и `httpsHelpPageUrl`.</span><span class="sxs-lookup"><span data-stu-id="1185d-123">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>  
  
 <span data-ttu-id="1185d-124">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="1185d-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="1185d-125">Первые три операции (сложение, вычитание и умножение) должны выполняться успешно.</span><span class="sxs-lookup"><span data-stu-id="1185d-125">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="1185d-126">Последняя операция (деление) завершается неудачей - выдается исключение в результате деления на ноль.</span><span class="sxs-lookup"><span data-stu-id="1185d-126">The last operation ("divide") fails with a division by zero exception.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1185d-127">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="1185d-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1185d-128">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1185d-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1185d-129">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1185d-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="1185d-130">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1185d-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1185d-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1185d-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1185d-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1185d-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1185d-133">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1185d-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1185d-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1185d-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
## <a name="see-also"></a><span data-ttu-id="1185d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="1185d-135">See Also</span></span>
