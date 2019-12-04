---
title: Несколько контрактов
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: d8e86682e18d0319476d33c16d3caa5a4337f983
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714748"
---
# <a name="multiple-contracts"></a><span data-ttu-id="67ea3-102">Несколько контрактов</span><span class="sxs-lookup"><span data-stu-id="67ea3-102">Multiple Contracts</span></span>
<span data-ttu-id="67ea3-103">В образце нескольких контрактов показано, как реализовать для службы более одного контракта и как настроить конечные точки для взаимодействия с каждым из реализованных контрактов.</span><span class="sxs-lookup"><span data-stu-id="67ea3-103">The Multiple Contracts sample demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span> <span data-ttu-id="67ea3-104">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="67ea3-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="67ea3-105">Служба была изменена, чтобы в ней было определено два контракта - контракт `ICalculator` и контракт `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="67ea3-105">The service has been modified to define two contracts, the `ICalculator` contract and the `ICalculatorSession` contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67ea3-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="67ea3-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="67ea3-107">Класс службы реализует контракты `ICalculator` и `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="67ea3-107">The service class implements both the `ICalculator` and `ICalculatorSession` contracts.</span></span> <span data-ttu-id="67ea3-108">Поскольку одному из контрактов требуется сеанс, служба использует режим экземпляра <xref:System.ServiceModel.InstanceContextMode.PerSession> для поддержки состояния в течение времени существования сеанса.</span><span class="sxs-lookup"><span data-stu-id="67ea3-108">Because one of the contracts requires a session, the service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the state over the lifetime of the session.</span></span>  
  
 <span data-ttu-id="67ea3-109">Конфигурация службы была изменена, чтобы в ней определялось две конечных точки для обоих контрактов.</span><span class="sxs-lookup"><span data-stu-id="67ea3-109">The service configuration has been modified to define two endpoints to expose each contract.</span></span> <span data-ttu-id="67ea3-110">Конечная `ICalculator` точка доступна по базовому адресу с использованием привязки `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="67ea3-110">The `ICalculator` endpoint is exposed at the base address using a `basicHttpBinding`.</span></span> <span data-ttu-id="67ea3-111">Конечная точка `ICalculatorSession` доступна по адресу "базовый_адрес/сеанс" с использованием привязки `wsHttpBinding`, атрибут `bindingConfiguration` которой имеет значение `BindingWithSession`, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="67ea3-111">The `ICalculatorSession` endpoint is exposed at the baseaddress/session using a `wsHttpBinding` with the `bindingConfiguration` attribute set to `BindingWithSession`, as shown in the following sample configuration.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="67ea3-112">Теперь созданный код клиента содержит клиентский класс как для исходного контракта `ICalculator`, так и для нового контракта `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="67ea3-112">The generated client code now includes a client class for both the original `ICalculator` contract and the new `ICalculatorSession` contract.</span></span> <span data-ttu-id="67ea3-113">Конфигурация и код клиента были изменены, чтобы он мог взаимодействовать с каждым из контрактов через соответствующую конечную точку службы.</span><span class="sxs-lookup"><span data-stu-id="67ea3-113">The client configuration and code have been modified to communicate with each contract at the appropriate service endpoint.</span></span>  
  
 <span data-ttu-id="67ea3-114">Клиент является консольным приложением Windows (EXE).</span><span class="sxs-lookup"><span data-stu-id="67ea3-114">The client is a console windows application (.exe).</span></span> <span data-ttu-id="67ea3-115">Служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="67ea3-115">The service is hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="67ea3-116">В окне консольного приложения клиента отображаются операции, передаваемые в каждую из конечных точек, сначала для базовой конечной точки, а затем для защищенной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="67ea3-116">The client console window displays the operations sent to each of the endpoints, first the basic endpoint, followed by the secure endpoint.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="67ea3-117">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="67ea3-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="67ea3-118">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="67ea3-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="67ea3-119">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="67ea3-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="67ea3-120">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="67ea3-120">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="67ea3-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="67ea3-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="67ea3-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="67ea3-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="67ea3-123">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="67ea3-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="67ea3-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="67ea3-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
