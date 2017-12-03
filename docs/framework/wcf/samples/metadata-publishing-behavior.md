---
title: "Поведение публикации метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a92b41df3b2e9c556e61c08979290b12206f18aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="metadata-publishing-behavior"></a><span data-ttu-id="9e903-102">Поведение публикации метаданных</span><span class="sxs-lookup"><span data-stu-id="9e903-102">Metadata Publishing Behavior</span></span>
<span data-ttu-id="9e903-103">Образец поведения публикации метаданных демонстрирует, как управлять возможностями публикации метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="9e903-103">The Metadata Publishing Behavior sample demonstrates how to control the metadata publishing features of a service.</span></span> <span data-ttu-id="9e903-104">Чтобы предотвратить непреднамеренное разглашение потенциально важных метаданных службы, в конфигурации служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] публикация метаданных по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="9e903-104">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="9e903-105">Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e903-105">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e903-106">Для ясности этот образец демонстрирует создание незащищенной конечной точки публикации метаданных.</span><span class="sxs-lookup"><span data-stu-id="9e903-106">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="9e903-107">Такие конечные точки являются потенциально доступными для анонимных не прошедших проверку подлинности потребителей, поэтому перед развертыванием таких конечных точек следует соблюдать осторожность и убедиться, что публичное раскрытие метаданных службы уместно.</span><span class="sxs-lookup"><span data-stu-id="9e903-107">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="9e903-108">В разделе [конечной точки метаданных защиты пользовательских](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) образец для образца, который защищает конечную точку метаданных.</span><span class="sxs-lookup"><span data-stu-id="9e903-108">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample that secures a metadata endpoint.</span></span>  
  
 <span data-ttu-id="9e903-109">Пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует `ICalculator` контракт службы.</span><span class="sxs-lookup"><span data-stu-id="9e903-109">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="9e903-110">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="9e903-110">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e903-111">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="9e903-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9e903-112">Чтобы отобразить метаданные для службы, параметр <xref:System.ServiceModel.Description.ServiceMetadataBehavior> должен быть сконфигурирован в службе.</span><span class="sxs-lookup"><span data-stu-id="9e903-112">For a service to expose metadata, the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> must be configured on the service.</span></span> <span data-ttu-id="9e903-113">При наличии такого поведения можно публиковать метаданные, конфигурируя конечную точку для предоставления контракта <xref:System.ServiceModel.Description.IMetadataExchange> как реализации протокола WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="9e903-113">When this behavior is present, you can publish metadata by configuring an endpoint to expose the <xref:System.ServiceModel.Description.IMetadataExchange> contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="9e903-114">Для удобства этому контракту присвоено сокращенное имя конфигурации "IMetadataExchange".</span><span class="sxs-lookup"><span data-stu-id="9e903-114">As a convenience, this contract has been given the abbreviated configuration name of "IMetadataExchange".</span></span> <span data-ttu-id="9e903-115">В этом образце используется привязка `mexHttpBinding`, являющаяся удобной стандартной привязкой, эквивалентной `wsHttpBinding` с режимом безопасности, которому присвоено значение `None`.</span><span class="sxs-lookup"><span data-stu-id="9e903-115">This sample uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="9e903-116">Относительный адрес «mex» используется в конечной точке, которая при разрешении относительно базового адреса службы приводит к созданию адреса конечной точки http://localhost/servicemodelsamples/service.svc/mex.</span><span class="sxs-lookup"><span data-stu-id="9e903-116">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span> <span data-ttu-id="9e903-117">Ниже приводится конфигурация поведения:</span><span class="sxs-lookup"><span data-stu-id="9e903-117">The following shows the behavior configuration:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="9e903-118">Ниже приводится описание конечной точки MEX.</span><span class="sxs-lookup"><span data-stu-id="9e903-118">The following shows the MEX endpoint.</span></span>  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="9e903-119">Этот образец присваивает свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> логическое значение `true`, а также предоставляет метаданные службы, используя HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="9e903-119">This sample sets the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, which also exposes the service's metadata using HTTP GET.</span></span> <span data-ttu-id="9e903-120">Чтобы включить конечную точку метаданных HTTP GET, службе должен быть присвоен базовый HTTP-адрес.</span><span class="sxs-lookup"><span data-stu-id="9e903-120">To enable an HTTP GET metadata endpoint, the service must have an HTTP base address.</span></span> <span data-ttu-id="9e903-121">Для доступа к метаданным используется строка запроса `?wsdl` для базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="9e903-121">The query string `?wsdl` is used on the base address of the service to access the metadata.</span></span> <span data-ttu-id="9e903-122">Например, для просмотра в веб-браузере WSDL для службы используйте адрес http://localhost/servicemodelsamples/service.svc?wsdl.</span><span class="sxs-lookup"><span data-stu-id="9e903-122">For example, to see the WSDL for the service in a Web browser you would use the address http://localhost/servicemodelsamples/service.svc?wsdl.</span></span> <span data-ttu-id="9e903-123">Кроме того, можно использовать это поведение, чтобы предоставить метаданные по протоколу HTTPS, присваивая свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> логическое значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9e903-123">Alternatively, you can use this behavior to expose metadata over HTTPS by setting <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> to `true`.</span></span> <span data-ttu-id="9e903-124">Это потребует наличия базового HTTPS-адреса.</span><span class="sxs-lookup"><span data-stu-id="9e903-124">This requires an HTTPS base address.</span></span>  
  
 <span data-ttu-id="9e903-125">Для использования конечной точки обмена Метаданными службы доступа к [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9e903-125">To access the service's MEX endpoint use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 <span data-ttu-id="9e903-126">Это позволит создать клиент, основанный на метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="9e903-126">This generates a client based on the service's metadata.</span></span>  
  
 <span data-ttu-id="9e903-127">Для доступа к метаданным службы с использованием HTTP GET укажите в браузере http://localhost/servicemodelsamples/service.svc?wsdl.</span><span class="sxs-lookup"><span data-stu-id="9e903-127">To access the service's metadata using HTTP GET, point your browser to http://localhost/servicemodelsamples/service.svc?wsdl.</span></span>  
  
 <span data-ttu-id="9e903-128">При удалении этого поведения и попытке открыть службу будет получено исключение.</span><span class="sxs-lookup"><span data-stu-id="9e903-128">If you remove this behavior and try to open the service you get an exception.</span></span> <span data-ttu-id="9e903-129">Происходит ошибка, поскольку конечная точка, настроенная с контрактом `IMetadataExchange`, не имеет реализации при отсутствии поведения.</span><span class="sxs-lookup"><span data-stu-id="9e903-129">This error occurs because without the behavior, the endpoint configured with the `IMetadataExchange` contract has no implementation.</span></span>  
  
 <span data-ttu-id="9e903-130">Если свойству `HttpGetEnabled` присваивается логическое значение `false`, будет отображена справочная страница CalculatorService вместо метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="9e903-130">If you set `HttpGetEnabled` to `false`, you see the CalculatorService help page instead of seeing the service's metadata.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9e903-131">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="9e903-131">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9e903-132">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e903-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9e903-133">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e903-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9e903-134">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e903-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e903-135">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9e903-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9e903-136">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9e903-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9e903-137">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e903-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e903-138">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9e903-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## <a name="see-also"></a><span data-ttu-id="9e903-139">См. также</span><span class="sxs-lookup"><span data-stu-id="9e903-139">See Also</span></span>
