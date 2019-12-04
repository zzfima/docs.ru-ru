---
title: Сеанс
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: e364b539e355f669037983813f9e6d1e0371da1f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715083"
---
# <a name="session"></a><span data-ttu-id="0d426-102">Сеанс</span><span class="sxs-lookup"><span data-stu-id="0d426-102">Session</span></span>
<span data-ttu-id="0d426-103">В образце сеанса показано, как реализовать контракт, требующий сеанс.</span><span class="sxs-lookup"><span data-stu-id="0d426-103">The Session sample demonstrates how to implement a contract that requires a session.</span></span> <span data-ttu-id="0d426-104">Сеанс обеспечивает контекст для выполнения нескольких операций.</span><span class="sxs-lookup"><span data-stu-id="0d426-104">A session provides context for performing multiple operations.</span></span> <span data-ttu-id="0d426-105">Это позволяет службе связать состояние с заданным сеансом, чтобы последующие операции могли использовать состояние предыдущей операции.</span><span class="sxs-lookup"><span data-stu-id="0d426-105">This allows a service to associate state with a given session, such that subsequent operations can use the state of a previous operation.</span></span> <span data-ttu-id="0d426-106">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="0d426-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="0d426-107">Контракт `ICalculator` был изменен, чтобы можно было выполнять набор арифметических операций с сохранением промежуточного результата.</span><span class="sxs-lookup"><span data-stu-id="0d426-107">The `ICalculator` contract has been modified to allow a set of arithmetic operations to be performed, while keeping a running result.</span></span> <span data-ttu-id="0d426-108">Эта функциональность определяется контрактом `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="0d426-108">This functionality is defined by the `ICalculatorSession` contract.</span></span> <span data-ttu-id="0d426-109">Служба поддерживает состояние клиента во время вызова нескольких операций для вычислений.</span><span class="sxs-lookup"><span data-stu-id="0d426-109">The service maintains the state for a client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="0d426-110">Клиент может извлечь текущий результат путем вызова метода `Result()` и очистить результат (сделать его равным нулю) путем вызова метода `Clear()`.</span><span class="sxs-lookup"><span data-stu-id="0d426-110">The client can retrieve the current result by calling `Result()` and clear the result to zero by calling `Clear()`.</span></span>  
  
 <span data-ttu-id="0d426-111">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="0d426-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d426-112">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="0d426-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0d426-113">Присвоение свойству <xref:System.ServiceModel.SessionMode> контракта значения `Required` гарантирует, что при предоставлении контракта через определенную привязку привязка будет поддерживать сеансы.</span><span class="sxs-lookup"><span data-stu-id="0d426-113">Setting the <xref:System.ServiceModel.SessionMode> of the contract to `Required` ensures that when the contract is exposed over a particular binding, the binding supports sessions.</span></span> <span data-ttu-id="0d426-114">Если привязка не поддерживает сеансы, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="0d426-114">If the binding does not support sessions an exception is thrown.</span></span> <span data-ttu-id="0d426-115">Интерфейс `ICalculatorSession` определяется таким образом, чтобы можно было вызывать одну или более операций, что приводит к изменению текущего результата, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="0d426-115">The `ICalculatorSession` interface is defined such that one or more operations can be called, which modifies a running result, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="0d426-116">Служба использует <xref:System.ServiceModel.InstanceContextMode> поля <xref:System.ServiceModel.InstanceContextMode.PerSession>, чтобы привязать контекст заданного экземпляра службы к каждому входящему сеансу.</span><span class="sxs-lookup"><span data-stu-id="0d426-116">The service uses a <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession> to bind a given service instance context to each incoming session.</span></span> <span data-ttu-id="0d426-117">Это позволяет службе поддерживать промежуточный результат для каждого сеанса в локальной переменной-члене.</span><span class="sxs-lookup"><span data-stu-id="0d426-117">This allows the service to maintain the running result for each session in a local member variable.</span></span>  
  
```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 <span data-ttu-id="0d426-118">При выполнении образца клиент отправляет на сервер несколько запросов и запрашивает результаты, которые затем отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="0d426-118">When you run the sample, the client makes several requests to the server and requests the result, which it then displays in the client console window.</span></span> <span data-ttu-id="0d426-119">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="0d426-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0d426-120">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="0d426-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0d426-121">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0d426-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0d426-122">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0d426-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0d426-123">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0d426-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0d426-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d426-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0d426-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0d426-125">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="0d426-126">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="0d426-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0d426-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0d426-127">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
