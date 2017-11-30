---
title: "Адресация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3ac0cb2b9df130820a4b12efd4b845b50ad7c79a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="addressing"></a><span data-ttu-id="5863c-102">Адресация</span><span class="sxs-lookup"><span data-stu-id="5863c-102">Addressing</span></span>
<span data-ttu-id="5863c-103">В образце адресации показаны различные аспекты и возможности адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="5863c-103">The Addressing sample demonstrates various aspects and features of endpoint addresses.</span></span> <span data-ttu-id="5863c-104">Пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5863c-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="5863c-105">В этом образце служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="5863c-105">In this sample the service is self-hosted.</span></span> <span data-ttu-id="5863c-106">Как служба, так и клиент являются консольными приложениями.</span><span class="sxs-lookup"><span data-stu-id="5863c-106">Both the service and the client are console applications.</span></span> <span data-ttu-id="5863c-107">Служба определяет несколько конечных точек, используя сочетание их относительных и абсолютных адресов.</span><span class="sxs-lookup"><span data-stu-id="5863c-107">The service defines multiple endpoints using a combination of relative and absolute endpoint addresses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5863c-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="5863c-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="5863c-109">Представленный ниже файл конфигурации службы задает базовый адрес и четыре конечные точки.</span><span class="sxs-lookup"><span data-stu-id="5863c-109">The service configuration file specifies a base address and four endpoints.</span></span> <span data-ttu-id="5863c-110">Базовый адрес задается с помощью элемента add в каталоге service/host/baseAddresses, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5863c-110">The base address is specified using the add element, under service/host/baseAddresses as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 <span data-ttu-id="5863c-111">В первом определении конечной точки, показанном в следующем образце конфигурации, задается относительный адрес. Это означает, что адрес конечной точки представляет собой сочетание базового и относительного адресов, соответствующее правилам формирования универсального кода ресурса.</span><span class="sxs-lookup"><span data-stu-id="5863c-111">The first endpoint definition shown in the following sample configuration specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of URI composition.</span></span>  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="5863c-112">В этом случае относительный адрес пустой (""), поэтому адрес конечной точки совпадает с базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="5863c-112">In this case, the relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="5863c-113">Фактический адрес конечной точки - http://localhost:8000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="5863c-113">The actual endpoint address is http://localhost:8000/servicemodelsamples/service.</span></span>  
  
 <span data-ttu-id="5863c-114">Во втором определении конечной точки также задается относительный адрес, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5863c-114">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span>  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="5863c-115">Относительный адрес, "test", присоединяется к базовому адресу.</span><span class="sxs-lookup"><span data-stu-id="5863c-115">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="5863c-116">Фактический адрес конечной точки - http://localhost:8000/servicemodelsamples/service/test.</span><span class="sxs-lookup"><span data-stu-id="5863c-116">The actual endpoint address is http://localhost:8000/servicemodelsamples/service/test.</span></span>  
  
 <span data-ttu-id="5863c-117">В третьем определении конечной точки задается абсолютный адрес, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5863c-117">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="5863c-118">Базовый адрес не играет никакой роли в этом адресе.</span><span class="sxs-lookup"><span data-stu-id="5863c-118">The base address plays no role in the address.</span></span> <span data-ttu-id="5863c-119">Фактический адрес конечной точки - http://localhost:8001/hello/servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5863c-119">The actual endpoint address is http://localhost:8001/hello/servicemodelsamples.</span></span>  
  
 <span data-ttu-id="5863c-120">В четвертом определении конечной точки задаются абсолютный адрес и другой транспорт - TCP.</span><span class="sxs-lookup"><span data-stu-id="5863c-120">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="5863c-121">Базовый адрес не играет никакой роли в этом адресе.</span><span class="sxs-lookup"><span data-stu-id="5863c-121">The base address plays no role in the address.</span></span> <span data-ttu-id="5863c-122">Фактический адрес конечной точки — net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="5863c-122">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</service>  
```  
  
 <span data-ttu-id="5863c-123">Клиент связывается только с одной конечной точкой службы из четырех, однако в файле конфигурации заданы все четыре.</span><span class="sxs-lookup"><span data-stu-id="5863c-123">The client accesses just one of the four service endpoints, but all four are defined in its configuration file.</span></span> <span data-ttu-id="5863c-124">Клиент выбирает конечную точку при создании объекта `CalculatorProxy`.</span><span class="sxs-lookup"><span data-stu-id="5863c-124">The client selects an endpoint when it creates the `CalculatorProxy` object.</span></span> <span data-ttu-id="5863c-125">Изменяя имя файла конфигурации с `CalculatorEndpoint1` по `CalculatorEndpoint4`, можно использовать любую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="5863c-125">By changing the configuration name from `CalculatorEndpoint1` through `CalculatorEndpoint4`, you can exercise each of the endpoints.</span></span>  
  
 <span data-ttu-id="5863c-126">При запуске образца служба перечисляет адрес, имя привязки и имя контракта для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5863c-126">When you run the sample, the service enumerates the address, binding name and contract name for each of its endpoints.</span></span> <span data-ttu-id="5863c-127">Конечная точка обмена метаданными (MEX) представляет собой лишь другую конечную точку из перспективы ServiceHost, поэтому она показывается в списке.</span><span class="sxs-lookup"><span data-stu-id="5863c-127">The metadata exchange (MEX) endpoint is just another endpoint from the ServiceHost's perspective so it shows up in the list.</span></span>  
  
```  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="5863c-128">При запуске клиента запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="5863c-128">When you run the client, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="5863c-129">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="5863c-129">Press ENTER in each console window to shut down the service and client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5863c-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="5863c-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5863c-131">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5863c-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="5863c-132">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5863c-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="5863c-133">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5863c-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5863c-134">Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="5863c-134">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5863c-135">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5863c-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5863c-136">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5863c-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5863c-137">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5863c-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5863c-138">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5863c-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
  
## <a name="see-also"></a><span data-ttu-id="5863c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="5863c-139">See Also</span></span>
