---
title: Регулирование
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, throttling sample
- Throttling Sample [Windows Communication Foundation]
ms.assetid: 40bb3582-8ae9-4410-96f0-6c515bfaf47c
ms.openlocfilehash: 686cc1ef74f11cbccfeba49a642239cb6bd33204
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="throttling"></a><span data-ttu-id="f5d3b-102">Регулирование</span><span class="sxs-lookup"><span data-stu-id="f5d3b-102">Throttling</span></span>
<span data-ttu-id="f5d3b-103">В образце регулирования демонстрируется использование элементов управления регулированием.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-103">The Throttling sample demonstrates the use of throttling controls.</span></span> <span data-ttu-id="f5d3b-104">Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-104">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span> <span data-ttu-id="f5d3b-105">Поведение регулирования задается параметрами файла конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-105">Throttling behavior is specified in service configuration file settings.</span></span> <span data-ttu-id="f5d3b-106">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
 <span data-ttu-id="f5d3b-107">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5d3b-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f5d3b-109">Файл конфигурации службы задает регулирования элементов управления в [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-109">The service configuration file specifies throttling controls in a [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), as shown in the following sample configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Specify throttling behavior -->  
    <serviceThrottling maxConcurrentCalls="2"  
                       maxConcurrentInstances="10"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="f5d3b-110">В соответствии с конфигурацией служба ограничивает максимальное число параллельных вызовов двумя, а максимальное число параллельных экземпляров десятью.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-110">As configured, the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span>  
  
 <span data-ttu-id="f5d3b-111">Для демонстрации регулирования в методах службы следующим образом определяется время задержки:</span><span class="sxs-lookup"><span data-stu-id="f5d3b-111">In order to demonstrate throttling we define a sleep time on the service methods as follows:</span></span>  
  
```  
public double Add(double n1, double n2)  
{  
    System.Threading.Thread.Sleep(2000);  
    return n1 + n2;  
}  
```  
  
 <span data-ttu-id="f5d3b-112">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-112">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="f5d3b-113">Методы Add и Subtract выполняются параллельно и методы Multiply и Divide выполняются параллельно, что подтверждает, что параллельно можно выполнять не более двух методов, и является демонстрацией регулирования.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-113">The Add and Subtract methods are executed concurrently and the Multiply and Divide methods are executed concurrently proving that not more than 2 methods can be executed concurrently thus demonstrating throttling.</span></span>  
  
```  
Press <ENTER> to terminate client.  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Add Result: 115.99  
Subtract Result: 68.46  
Multiply Result: 731.25  
Divide Result: 3.14285714285714  
  
Press any key to continue . . .  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f5d3b-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="f5d3b-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f5d3b-115">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5d3b-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f5d3b-116">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5d3b-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="f5d3b-117">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5d3b-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5d3b-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5d3b-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f5d3b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f5d3b-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5d3b-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5d3b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Throttling`  
  
## <a name="see-also"></a><span data-ttu-id="f5d3b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f5d3b-122">See Also</span></span>
