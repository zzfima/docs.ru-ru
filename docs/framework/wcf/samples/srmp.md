---
title: SRMP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d42c6f19091703242a730cb40495cfb073631682
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="srmp"></a><span data-ttu-id="c9d41-102">SRMP</span><span class="sxs-lookup"><span data-stu-id="c9d41-102">SRMP</span></span>
<span data-ttu-id="c9d41-103">В этом образце показано, как осуществлять транзакционное взаимодействие с использованием очередей с помощью очереди сообщений (MSMQ) по HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 <span data-ttu-id="c9d41-104">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="c9d41-104">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="c9d41-105">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="c9d41-105">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="c9d41-106">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="c9d41-106">The service receives messages from the queue.</span></span> <span data-ttu-id="c9d41-107">Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="c9d41-107">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="c9d41-108">MSMQ обеспечивает использование HTTP (включая HTTPS) для отправки сообщений в очередь.</span><span class="sxs-lookup"><span data-stu-id="c9d41-108">MSMQ enables the use of HTTP (including the use of HTTPS) to send messages to a queue.</span></span> <span data-ttu-id="c9d41-109">В этом примере показано использование взаимодействие с использованием очередей [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и отправка сообщений по HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-109">In this example, we demonstrate using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] queued communication and how to send messages over HTTP.</span></span> <span data-ttu-id="c9d41-110">MSMQ использует протокол под названием SRMP, являющийся протоколом на основе SOAP для взаимодействия по HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-110">MSMQ uses a protocol called SRMP, which is a SOAP-based protocol for communication over HTTP.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9d41-111">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="c9d41-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c9d41-112">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9d41-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c9d41-113">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9d41-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="c9d41-114">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9d41-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="c9d41-115">Перед запуском образца в **компонентов Windows**, убедитесь, что MSMQ установлен с поддержкой HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-115">Before running the sample in **Add/Remove Windows Components**, ensure that MSMQ is installed with HTTP support.</span></span> <span data-ttu-id="c9d41-116">При установке поддержки HTTP автоматически устанавливаются службы IIS и в них добавляется поддержка протокола для MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c9d41-116">Installing HTTP support automatically installs Internet Information Services (IIS) and adds the protocol support in IIS for MSMQ.</span></span>  
  
5.  <span data-ttu-id="c9d41-117">Чтобы гарантировать использование HTTP для взаимодействия, можно включить ужесточенный режим MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c9d41-117">If you want to be certain that HTTP is used for communication, you can enable MSMQ to run in hardened mode.</span></span> <span data-ttu-id="c9d41-118">Это позволит предотвратить получение сообщений в любую очередь, размещенную на компьютере, посредством транспорта, отличного от HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-118">This ensures that no messages to any queue hosted on the machine can arrive using any non-HTTP transport.</span></span>  
  
6.  <span data-ttu-id="c9d41-119">После выбора ужесточенного режима MSMQ требуется перезагрузка компьютера с ОС [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9d41-119">After you have selected MSMQ to run in hardened mode, the machine requires a re-boot on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
7.  <span data-ttu-id="c9d41-120">Запустите службу.</span><span class="sxs-lookup"><span data-stu-id="c9d41-120">Run the service.</span></span>  
  
8.  <span data-ttu-id="c9d41-121">Запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="c9d41-121">Run the client.</span></span> <span data-ttu-id="c9d41-122">Измените адрес конечной точки клиента, указав имя компьютера или IP-адрес вместо "localhost".</span><span class="sxs-lookup"><span data-stu-id="c9d41-122">Ensure that you change the endpoint address to point to the machine name or IP address instead of localhost.</span></span> <span data-ttu-id="c9d41-123">Клиент отправляет сообщение, и выполняется выход.</span><span class="sxs-lookup"><span data-stu-id="c9d41-123">The client sends a message and exits.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9d41-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c9d41-124">Requirements</span></span>  
 <span data-ttu-id="c9d41-125">Чтобы запустить этот образец, кроме MSMQ на компьютерах службы и клиента должны быть установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="c9d41-125">To run this sample, IIS must be installed on both the service and the client machines in addition to MSMQ.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="c9d41-126">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="c9d41-126">Demonstrates</span></span>  
 <span data-ttu-id="c9d41-127">В образце показана отправка сообщений в очереди [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью MSMQ по HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-127">The sample demonstrates sending [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queued messages using MSMQ over HTTP.</span></span> <span data-ttu-id="c9d41-128">Это также называется обменом сообщениями SRMP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-128">This is also called SRMP messaging.</span></span> <span data-ttu-id="c9d41-129">Когда отправляется сообщение в очереди, MSMQ на отправляющем компьютере передает сообщения диспетчеру принимающей очереди по транспорту TCP или HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-129">When a queued message is sent, MSMQ on the sending machine transfers the messages to the receiving queue manager over TCP or HTTP transport.</span></span> <span data-ttu-id="c9d41-130">Закрывая SRMP, пользователь указывает, что HTTP должен использоваться в качестве транспорта для передачи очередей.</span><span class="sxs-lookup"><span data-stu-id="c9d41-130">By choosing SRMP, the user indicates the choice of HTTP as a transport for queue transfer.</span></span> <span data-ttu-id="c9d41-131">Безопасный SRMP (SRMP Secure) обеспечивает использование HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c9d41-131">SRMP Secure enables the use of HTTPS.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9d41-132">Пример</span><span class="sxs-lookup"><span data-stu-id="c9d41-132">Example</span></span>  
 <span data-ttu-id="c9d41-133">Образец кода основан на образце с транзакциями.</span><span class="sxs-lookup"><span data-stu-id="c9d41-133">The sample code is based on the transacted sample.</span></span> <span data-ttu-id="c9d41-134">Отправка сообщения в очередь и его получение из нее с помощью SRMP аналогичны отправке и получению сообщений с помощью собственного протокола.</span><span class="sxs-lookup"><span data-stu-id="c9d41-134">How you send a message to the queue and receive a message from the queue using SRMP is the same as sending and receiving messages using a Native protocol.</span></span>  
  
 <span data-ttu-id="c9d41-135">Конфигурация клиента изменяется, что указать выбранный протокол передачи между очередями.</span><span class="sxs-lookup"><span data-stu-id="c9d41-135">The configuration for the client is changed to indicate the choice of the queue transfer protocol.</span></span> <span data-ttu-id="c9d41-136">Протокол передачи между очередями может быть собственным, SRMP или SrmpSecure.</span><span class="sxs-lookup"><span data-stu-id="c9d41-136">The queue transfer protocol can be one of Native, SRMP or SrmpSecure.</span></span> <span data-ttu-id="c9d41-137">По умолчанию используется собственный протокол.</span><span class="sxs-lookup"><span data-stu-id="c9d41-137">By default, the transfer protocol is Native.</span></span> <span data-ttu-id="c9d41-138">В этом примере в конфигурации клиента и службы отмечено использование SRMP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-138">The client and service specify in the configuration to use SRMP in this example.</span></span>  
  
 <span data-ttu-id="c9d41-139">Существуют некоторые ограничения SRMP в отношении безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="c9d41-139">There are limitations to SRMP in relation to transport security.</span></span> <span data-ttu-id="c9d41-140">Для безопасности транспорта MSMQ по умолчанию необходима Active Directory, требующая, чтобы диспетчер передающей и принимающей очереди находились в одном и том же домене Windows.</span><span class="sxs-lookup"><span data-stu-id="c9d41-140">The default MSMQ transport security requires Active Directory that requires that the sending queue manager and the receiving queue manager reside in the same Windows domain.</span></span> <span data-ttu-id="c9d41-141">Это невозможно при отправке сообщений по HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-141">This is not possible when sending messages over HTTP boundary.</span></span> <span data-ttu-id="c9d41-142">По существу, безопасность транспорта по умолчанию не работает.</span><span class="sxs-lookup"><span data-stu-id="c9d41-142">As such, the default transport security does not work.</span></span> <span data-ttu-id="c9d41-143">Для безопасности транспорта необходимо задать "Certificate" (Сертификат), если она необходима.</span><span class="sxs-lookup"><span data-stu-id="c9d41-143">The transport security must be set to Certificate if transport security is desired.</span></span> <span data-ttu-id="c9d41-144">Для защиты сообщений можно также использовать безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9d41-144">Message security can also be used to secure the message.</span></span> <span data-ttu-id="c9d41-145">В этом образце безопасность транспорта и сообщений отключена, чтобы продемонстрировать обмен сообщениями SRMP.</span><span class="sxs-lookup"><span data-stu-id="c9d41-145">In this sample, both transport and message security is turned off to illustrate SRMP messaging.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None"></security>  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="c9d41-146">Этот код будет приводить к следующему результату.</span><span class="sxs-lookup"><span data-stu-id="c9d41-146">Running the sample yields the following output.</span></span>  
  
```  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9d41-147">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9d41-147">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c9d41-148">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c9d41-148">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c9d41-149">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9d41-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9d41-150">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c9d41-150">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
  
## <a name="see-also"></a><span data-ttu-id="c9d41-151">См. также</span><span class="sxs-lookup"><span data-stu-id="c9d41-151">See Also</span></span>
