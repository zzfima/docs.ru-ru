---
title: Размещение в службах IIS с использованием встроенного кода
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 862ae61112db475825901f7c3f1d5127b384bb22
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711614"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="793f4-102">Размещение в службах IIS с использованием встроенного кода</span><span class="sxs-lookup"><span data-stu-id="793f4-102">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="793f4-103">Этот образец демонстрирует реализацию службы, размещенной в службах IIS, когда код службы находится в строках файла SVC и компилируется по требованию.</span><span class="sxs-lookup"><span data-stu-id="793f4-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="793f4-104">Код службы может также быть реализован непосредственно в файлах исходного кода, расположенных в каталоге \App_Code приложения, или он может быть скомпилирован в сборку, развернутую в каталоге \bin.</span><span class="sxs-lookup"><span data-stu-id="793f4-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="793f4-105">В этом примере такие приемы не демонстрируются.</span><span class="sxs-lookup"><span data-stu-id="793f4-105">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="793f4-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="793f4-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="793f4-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="793f4-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="793f4-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="793f4-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="793f4-109">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="793f4-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="793f4-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="793f4-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="793f4-111">В этом примере показана типичная служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="793f4-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="793f4-112">Служба размещается в службах IIS, а весь код службы полностью содержится в файле Service.svc.</span><span class="sxs-lookup"><span data-stu-id="793f4-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="793f4-113">Служба активируется ведущим приложением и компилируется по требованию при поступлении первого сообщения, отправленного этой службе.</span><span class="sxs-lookup"><span data-stu-id="793f4-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="793f4-114">Предварительная компиляция не требуется.</span><span class="sxs-lookup"><span data-stu-id="793f4-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="793f4-115">Служба реализует контракт `ICalculator`, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="793f4-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="793f4-116">Реализация службы выполняет вычисления и возвращает соответствующий результат.</span><span class="sxs-lookup"><span data-stu-id="793f4-116">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="793f4-117">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="793f4-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="793f4-118">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="793f4-118">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="793f4-119">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="793f4-119">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="793f4-120">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="793f4-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="793f4-121">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="793f4-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="793f4-122">После построения решения запустите программу Setup. bat, чтобы настроить приложение ServiceModelSamples в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="793f4-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="793f4-123">Теперь каталог ServiceModelSamples должен отображаться как приложение IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="793f4-123">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="793f4-124">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="793f4-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="793f4-125">Пример создания клиентского приложения, который может вызывать эту службу, см. в разделе [как создать клиент](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="793f4-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="793f4-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="793f4-126">See also</span></span>

- [<span data-ttu-id="793f4-127">Примеры размещения и сохраняемости AppFabric</span><span class="sxs-lookup"><span data-stu-id="793f4-127">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
