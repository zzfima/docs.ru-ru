---
title: Создание экземпляров
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, instancing sample
- Instancing Sample [Windows Communication Foundation]
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
ms.openlocfilehash: 868d88cff1c398009f136fe50f6cc3fe8c62d8e1
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715761"
---
# <a name="instancing"></a><span data-ttu-id="75887-102">Создание экземпляров</span><span class="sxs-lookup"><span data-stu-id="75887-102">Instancing</span></span>
<span data-ttu-id="75887-103">В образце создания экземпляра демонстрируется действие параметра, регулирующего способ создания экземпляров класса службы при получении запросов от клиентов.</span><span class="sxs-lookup"><span data-stu-id="75887-103">The Instancing sample demonstrates the instancing behavior setting, which controls how instances of a service class are created in response to client requests.</span></span> <span data-ttu-id="75887-104">Образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует контракт службы `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="75887-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="75887-105">В этом образце определен новый контракт `ICalculatorInstance`, производный от класса `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="75887-105">This sample defines a new contract, `ICalculatorInstance`, which inherits from `ICalculator`.</span></span> <span data-ttu-id="75887-106">Контракт, указанный для `ICalculatorInstance`, обеспечивает три дополнительные операции для проверки состояния экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="75887-106">The contract specified by `ICalculatorInstance` provides three additional operations for inspecting the state of the service instance.</span></span> <span data-ttu-id="75887-107">Изменив параметр создания экземпляров, можно запустить клиент и проверить, как изменилось поведение создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="75887-107">By altering the instancing setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="75887-108">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="75887-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75887-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="75887-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="75887-110">Доступны следующие режимы создания экземпляров:</span><span class="sxs-lookup"><span data-stu-id="75887-110">The following instancing modes are available:</span></span>  
  
- <span data-ttu-id="75887-111"><xref:System.ServiceModel.InstanceContextMode.PerCall>: создание нового экземпляра для каждого запроса клиента.</span><span class="sxs-lookup"><span data-stu-id="75887-111"><xref:System.ServiceModel.InstanceContextMode.PerCall>: A new service instance is created for each client request.</span></span>  
  
- <span data-ttu-id="75887-112"><xref:System.ServiceModel.InstanceContextMode.PerSession>: новый контекст создается для каждого нового сеанса клиента и существует в течение времени существования этого сеанса (для этого требуется привязка, поддерживающая сеанс).</span><span class="sxs-lookup"><span data-stu-id="75887-112"><xref:System.ServiceModel.InstanceContextMode.PerSession>: A new instance is created for each new client session, and maintained for the lifetime of that session (requires a binding that supports session).</span></span>  
  
- <span data-ttu-id="75887-113"><xref:System.ServiceModel.InstanceContextMode.Single>: все запросы клиентов за время существования приложения обрабатываются одним экземпляром класса службы.</span><span class="sxs-lookup"><span data-stu-id="75887-113"><xref:System.ServiceModel.InstanceContextMode.Single>: A single instance of the service class handles all client requests for the lifetime of the application.</span></span>  
  
 <span data-ttu-id="75887-114">Класс службы задает поведение создания экземпляров с помощью атрибута `[ServiceBehavior(InstanceContextMode=<setting>)]`, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="75887-114">The service class specifies instancing behavior with the `[ServiceBehavior(InstanceContextMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="75887-115">Можно проследить поведение каждого режима создания экземпляров, вставляя и удаляя символы комментирования перед различными строками кода.</span><span class="sxs-lookup"><span data-stu-id="75887-115">By changing which lines are commented out, you can observe the behavior of each of the instance modes.</span></span> <span data-ttu-id="75887-116">Не забывайте заново построить службу после изменения режима создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="75887-116">Remember to rebuild the service after changing the instancing mode.</span></span> <span data-ttu-id="75887-117">На клиенте не задаются никакие параметры, связанные с созданием экземпляров.</span><span class="sxs-lookup"><span data-stu-id="75887-117">There are no instancing-related settings to specify on the client.</span></span>  
  
```csharp
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed   
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="75887-118">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="75887-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="75887-119">Отображается режим создания экземпляров, используемый службой.</span><span class="sxs-lookup"><span data-stu-id="75887-119">The instance mode the service is running under is displayed.</span></span> <span data-ttu-id="75887-120">После каждой операции отображается идентификатор экземпляра и счетчик операций (эти величины характеризуют поведение режима создания экземпляров).</span><span class="sxs-lookup"><span data-stu-id="75887-120">After each operation, the instance ID and operation count are displayed to reflect the behavior of the instancing mode.</span></span> <span data-ttu-id="75887-121">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="75887-121">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="75887-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="75887-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="75887-123">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="75887-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="75887-124">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="75887-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="75887-125">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="75887-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="75887-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="75887-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="75887-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="75887-127">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="75887-128">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="75887-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="75887-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="75887-129">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
