---
title: Поведение служб по умолчанию
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, defaults
- Default Service Behavior Sample [Windows Communication Foundation]
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
ms.openlocfilehash: 8583c74f85d9638313db1779610c0f6dac9cfbe5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486978"
---
# <a name="default-service-behavior"></a><span data-ttu-id="55d24-102">Поведение служб по умолчанию</span><span class="sxs-lookup"><span data-stu-id="55d24-102">Default Service Behavior</span></span>
<span data-ttu-id="55d24-103">В этом образце показано, как могут настраиваться параметры поведения службы.</span><span class="sxs-lookup"><span data-stu-id="55d24-103">This sample demonstrates how service behavior settings can be configured.</span></span> <span data-ttu-id="55d24-104">Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует `ICalculator` контракт службы.</span><span class="sxs-lookup"><span data-stu-id="55d24-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="55d24-105">В этом образце с помощью атрибутов <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> явным образом определены поведения службы и операции.</span><span class="sxs-lookup"><span data-stu-id="55d24-105">This sample explicitly defines service behaviors and operation behaviors using the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes.</span></span> <span data-ttu-id="55d24-106">Поведения можно настраивать в файлах конфигурации или непосредственно в коде (как показано в этом образце).</span><span class="sxs-lookup"><span data-stu-id="55d24-106">You can configure behaviors in configuration files or imperatively in code (as this sample demonstrates).</span></span>  
  
 <span data-ttu-id="55d24-107">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="55d24-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55d24-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="55d24-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="55d24-109">Класс службы задает поведение с помощью атрибутов <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute>, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="55d24-109">The service class specifies behaviors with the <xref:System.ServiceModel.ServiceBehaviorAttribute> and the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following code sample.</span></span> <span data-ttu-id="55d24-110">Все заданные значения являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="55d24-110">All values specified are the defaults.</span></span>  
  
```  
[ServiceBehavior(  
    AutomaticSessionShutdown=true,  
    ConcurrencyMode=ConcurrencyMode.Single,  
    InstanceContextMode=InstanceContextMode.PerSession,  
    IncludeExceptionDetailInFaults=false,  
    UseSynchronizationContext=true,  
    ValidateMustUnderstand=true)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(  
        TransactionAutoComplete=true,  
        TransactionScopeRequired=false,  
        Impersonation=ImpersonationOption.NotAllowed)]  
    public double Add(double n1, double n2)  
    {  
        System.Threading.Thread.Sleep(1600);  
        return n1 + n2;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="55d24-111">Поведения службы задаются атрибутом <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="55d24-111">Service behaviors are specified with the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span> <span data-ttu-id="55d24-112">В приведенной ниже таблице описаны некоторые из этих поведений.</span><span class="sxs-lookup"><span data-stu-id="55d24-112">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="55d24-113">Поведение службы</span><span class="sxs-lookup"><span data-stu-id="55d24-113">Service behavior</span></span>|<span data-ttu-id="55d24-114">Описание</span><span class="sxs-lookup"><span data-stu-id="55d24-114">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|<span data-ttu-id="55d24-115">Автоматически завершает сеанс по запросу клиента.</span><span class="sxs-lookup"><span data-stu-id="55d24-115">Automatically shuts down a session at the client's request.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|<span data-ttu-id="55d24-116">Задает режим параллелизма для каждого из экземпляров служб.</span><span class="sxs-lookup"><span data-stu-id="55d24-116">Specifies the concurrency mode for each service instance.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|<span data-ttu-id="55d24-117">Задает режим контекста экземпляра.</span><span class="sxs-lookup"><span data-stu-id="55d24-117">Specifies the instance context mode.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|<span data-ttu-id="55d24-118">Определяет, нужно ли использовать предоставляемый контекст синхронизации, если он задан.</span><span class="sxs-lookup"><span data-stu-id="55d24-118">Determines whether to use the provided synchronization context, if one is set.</span></span> <span data-ttu-id="55d24-119">Его следует использовать, если требуется определить, нужно ли использовать `WindowsFormsSynchronizationContext` в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="55d24-119">Use this when you want to control whether to use a `WindowsFormsSynchronizationContext` in Windows Forms applications.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|<span data-ttu-id="55d24-120">Определяет, что общие необработанные исключения выполнения должны преобразовываться в `Fault<string>` и отправляться как сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="55d24-120">Determines whether general unhandled execution exceptions are to be converted into a `Fault<string>` and sent as a fault message.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|<span data-ttu-id="55d24-121">Задает уровень изоляции транзакций.</span><span class="sxs-lookup"><span data-stu-id="55d24-121">Specifies the isolation level for transactions.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|<span data-ttu-id="55d24-122">Определяет, вызывают ли неожиданные заголовки сообщений ошибку.</span><span class="sxs-lookup"><span data-stu-id="55d24-122">Determines whether unexpected message headers cause an error condition.</span></span>|  
  
 <span data-ttu-id="55d24-123">Поведения операций задаются атрибутом <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="55d24-123">Operation behaviors are specified by using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="55d24-124">В приведенной ниже таблице описаны некоторые из этих поведений.</span><span class="sxs-lookup"><span data-stu-id="55d24-124">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="55d24-125">Поведение операции</span><span class="sxs-lookup"><span data-stu-id="55d24-125">Operation Behavior</span></span>|<span data-ttu-id="55d24-126">Описание</span><span class="sxs-lookup"><span data-stu-id="55d24-126">Description</span></span>|  
|------------------------|-----------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|<span data-ttu-id="55d24-127">Определяет, приводит ли завершение операции службы к завершению текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="55d24-127">Determines whether service operation completion commits the current transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|<span data-ttu-id="55d24-128">Определяет, зачислятся ли операция службы в транзакции потока клиента.</span><span class="sxs-lookup"><span data-stu-id="55d24-128">Determines whether the service operation enlists in a client-flowed transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|<span data-ttu-id="55d24-129">Определяет, олицетворяет ли операция службы удостоверение вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="55d24-129">Determines whether the service operation impersonates the caller's identity.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|<span data-ttu-id="55d24-130">Определяет, удаляются ли экземпляры служб при начале и завершении вызова операции службы.</span><span class="sxs-lookup"><span data-stu-id="55d24-130">Determines whether service instances are recycled at the start or end of the service operation call.</span></span>|  
  
 <span data-ttu-id="55d24-131">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="55d24-131">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="55d24-132">Задержка между вызовами связана с вызовами метода `System.Threading.Thread.Sleep()` в операциях службы.</span><span class="sxs-lookup"><span data-stu-id="55d24-132">The delay between the calls is the result of the calls to `System.Threading.Thread.Sleep()` made in the service operations.</span></span> <span data-ttu-id="55d24-133">В остальных образцах поведений эти поведения описаны более подробно.</span><span class="sxs-lookup"><span data-stu-id="55d24-133">The rest of the behavior samples explain these behaviors in more detail.</span></span> <span data-ttu-id="55d24-134">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="55d24-134">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="55d24-135">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="55d24-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="55d24-136">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55d24-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="55d24-137">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55d24-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="55d24-138">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55d24-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="55d24-139">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="55d24-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="55d24-140">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="55d24-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="55d24-141">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="55d24-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="55d24-142">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="55d24-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
  
## <a name="see-also"></a><span data-ttu-id="55d24-143">См. также</span><span class="sxs-lookup"><span data-stu-id="55d24-143">See Also</span></span>
