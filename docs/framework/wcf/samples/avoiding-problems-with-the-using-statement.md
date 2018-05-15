---
title: Предотвращение проблем при использовании операторов
ms.date: 03/30/2017
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 14a0649c9996158f1503581c906d8dfd1a95ebc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="avoiding-problems-with-the-using-statement"></a><span data-ttu-id="e5c8c-102">Предотвращение проблем при использовании операторов</span><span class="sxs-lookup"><span data-stu-id="e5c8c-102">Avoiding Problems with the Using Statement</span></span>
<span data-ttu-id="e5c8c-103">В этом образце показано, как не следует использовать оператор "using" в C# для автоматической очистки ресурсов при использовании типизированного клиента.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-103">This sample demonstrates how you should not use the C# "using" statement to automatically clean up resources when using a typed client.</span></span> <span data-ttu-id="e5c8c-104">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="e5c8c-105">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5c8c-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e5c8c-107">В этом образце показаны две общие проблемы, которые могут возникнуть при использовании оператора "using" в C# с типизированными клиентами, а также код, который правильно выполняет очистку после исключений.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-107">This sample shows two of the common problems that occur when using the C# "using" statement with typed clients, as well as code that correctly cleans up after exceptions.</span></span>  
  
 <span data-ttu-id="e5c8c-108">Оператор "using" в C# приводит к вызову метода `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="e5c8c-108">The C# "using" statement results in a call to `Dispose`().</span></span> <span data-ttu-id="e5c8c-109">Этот метод эквивалентен методу `Close`(), который может выдавать исключения при возникновении сетевой ошибки.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-109">This is the same as `Close`(), which may throw exceptions when a network error occurs.</span></span> <span data-ttu-id="e5c8c-110">Поскольку вызов метода `Dispose`() выполняется неявно в закрывающей круглой скобке блока "using", этот источник исключений, скорее всего, останется незамеченным как теми, кто пишет код, так и теми, кто его считывает.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-110">Because the call to `Dispose`() happens implicitly at the closing brace of the "using" block, this source of exceptions is likely to go unnoticed both by people writing the code and reading the code.</span></span> <span data-ttu-id="e5c8c-111">Он представляет собой потенциальный источник ошибок приложения.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-111">This represents a potential source of application errors.</span></span>  
  
 <span data-ttu-id="e5c8c-112">Первая проблема, показанная в методе `DemonstrateProblemUsingCanThrow`, заключается в том, что закрывающая круглая скобка выдает исключение, а код после закрывающей круглой скобки не выполняет следующее.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-112">The first problem, illustrated in the `DemonstrateProblemUsingCanThrow` method, is that the closing brace throws an exception and the code after the closing brace does not execute:</span></span>  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 <span data-ttu-id="e5c8c-113">Даже если ничего в блоке "using" не выдает исключения или все исключения в блоке "using" перехватываются, `Console.Writeline` может не произойти, поскольку неявный вызов метода `Dispose`() в закрывающей круглой скобке может выдать исключение.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-113">Even if nothing inside the using block throws an exception or all exceptions inside the using block are caught, the `Console.Writeline` might not happen because the implicit `Dispose`() call at the closing brace might throw an exception.</span></span>  
  
 <span data-ttu-id="e5c8c-114">Вторая проблема, показанная в методе `DemonstrateProblemUsingCanThrowAndMask`, представляет собой еще одно последствие использования закрывающей круглой скобки, выдающей исключение.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-114">The second problem, illustrated in the `DemonstrateProblemUsingCanThrowAndMask` method, is another implication of the closing brace throwing an exception:</span></span>  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 <span data-ttu-id="e5c8c-115">Поскольку метод `Dispose`() происходит в блоке "finally", исключение `ApplicationException` никогда не видно за пределами блока "using", если метод `Dispose`() выполняется с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-115">Because the `Dispose`() occurs inside a "finally" block, the `ApplicationException` is never seen outside the using block if the `Dispose`() fails.</span></span> <span data-ttu-id="e5c8c-116">Если внешний код должен знать, когда происходит исключение `ApplicationException`, конструкция "using" может стать причиной возникновения проблем, маскируя это исключение.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-116">If the code outside must know about when the `ApplicationException` occurs, the "using" construct may cause problems by masking this exception.</span></span>  
  
 <span data-ttu-id="e5c8c-117">Наконец, в этом образце показано, как правильно выполнить очистку, если исключения происходят в `DemonstrateCleanupWithExceptions`.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-117">Finally, the sample demonstrates how to clean up correctly when exceptions occur in `DemonstrateCleanupWithExceptions`.</span></span> <span data-ttu-id="e5c8c-118">При этом используется блок try/catch для сообщения об ошибках и вызова метода `Abort`.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-118">This uses a try/catch block to report errors and call `Abort`.</span></span> <span data-ttu-id="e5c8c-119">В разделе [ожидаемого исключения](../../../../docs/framework/wcf/samples/expected-exceptions.md) образец Дополнительные сведения о перехвате исключений из вызовов клиента.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-119">See the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample for more details about catching exceptions from client calls.</span></span>  
  
