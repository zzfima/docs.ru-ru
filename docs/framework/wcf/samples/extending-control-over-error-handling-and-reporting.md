---
title: Повышение управляемости обработки ошибок и формирования сообщений об ошибках
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: abb747a0deecb7e07776d9cd6ef5bc3775b1be9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281695"
---
# <a name="extending-control-over-error-handling-and-reporting"></a><span data-ttu-id="ae74b-102">Повышение управляемости обработки ошибок и формирования сообщений об ошибках</span><span class="sxs-lookup"><span data-stu-id="ae74b-102">Extending Control Over Error Handling and Reporting</span></span>
<span data-ttu-id="ae74b-103">В этом примере показано, как расширить контроль над обработкой ошибок и отчетами об ошибках в службе Windows Communication Foundation (WCF) с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="ae74b-103">This sample demonstrates how to extend control over error handling and error reporting in a Windows Communication Foundation (WCF) service using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="ae74b-104">Образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) с дополнительным кодом, добавленным в службу для обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="ae74b-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) with some additional code added to the service to handle errors.</span></span> <span data-ttu-id="ae74b-105">Клиент вызывает несколько ошибок.</span><span class="sxs-lookup"><span data-stu-id="ae74b-105">The client forces several error conditions.</span></span> <span data-ttu-id="ae74b-106">Служба перехватывает эти ошибки и регистрирует их в файле.</span><span class="sxs-lookup"><span data-stu-id="ae74b-106">The service intercepts the errors and logs them in a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae74b-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ae74b-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ae74b-108">Интерфейс <xref:System.ServiceModel.Dispatcher.IErrorHandler> позволяет службам перехватывать ошибки, обрабатывать их и определять, каким образом будут создаваться отчеты об этих ошибках.</span><span class="sxs-lookup"><span data-stu-id="ae74b-108">Services can intercept errors, perform processing, and affect how errors are reported using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="ae74b-109">Интерфейс позволяет реализовать два метода: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> и <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae74b-109">The interface has two methods that can be implemented: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> and <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span></span> <span data-ttu-id="ae74b-110">Метод <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> служит для добавления, изменения и подавления сообщений ошибках, создаваемых в результате исключений.</span><span class="sxs-lookup"><span data-stu-id="ae74b-110">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> method allows you to add, modify, or suppress a fault message that is generated in response to an exception.</span></span> <span data-ttu-id="ae74b-111">Метод <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> служит для обработки ошибки в случае ее возникновения и позволяет определять, требуется ли дополнительная обработка ошибок.</span><span class="sxs-lookup"><span data-stu-id="ae74b-111">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method allows error processing to take place in the event of an error and controls whether additional error handling can run.</span></span>  
  
 <span data-ttu-id="ae74b-112">В этом образце тип `CalculatorErrorHandler` реализует интерфейс <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="ae74b-112">In this sample, the `CalculatorErrorHandler` type implements the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="ae74b-113">В раздел</span><span class="sxs-lookup"><span data-stu-id="ae74b-113">In the</span></span>  
  
 <span data-ttu-id="ae74b-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> метод, `CalculatorErrorHandler` записывает журнал ошибок в текстовый файл Error. txt в к:\логс.</span><span class="sxs-lookup"><span data-stu-id="ae74b-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method, the `CalculatorErrorHandler` writes a log of the error to an Error.txt text file in c:\logs.</span></span> <span data-ttu-id="ae74b-115">Обратите внимание, что этот образец регистрирует ошибку в журнале и не подавляет ее, чтобы о ней можно было уведомить клиент.</span><span class="sxs-lookup"><span data-stu-id="ae74b-115">Note that the sample logs the fault and does not suppress it, allowing it to be reported back to the client.</span></span>  
  
