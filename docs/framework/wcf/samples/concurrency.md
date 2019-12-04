---
title: Параллельность
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
ms.openlocfilehash: 1342e50a5dca56260f832f5e0d684f4f79d355e2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715987"
---
# <a name="concurrency"></a><span data-ttu-id="47a1f-102">Параллельность</span><span class="sxs-lookup"><span data-stu-id="47a1f-102">Concurrency</span></span>
<span data-ttu-id="47a1f-103">Образец Concurrency демонстрирует использование <xref:System.ServiceModel.ServiceBehaviorAttribute> с перечислением <xref:System.ServiceModel.ConcurrencyMode>, определяющим, будет ли экземпляр службы обрабатывать сообщения последовательно или параллельно.</span><span class="sxs-lookup"><span data-stu-id="47a1f-103">The Concurrency sample demonstrates using the <xref:System.ServiceModel.ServiceBehaviorAttribute> with the <xref:System.ServiceModel.ConcurrencyMode> enumeration, which controls whether an instance of a service processes messages sequentially or concurrently.</span></span> <span data-ttu-id="47a1f-104">Образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует контракт службы `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="47a1f-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="47a1f-105">Этот образец определяет новый контракт, `ICalculatorConcurrency`, унаследованный от `ICalculator`, который добавляет две операции для контроля состояния параллелизма службы.</span><span class="sxs-lookup"><span data-stu-id="47a1f-105">This sample defines a new contract, `ICalculatorConcurrency`, which inherits from `ICalculator`, providing two additional operations for inspecting the state of the service concurrency.</span></span> <span data-ttu-id="47a1f-106">Изменив параметр параллелизма, можно запустить клиент и посмотреть, как изменилось поведение.</span><span class="sxs-lookup"><span data-stu-id="47a1f-106">By altering the concurrency setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="47a1f-107">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="47a1f-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47a1f-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="47a1f-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="47a1f-109">Доступны три режима параллелизма.</span><span class="sxs-lookup"><span data-stu-id="47a1f-109">There are three concurrency modes available:</span></span>  
  
- <span data-ttu-id="47a1f-110">`Single`: все экземпляры службы обрабатывают в данный момент времени одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="47a1f-110">`Single`: Each service instance processes one message at a time.</span></span> <span data-ttu-id="47a1f-111">Это режим параллелизма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47a1f-111">This is the default concurrency mode.</span></span>  
  
- <span data-ttu-id="47a1f-112">`Multiple`: каждый экземпляр службы обрабатывает несколько сообщений параллельно.</span><span class="sxs-lookup"><span data-stu-id="47a1f-112">`Multiple`: Each service instance processes multiple messages concurrently.</span></span> <span data-ttu-id="47a1f-113">Чтобы использовать этот режим параллелизма, реализация службы должна быть потокобезопасной.</span><span class="sxs-lookup"><span data-stu-id="47a1f-113">The service implementation must be thread-safe to use this concurrency mode.</span></span>  
  
- <span data-ttu-id="47a1f-114">`Reentrant`: каждый экземпляр службы одновременно обрабатывает одно сообщение, но принимает вызовы с повторным входом.</span><span class="sxs-lookup"><span data-stu-id="47a1f-114">`Reentrant`: Each service instance processes one message at a time, but accepts reentrant calls.</span></span> <span data-ttu-id="47a1f-115">Служба принимает эти вызовы только при вызове. Повторный вход показан в образце [ConcurrencyMode.](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md) повторного входа.</span><span class="sxs-lookup"><span data-stu-id="47a1f-115">The service only accepts these calls when it is calling out. Reentrant is demonstrated in the [ConcurrencyMode.Reentrant](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md) sample.</span></span>  
  
 <span data-ttu-id="47a1f-116">Использование параллелизма связано с режимом создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="47a1f-116">The use of concurrency is related to the instancing mode.</span></span> <span data-ttu-id="47a1f-117">В режиме создания экземпляров <xref:System.ServiceModel.InstanceContextMode.PerCall> параллелизм не имеет значения, так как каждое сообщение обрабатывается новым экземпляром службы.</span><span class="sxs-lookup"><span data-stu-id="47a1f-117">In <xref:System.ServiceModel.InstanceContextMode.PerCall> instancing, concurrency is not relevant, because each message is processed by a new service instance.</span></span> <span data-ttu-id="47a1f-118">В режиме создания экземпляров <xref:System.ServiceModel.InstanceContextMode.Single> имеет значение параллелизм <xref:System.ServiceModel.ConcurrencyMode.Single> или <xref:System.ServiceModel.ConcurrencyMode.Multiple>, в зависимости от того, обрабатывает ли один экземпляр сообщения последовательно или параллельно.</span><span class="sxs-lookup"><span data-stu-id="47a1f-118">In <xref:System.ServiceModel.InstanceContextMode.Single> instancing, either <xref:System.ServiceModel.ConcurrencyMode.Single> or <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency is relevant, depending on whether the single instance processes messages sequentially or concurrently.</span></span> <span data-ttu-id="47a1f-119">В режиме создания экземпляров <xref:System.ServiceModel.InstanceContextMode.PerSession> могут иметь значение любые режимы параллелизма.</span><span class="sxs-lookup"><span data-stu-id="47a1f-119">In <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing, any of the concurrency modes may be relevant.</span></span>  
  
 <span data-ttu-id="47a1f-120">Класс службы задает поведение параллелизма с помощью атрибута `[ServiceBehavior(ConcurrencyMode=<setting>)]`, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="47a1f-120">The service class specifies concurrency behavior with the `[ServiceBehavior(ConcurrencyMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="47a1f-121">Преобразуя в комментарий различные строки, можно поэкспериментировать с режимами параллелизма `Single` и `Multiple`.</span><span class="sxs-lookup"><span data-stu-id="47a1f-121">By changing which lines are commented out, you can experiment with the `Single` and `Multiple` concurrency modes.</span></span> <span data-ttu-id="47a1f-122">Не забывайте строить службу заново после изменения режима параллелизма.</span><span class="sxs-lookup"><span data-stu-id="47a1f-122">Remember to rebuild the service after changing the concurrency mode.</span></span>  
  
```csharp
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {     
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {     
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 <span data-ttu-id="47a1f-123">По умолчанию образец использует параллелизм <xref:System.ServiceModel.ConcurrencyMode.Multiple> с режимом создания экземпляров <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="47a1f-123">The sample uses <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency with <xref:System.ServiceModel.InstanceContextMode.Single> instancing by default.</span></span> <span data-ttu-id="47a1f-124">Код клиента изменен для использования асинхронного прокси.</span><span class="sxs-lookup"><span data-stu-id="47a1f-124">The client code has been modified to use an asynchronous proxy.</span></span> <span data-ttu-id="47a1f-125">Это позволяет клиенту направлять службе сразу несколько вызовов, не дожидаясь ответа на каждый вызов.</span><span class="sxs-lookup"><span data-stu-id="47a1f-125">This allows the client to make multiple calls to the service without waiting for a response between each call.</span></span> <span data-ttu-id="47a1f-126">Можно наблюдать различия в поведении режима параллелизма службы.</span><span class="sxs-lookup"><span data-stu-id="47a1f-126">You can observe the difference in behavior of the service concurrency mode.</span></span>  
  
 <span data-ttu-id="47a1f-127">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="47a1f-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="47a1f-128">Отображается режим параллелизма, в котором работает служба, вызываются все операции, и отображается число операций.</span><span class="sxs-lookup"><span data-stu-id="47a1f-128">The concurrency mode that the service is running under is displayed, each operation is called, and then the operation count is displayed.</span></span> <span data-ttu-id="47a1f-129">Обратите внимание, что в режиме параллельности `Multiple` результаты возвращаются в порядке, отличном от порядка вызовов, потому что служба обрабатывает несколько сообщений параллельно.</span><span class="sxs-lookup"><span data-stu-id="47a1f-129">Notice that when the concurrency mode is `Multiple`, the results are returned in a different order than how they were called, because the service processes multiple messages concurrently.</span></span> <span data-ttu-id="47a1f-130">Если изменить режим параллельности на `Single`, результаты возвращаются в порядке вызова, потому что служба обрабатывает все сообщения последовательно.</span><span class="sxs-lookup"><span data-stu-id="47a1f-130">By changing the concurrency mode to `Single`, the results are returned in the order they were called, because the service processes each message sequentially.</span></span> <span data-ttu-id="47a1f-131">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="47a1f-131">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="47a1f-132">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="47a1f-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="47a1f-133">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47a1f-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="47a1f-134">При использовании программы Svcutil. exe для создания прокси-клиента убедитесь, что включен параметр `/async`.</span><span class="sxs-lookup"><span data-stu-id="47a1f-134">If you use Svcutil.exe to generate the proxy client, ensure that you include the `/async` option.</span></span>  
  
3. <span data-ttu-id="47a1f-135">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47a1f-135">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="47a1f-136">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47a1f-136">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="47a1f-137">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="47a1f-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47a1f-138">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="47a1f-138">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="47a1f-139">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="47a1f-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47a1f-140">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="47a1f-140">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