```csharp   
try  
{  
    ...  
    client.Close();  
}  
catch (CommunicationException e)  
{  
    ...  
    client.Abort();  
}  
catch (TimeoutException e)  
{  
    ...  
    client.Abort();  
}  
catch (Exception e)  
{  
    ...  
    client.Abort();  
    throw;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="e5c8c-120">Оператор "using" и ServiceHost. Большинство резидентных приложений не только размещают службу, а метод ServiceHost.Close редко выдает исключение, поэтому такие приложения могут безопасно использовать оператор "using" с ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-120">The using statement and ServiceHost: Many self-hosting applications do little more than host a service, and ServiceHost.Close rarely throws an exception, so such applications can safely use the using statement with ServiceHost.</span></span> <span data-ttu-id="e5c8c-121">Однако необходимо помнить, что метод ServiceHost.Close может выдать исключение `CommunicationException`, поэтому если приложение продолжает работать после закрытия ServiceHost, следует избегать использования оператора "using" и следовать шаблону, указанному ранее.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-121">However, be aware that ServiceHost.Close can throw a `CommunicationException`, so if your application continues after closing the ServiceHost, you should avoid the using statement and follow the pattern previously given.</span></span>  
  
 <span data-ttu-id="e5c8c-122">При выполнении образца ответы и исключения операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-122">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="e5c8c-123">Клиентский процесс выполняет три сценария, каждый из которых пытается вызвать метод `Divide`.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-123">The client process runs three scenarios, each of which attempts to call `Divide`.</span></span> <span data-ttu-id="e5c8c-124">В первом сценарии показан код, пропущенный из-за исключения, выданного методом `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="e5c8c-124">The first scenario demonstrates code being skipped because of an exception from `Dispose`().</span></span> <span data-ttu-id="e5c8c-125">Во втором сценарии показано важное исключение с маской из-за исключения, выданного методом `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="e5c8c-125">The second scenario demonstrates an important exception being masked because of an exception from `Dispose`().</span></span> <span data-ttu-id="e5c8c-126">В третьем сценарии показана правильная очистка.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-126">The third scenario demonstrates correct clean up.</span></span>  
  
 <span data-ttu-id="e5c8c-127">Ниже представлен ожидаемый результат выполнения клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-127">The expected output from the client process is:</span></span>  
  
```  
=  
= Demonstrating problem:  closing brace of using statement can throw.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating cleanup with Exceptions.  
=  
Calling client.Add(0.0, 0.0);  
        client.Add(0.0, 0.0); returned 0  
Calling client.Divide(0.0, 0.0);  
Got System.ServiceModel.CommunicationException from Divide.  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e5c8c-128">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e5c8c-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e5c8c-129">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5c8c-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e5c8c-130">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5c8c-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e5c8c-131">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5c8c-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5c8c-132">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e5c8c-133">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e5c8c-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e5c8c-134">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e5c8c-135">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e5c8c-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## <a name="see-also"></a><span data-ttu-id="e5c8c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e5c8c-136">See Also</span></span>