```csharp
public class CalculatorErrorHandler : IErrorHandler
{
    // Provide a fault. The Message fault parameter can be replaced, or set to
    // null to suppress reporting a fault.

    public void ProvideFault(Exception error, MessageVersion version, ref Message fault)
    {
    }

    // HandleError. Log an error, then allow the error to be handled as usual.
    // Return true if the error is considered as already handled

    public bool HandleError(Exception error)
    {
        using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))
        {
            if (error != null)
            {
                tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);
            }
            tw.Close();
        }
        return true;
    }
}  
```  
  
 <span data-ttu-id="ae74b-116">Атрибут `ErrorBehaviorAttribute` выполняет роль механизма регистрации обработчика ошибок в службе.</span><span class="sxs-lookup"><span data-stu-id="ae74b-116">The `ErrorBehaviorAttribute` exists as a mechanism to register an error handler with a service.</span></span> <span data-ttu-id="ae74b-117">Этот атрибут принимает параметр единственного типа.</span><span class="sxs-lookup"><span data-stu-id="ae74b-117">This attribute takes a single type parameter.</span></span> <span data-ttu-id="ae74b-118">Этот тип должен быть реализацией интерфейса <xref:System.ServiceModel.Dispatcher.IErrorHandler> и должен иметь открытый пустой конструктор.</span><span class="sxs-lookup"><span data-stu-id="ae74b-118">That type should implement the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface and should have a public, empty constructor.</span></span> <span data-ttu-id="ae74b-119">В этом случае атрибут создает экземпляр типа обработчика ошибок и устанавливает его в службе.</span><span class="sxs-lookup"><span data-stu-id="ae74b-119">The attribute then instantiates an instance of that error handler type and installs it into the service.</span></span> <span data-ttu-id="ae74b-120">Для этого он реализует интерфейс <xref:System.ServiceModel.Description.IServiceBehavior> и с помощью метода <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> добавляет экземпляры в обработчик ошибок в службе.</span><span class="sxs-lookup"><span data-stu-id="ae74b-120">It does this by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface and then using the <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> method to add instances of the error handler to the service.</span></span>  
  
```csharp
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }                                                  
    }  
}  
```  
  
 <span data-ttu-id="ae74b-121">Этот образец реализует службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="ae74b-121">The sample implements a calculator service.</span></span> <span data-ttu-id="ae74b-122">Клиент намеренно вызывает в службе две ошибки путем предоставления параметров с недопустимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="ae74b-122">The client deliberately causes two errors to occur on the service by providing parameters with illegal values.</span></span> <span data-ttu-id="ae74b-123">`CalculatorErrorHandler` с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IErrorHandler> записывает ошибки в локальный файл и позволяет уведомить клиент об этих ошибках.</span><span class="sxs-lookup"><span data-stu-id="ae74b-123">The `CalculatorErrorHandler` uses the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface to log the errors to a local file and then allows them to be reported back to the client.</span></span> <span data-ttu-id="ae74b-124">Клиент вызывает ошибки типа "деление на ноль" и "аргумент вне диапазона".</span><span class="sxs-lookup"><span data-stu-id="ae74b-124">The client forces a divide by zero and an argument-out-of-range condition.</span></span>  
  
```csharp
try
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 <span data-ttu-id="ae74b-125">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="ae74b-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ae74b-126">При этом будут появляться ошибки типа "деление на ноль" и "аргумент вне диапазона".</span><span class="sxs-lookup"><span data-stu-id="ae74b-126">You see the division by zero and the argument-out-of-range conditions being reported as faults.</span></span> <span data-ttu-id="ae74b-127">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="ae74b-127">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="ae74b-128">Файл c:\logs\errors.txt содержит записанные службой сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ae74b-128">The file c:\logs\errors.txt contains the information logged about the errors by the service.</span></span> <span data-ttu-id="ae74b-129">Обратите внимание, что для записи в каталог в службе необходимо убедиться в том, что процесс, в котором запущена служба (обычно ASP.NET или Network Service), имеет разрешение на запись в каталог.</span><span class="sxs-lookup"><span data-stu-id="ae74b-129">Note that for the service to write to the directory you must make sure that the process under which the service is running (typically ASP.NET or Network Service) has permission to write to the directory.</span></span>  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ae74b-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ae74b-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ae74b-131">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ae74b-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ae74b-132">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ae74b-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ae74b-133">Проверьте, что создан каталог c:\logs для файла error.txt.</span><span class="sxs-lookup"><span data-stu-id="ae74b-133">Ensure you have created the c:\logs directory for the error.txt file.</span></span> <span data-ttu-id="ae74b-134">Либо измените имя файла, используемое в `CalculatorErrorHandler.HandleError`.</span><span class="sxs-lookup"><span data-stu-id="ae74b-134">Or modify the file name used in `CalculatorErrorHandler.HandleError`.</span></span>  
  
4. <span data-ttu-id="ae74b-135">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ae74b-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ae74b-136">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae74b-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae74b-137">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ae74b-137">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="ae74b-138">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="ae74b-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae74b-139">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ae74b-139">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
