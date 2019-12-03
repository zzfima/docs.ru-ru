---
title: Повторный вход ConcurrencyMode
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: 0ac3b811c59abfbb3148ddad3d518443f7633adc
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714970"
---
# <a name="concurrencymode-reentrant"></a><span data-ttu-id="b701c-102">Повторный вход ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="b701c-102">ConcurrencyMode Reentrant</span></span>
<span data-ttu-id="b701c-103">Этот образец демонстрирует необходимость и последствия использования ConcurrencyMode.Reentrant в реализации службы.</span><span class="sxs-lookup"><span data-stu-id="b701c-103">This sample demonstrates the necessity and implications of using ConcurrencyMode.Reentrant on a service implementation.</span></span> <span data-ttu-id="b701c-104">Поведение ConcurrencyMode.Reentrant подразумевает, что служба (или обратный вызов) обрабатывает только одно сообщение в данный момент времени (аналогично `ConcurencyMode.Single`).</span><span class="sxs-lookup"><span data-stu-id="b701c-104">ConcurrencyMode.Reentrant implies that the service (or callback) processes only one message at a given time (analogous to `ConcurencyMode.Single`).</span></span> <span data-ttu-id="b701c-105">Чтобы обеспечить потокобезопасность, Windows Communication Foundation (WCF) блокирует `InstanceContext` обработки сообщения, чтобы никакие другие сообщения не обрабатывались.</span><span class="sxs-lookup"><span data-stu-id="b701c-105">To ensure thread safety, Windows Communication Foundation (WCF) locks the `InstanceContext` processing a message so that no other messages can be processed.</span></span> <span data-ttu-id="b701c-106">В режиме Reentrant объект `InstanceContext` разблокируется непосредственно перед тем, как служба делает исходящий вызов, что делает возможным последующий вызов (который может быть реентерабельным, как показано в этом образце), и снова блокируется при следующем его поступлении в службу.</span><span class="sxs-lookup"><span data-stu-id="b701c-106">In case of Reentrant mode, the `InstanceContext` is unlocked just before the service makes an outgoing call thereby allowing the subsequent call, (which can be reentrant as demonstrated in the sample) to get the lock next time it comes in to the service.</span></span> <span data-ttu-id="b701c-107">Для демонстрации этого поведения в образце показано, как клиент и служба могут отправлять сообщения друг другу, используя дуплексный контракт.</span><span class="sxs-lookup"><span data-stu-id="b701c-107">To demonstrate the behavior, the sample shows how a client and service can send messages between each other using a duplex contract.</span></span>  
  
 <span data-ttu-id="b701c-108">Определенный в примере контракт является дуплексным: метод `Ping` реализуется службой, а метод обратного вызова `Pong` реализуется клиентом.</span><span class="sxs-lookup"><span data-stu-id="b701c-108">The contract defined is a duplex contract with the `Ping` method being implemented by the service and the callback method `Pong` being implemented by the client.</span></span> <span data-ttu-id="b701c-109">Клиент вызывает метод `Ping` сервера со счетчиком тактов, тем самым инициируя вызов.</span><span class="sxs-lookup"><span data-stu-id="b701c-109">A client invokes the server's `Ping` method with a tick count thereby initiating the call.</span></span> <span data-ttu-id="b701c-110">Служба проверяет, отличен ли счетчик тактов от нуля, и затем вызывает метод обратного вызова `Pong`, одновременно уменьшая на единицу счетчик тактов.</span><span class="sxs-lookup"><span data-stu-id="b701c-110">The service checks whether the tick count is not equal to 0 and then invokes the callbacks `Pong` method while decrementing the tick count.</span></span> <span data-ttu-id="b701c-111">Это делает следующий код в образце.</span><span class="sxs-lookup"><span data-stu-id="b701c-111">This is done by the following code in the sample.</span></span>  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 Реализация метода `Pong` обратного вызова имеет ту же логику, что и реализация метода `Ping`. Это значит, что она сравнивает значение счетчика тактов с нулем, а затем вызывает метод `Ping` по каналу обратного вызова (в данном случае это канал, который использовался для отправки исходного сообщения `Ping`), уменьшая счетчик тактов на 1. Когда счетчик тактов достигает 0, метод завершает работу, возвращая все ответы в первый вызов, выполненный клиентом, который запустил вызов. <span data-ttu-id="b701c-115">Это показано в реализации обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="b701c-115">This is shown in the callback implementation.</span></span>  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 И метод `Ping`, и метод `Pong` работают по шаблону "запрос-ответ", что означает, что первый вызов метода `Ping` не возвращается, пока не будет возвращен вызов метода `CallbackChannel<T>.Pong()`. <span data-ttu-id="b701c-117">На стороне клиента метод `Pong` не может возвратиться до тех пор, пока не будет возвращен следующий сделанный им вызов метода `Ping`.</span><span class="sxs-lookup"><span data-stu-id="b701c-117">On the client, the `Pong` method cannot return until the next `Ping` call that it made returns.</span></span> <span data-ttu-id="b701c-118">Поскольку и обратный вызов, и служба должны делать исходящие вызовы "запрос-ответ", прежде чем они смогут ответить на ожидающий запрос, обе реализации должны быть отмечены поведением ConcurrencyMode.Reentrant.</span><span class="sxs-lookup"><span data-stu-id="b701c-118">Because both the callback and the service must make outgoing request/reply calls before they can reply for the pending request, both the implementations must be marked with the ConcurrencyMode.Reentrant behavior.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b701c-119">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="b701c-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b701c-120">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b701c-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b701c-121">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b701c-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b701c-122">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b701c-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b701c-123">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="b701c-123">Demonstrates</span></span>  
 <span data-ttu-id="b701c-124">Чтобы выполнить образец, постройте клиентский и серверный проекты.</span><span class="sxs-lookup"><span data-stu-id="b701c-124">To run the sample, build the client and server projects.</span></span> <span data-ttu-id="b701c-125">Затем откройте две командные окна и измените каталоги на \<Sample > \Кс\сервице\бин\дебуг и \<Sample > \Кс\клиент\бин\дебуг directorys.</span><span class="sxs-lookup"><span data-stu-id="b701c-125">Then open two command windows and change the directories to the \<sample>\CS\Service\bin\debug and \<sample>\CS\Client\bin\debug directories.</span></span> <span data-ttu-id="b701c-126">Затем запустите службу, введя `service.exe` и вызовите Client. exe с начальным значением тактов, переданным в качестве входного аргумента.</span><span class="sxs-lookup"><span data-stu-id="b701c-126">Then start the service by typing `service.exe` and then invoke the Client.exe with the initial value of ticks passed as an input argument.</span></span> <span data-ttu-id="b701c-127">Ниже показаны результаты выполнения для количества тактов, равного 10.</span><span class="sxs-lookup"><span data-stu-id="b701c-127">A sample output for 10 ticks is shown.</span></span>  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="b701c-128">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b701c-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b701c-129">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b701c-129">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="b701c-130">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="b701c-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b701c-131">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b701c-131">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
