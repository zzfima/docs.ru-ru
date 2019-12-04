---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 0ee11b67dcd9c7251df17dc7523dc20765e157c5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716694"
---
# <a name="srmp"></a><span data-ttu-id="5aeaa-102">SRMP</span><span class="sxs-lookup"><span data-stu-id="5aeaa-102">SRMP</span></span>
<span data-ttu-id="5aeaa-103">В этом образце показано, как осуществлять транзакционное взаимодействие с использованием очередей с помощью очереди сообщений (MSMQ) по HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 <span data-ttu-id="5aeaa-104">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-104">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="5aeaa-105">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-105">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="5aeaa-106">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-106">The service receives messages from the queue.</span></span> <span data-ttu-id="5aeaa-107">Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-107">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="5aeaa-108">MSMQ обеспечивает использование HTTP (включая HTTPS) для отправки сообщений в очередь.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-108">MSMQ enables the use of HTTP (including the use of HTTPS) to send messages to a queue.</span></span> <span data-ttu-id="5aeaa-109">В этом примере демонстрируется использование взаимодействия в очереди Windows Communication Foundation (WCF) и отправка сообщений по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-109">In this example, we demonstrate using Windows Communication Foundation (WCF) queued communication and how to send messages over HTTP.</span></span> <span data-ttu-id="5aeaa-110">MSMQ использует протокол под названием SRMP, являющийся протоколом на основе SOAP для взаимодействия по HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-110">MSMQ uses a protocol called SRMP, which is a SOAP-based protocol for communication over HTTP.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5aeaa-111">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="5aeaa-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="5aeaa-112">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5aeaa-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="5aeaa-113">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5aeaa-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="5aeaa-114">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5aeaa-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="5aeaa-115">Перед запуском примера в окне " **Установка и удаление компонентов Windows**" убедитесь, что служба MSMQ установлена с поддержкой HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-115">Before running the sample in **Add/Remove Windows Components**, ensure that MSMQ is installed with HTTP support.</span></span> <span data-ttu-id="5aeaa-116">При установке поддержки HTTP автоматически устанавливаются службы IIS и в них добавляется поддержка протокола для MSMQ.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-116">Installing HTTP support automatically installs Internet Information Services (IIS) and adds the protocol support in IIS for MSMQ.</span></span>  
  
5. <span data-ttu-id="5aeaa-117">Чтобы гарантировать использование HTTP для взаимодействия, можно включить ужесточенный режим MSMQ.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-117">If you want to be certain that HTTP is used for communication, you can enable MSMQ to run in hardened mode.</span></span> <span data-ttu-id="5aeaa-118">Это позволит предотвратить получение сообщений в любую очередь, размещенную на компьютере, посредством транспорта, отличного от HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-118">This ensures that no messages to any queue hosted on the machine can arrive using any non-HTTP transport.</span></span>  
  
