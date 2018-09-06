---
title: Активация на основе конфигурации
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: e016dffdaf93b222c1fd2380bfa175256b009068
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43742320"
---
# <a name="configuration-based-activation"></a><span data-ttu-id="73acb-102">Активация на основе конфигурации</span><span class="sxs-lookup"><span data-stu-id="73acb-102">Configuration-Based Activation</span></span>
<span data-ttu-id="73acb-103">В этом примере показано, как активировать службы Windows Communication Foundation (WCF) без использования SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="73acb-103">This sample demonstrates how to activate Windows Communication Foundation (WCF) services without requiring a .svc file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73acb-104">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="73acb-104">The samples may already be installed on your computer.</span></span> <span data-ttu-id="73acb-105">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="73acb-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="73acb-106">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="73acb-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="73acb-107">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="73acb-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="73acb-108">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="73acb-108">Sample Details</span></span>  
 <span data-ttu-id="73acb-109">В этом образце клиентом является тестовый клиент WCF, а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="73acb-109">In this sample, the client is the WCF test client and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73acb-110">Инструкции по настройке и построению этого образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="73acb-110">The setup and build instructions for this sample are located at the end of this topic.</span></span>  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a><span data-ttu-id="73acb-111">Активация служб без использования SVC-файла</span><span class="sxs-lookup"><span data-stu-id="73acb-111">Activation of services without requiring a .svc file</span></span>  
 <span data-ttu-id="73acb-112">В [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] для активации служб необходим SVC-файл.</span><span class="sxs-lookup"><span data-stu-id="73acb-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], a .svc file was required for activating a service.</span></span> <span data-ttu-id="73acb-113">Это привело к появлению дополнительных затрат на управление, поскольку требовалось выполнить развертывание дополнительного файла, который необходимо поддерживать вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="73acb-113">This caused additional management overhead, because an additional file was required to be deployed and maintained along with the application.</span></span> <span data-ttu-id="73acb-114">В выпуске [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] компоненты активации можно настроить с помощью файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="73acb-114">With the release of [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], the activation components can be configured using the application configuration file.</span></span>  
  
 <span data-ttu-id="73acb-115">В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] реализован новый элемент конфигурации (<xref:System.ServiceModel.Configuration.ServiceActivationElement>) в разделе <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="73acb-115">[!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] introduces a new configuration element (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in the <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> of the application configuration file.</span></span> <span data-ttu-id="73acb-116">Коллекция <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> принимает коллекцию служб для активации, как показано в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="73acb-116">The <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> collection accepts a collection of services to activate, as shown in the following code example.</span></span>  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 <span data-ttu-id="73acb-117">Необходимо отметить, что конфигурация схожа с конфигурацией SVC-файлов.</span><span class="sxs-lookup"><span data-stu-id="73acb-117">The observation to make is the configuration looks very similar to the configuration of .svc files.</span></span> <span data-ttu-id="73acb-118">Также реализуется дополнительный атрибут `relativeAddress`, предоставляющий адрес службы.</span><span class="sxs-lookup"><span data-stu-id="73acb-118">An additional attribute that is introduced is the `relativeAddress` that provides the address of the service.</span></span> <span data-ttu-id="73acb-119">Относительный адрес также является виртуальным путем службы.</span><span class="sxs-lookup"><span data-stu-id="73acb-119">The relative address is also the virtual path for the service.</span></span> <span data-ttu-id="73acb-120">Узел извлекает файл Web.config из файла в местоположении `virtualPath` (если имеется), в противном случае узел выполняет рекурсивный поиск родительской папки.</span><span class="sxs-lookup"><span data-stu-id="73acb-120">The host retrieves the Web.config file of the file from the `virtualPath` location, if present; otherwise the host searches its parent folder recursively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73acb-121">Для работы этого образца требуется размещение в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="73acb-121">This sample requires hosting in IIS to function.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="73acb-122">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="73acb-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="73acb-123">Используйте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], чтобы открыть файл Service.csproj.</span><span class="sxs-lookup"><span data-stu-id="73acb-123">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Service.csproj file.</span></span>  
  
2.  <span data-ttu-id="73acb-124">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="73acb-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="73acb-125">Проверьте службу, запустив WCFTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="73acb-125">Test the service by running WCFTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="73acb-126">С помощью [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] найдите папку %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="73acb-126">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE folder.</span></span>  
  
5.  <span data-ttu-id="73acb-127">Запустите файл WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="73acb-127">Run WcfTestClient.exe.</span></span>  
  
6.  <span data-ttu-id="73acb-128">Задайте адрес MEX службы.</span><span class="sxs-lookup"><span data-stu-id="73acb-128">Set the MEX address of the service.</span></span>  
  
7.  <span data-ttu-id="73acb-129">Нажмите CTRL+SHIFT+A, чтобы задать адрес службы.</span><span class="sxs-lookup"><span data-stu-id="73acb-129">Press CTRL+SHIFT+A to set the service address.</span></span>  
  
8.  <span data-ttu-id="73acb-130">Задайте адрес http://localhost/ServiceModelSamples/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="73acb-130">Set the address to http://localhost/ServiceModelSamples/Calculator.svc.</span></span>  
  
9. <span data-ttu-id="73acb-131">Выполните операцию `Add`.</span><span class="sxs-lookup"><span data-stu-id="73acb-131">Perform the `Add` operation.</span></span> <span data-ttu-id="73acb-132">Задайте для параметра `n1` значение, равное 10, а для параметра `n2` значение, равное 15.</span><span class="sxs-lookup"><span data-stu-id="73acb-132">Set value on the `n1` parameter to 10 and set value on the `n2` parameter to 15.</span></span>  
  
10. <span data-ttu-id="73acb-133">Нажмите клавишу **вызова**.</span><span class="sxs-lookup"><span data-stu-id="73acb-133">Press **Invoke**.</span></span>  
  
     <span data-ttu-id="73acb-134">Ожидаемым результатом является 25.</span><span class="sxs-lookup"><span data-stu-id="73acb-134">The expected result is 25.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="73acb-135">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="73acb-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="73acb-136">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="73acb-136">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="73acb-137">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="73acb-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="73acb-138">После построения решения запустите файл Setup.bat, чтобы настроить приложение ServiceModelSamples в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="73acb-138">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS.</span></span> <span data-ttu-id="73acb-139">Теперь каталог ServiceModelSamples должен представляться как приложение IIS.</span><span class="sxs-lookup"><span data-stu-id="73acb-139">The ServiceModelSamples directory should now appear as an IIS Application.</span></span>  
  
4.  <span data-ttu-id="73acb-140">Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="73acb-140">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73acb-141">См. также</span><span class="sxs-lookup"><span data-stu-id="73acb-141">See Also</span></span>  
 [<span data-ttu-id="73acb-142">Образцы размещения AppFabric и сохраняемости</span><span class="sxs-lookup"><span data-stu-id="73acb-142">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