6. <span data-ttu-id="5aeaa-119">После выбора ужесточенного режима MSMQ требуется перезагрузка компьютера с ОС [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aeaa-119">After you have selected MSMQ to run in hardened mode, the machine requires a re-boot on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
7. <span data-ttu-id="5aeaa-120">Запустите службу.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-120">Run the service.</span></span>  
  
8. <span data-ttu-id="5aeaa-121">Запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-121">Run the client.</span></span> <span data-ttu-id="5aeaa-122">Измените адрес конечной точки клиента, указав имя компьютера или IP-адрес вместо "localhost".</span><span class="sxs-lookup"><span data-stu-id="5aeaa-122">Ensure that you change the endpoint address to point to the machine name or IP address instead of localhost.</span></span> <span data-ttu-id="5aeaa-123">Клиент отправляет сообщение, и выполняется выход.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-123">The client sends a message and exits.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aeaa-124">Требования</span><span class="sxs-lookup"><span data-stu-id="5aeaa-124">Requirements</span></span>  
 <span data-ttu-id="5aeaa-125">Чтобы запустить этот образец, кроме MSMQ на компьютерах службы и клиента должны быть установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-125">To run this sample, IIS must be installed on both the service and the client machines in addition to MSMQ.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5aeaa-126">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="5aeaa-126">Demonstrates</span></span>  
 <span data-ttu-id="5aeaa-127">В примере демонстрируется отправка сообщений в очереди WCF с помощью MSMQ по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-127">The sample demonstrates sending WCF queued messages using MSMQ over HTTP.</span></span> <span data-ttu-id="5aeaa-128">Это также называется обменом сообщениями SRMP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-128">This is also called SRMP messaging.</span></span> <span data-ttu-id="5aeaa-129">Когда отправляется сообщение в очереди, MSMQ на отправляющем компьютере передает сообщения диспетчеру принимающей очереди по транспорту TCP или HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-129">When a queued message is sent, MSMQ on the sending machine transfers the messages to the receiving queue manager over TCP or HTTP transport.</span></span> <span data-ttu-id="5aeaa-130">Закрывая SRMP, пользователь указывает, что HTTP должен использоваться в качестве транспорта для передачи очередей.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-130">By choosing SRMP, the user indicates the choice of HTTP as a transport for queue transfer.</span></span> <span data-ttu-id="5aeaa-131">Безопасный SRMP (SRMP Secure) обеспечивает использование HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-131">SRMP Secure enables the use of HTTPS.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aeaa-132">Пример</span><span class="sxs-lookup"><span data-stu-id="5aeaa-132">Example</span></span>  
 <span data-ttu-id="5aeaa-133">Образец кода основан на образце с транзакциями.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-133">The sample code is based on the transacted sample.</span></span> <span data-ttu-id="5aeaa-134">Отправка сообщения в очередь и его получение из нее с помощью SRMP аналогичны отправке и получению сообщений с помощью собственного протокола.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-134">How you send a message to the queue and receive a message from the queue using SRMP is the same as sending and receiving messages using a Native protocol.</span></span>  
  
 <span data-ttu-id="5aeaa-135">Конфигурация клиента изменяется, что указать выбранный протокол передачи между очередями.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-135">The configuration for the client is changed to indicate the choice of the queue transfer protocol.</span></span> <span data-ttu-id="5aeaa-136">Протокол передачи между очередями может быть собственным, SRMP или SrmpSecure.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-136">The queue transfer protocol can be one of Native, SRMP or SrmpSecure.</span></span> <span data-ttu-id="5aeaa-137">По умолчанию используется собственный протокол.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-137">By default, the transfer protocol is Native.</span></span> <span data-ttu-id="5aeaa-138">В этом примере в конфигурации клиента и службы отмечено использование SRMP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-138">The client and service specify in the configuration to use SRMP in this example.</span></span>  
  
 <span data-ttu-id="5aeaa-139">Существуют некоторые ограничения SRMP в отношении безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-139">There are limitations to SRMP in relation to transport security.</span></span> <span data-ttu-id="5aeaa-140">Для безопасности транспорта MSMQ по умолчанию необходима Active Directory, требующая, чтобы диспетчер передающей и принимающей очереди находились в одном и том же домене Windows.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-140">The default MSMQ transport security requires Active Directory that requires that the sending queue manager and the receiving queue manager reside in the same Windows domain.</span></span> <span data-ttu-id="5aeaa-141">Это невозможно при отправке сообщений по HTTP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-141">This is not possible when sending messages over HTTP boundary.</span></span> <span data-ttu-id="5aeaa-142">По существу, безопасность транспорта по умолчанию не работает.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-142">As such, the default transport security does not work.</span></span> <span data-ttu-id="5aeaa-143">Для безопасности транспорта необходимо задать "Certificate" (Сертификат), если она необходима.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-143">The transport security must be set to Certificate if transport security is desired.</span></span> <span data-ttu-id="5aeaa-144">Для защиты сообщений можно также использовать безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-144">Message security can also be used to secure the message.</span></span> <span data-ttu-id="5aeaa-145">В этом образце безопасность транспорта и сообщений отключена, чтобы продемонстрировать обмен сообщениями SRMP.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-145">In this sample, both transport and message security is turned off to illustrate SRMP messaging.</span></span>  
  
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
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="5aeaa-146">Этот код будет приводить к следующему результату.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-146">Running the sample yields the following output.</span></span>  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="5aeaa-147">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-147">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5aeaa-148">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5aeaa-148">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="5aeaa-149">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5aeaa-150">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5aeaa-150">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
