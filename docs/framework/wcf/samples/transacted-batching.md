---
title: Пакетирование с поддержкой транзакций
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: abada9aaf5fac8f05599467f385e708e1898832f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856067"
---
# <a name="transacted-batching"></a><span data-ttu-id="4410f-102">Пакетирование с поддержкой транзакций</span><span class="sxs-lookup"><span data-stu-id="4410f-102">Transacted Batching</span></span>
<span data-ttu-id="4410f-103">В этом образце показано, как пакетировать операции чтения с поддержкой транзакций с помощью очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="4410f-103">This sample demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span> <span data-ttu-id="4410f-104">Пакетирование с поддержкой транзакций - это функция оптимизации производительности для чтения с поддержкой транзакций при взаимодействии с использованием очередей.</span><span class="sxs-lookup"><span data-stu-id="4410f-104">Transacted Batching is a performance optimization feature for transacted reads in queued communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4410f-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="4410f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4410f-106">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="4410f-107">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="4410f-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="4410f-108">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-108">The service receives messages from the queue.</span></span> <span data-ttu-id="4410f-109">Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-109">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="4410f-110">В этом образце демонстрируется пакетирование с поддержкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="4410f-110">This sample demonstrates transacted batching.</span></span> <span data-ttu-id="4410f-111">Пакетирование с поддержкой транзакций - это поведение, которое позволяет считывать несколько сообщений в очереди и обрабатывать их в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-111">Transacted batching is a behavior that enables the use of a single transaction when reading many messages in the queue and processing them.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4410f-112">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="4410f-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4410f-113">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4410f-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4410f-114">При первом запуске служба проверит наличие очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-114">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="4410f-115">Если очередь отсутствует, служба ее создаст.</span><span class="sxs-lookup"><span data-stu-id="4410f-115">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="4410f-116">Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4410f-116">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="4410f-117">Чтобы создать очередь в Windows 2008, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4410f-117">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="4410f-118">Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4410f-118">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="4410f-119">Разверните **функции** вкладки.</span><span class="sxs-lookup"><span data-stu-id="4410f-119">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="4410f-120">Щелкните правой кнопкой мыши **очереди личных сообщений**и выберите **New**, **частную очередь**.</span><span class="sxs-lookup"><span data-stu-id="4410f-120">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="4410f-121">Проверьте **транзакционная** поле.</span><span class="sxs-lookup"><span data-stu-id="4410f-121">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="4410f-122">Введите `ServiceModelSamplesTransacted` как имя новой очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-122">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4410f-123">В этом образце клиент отправляет в составе пакета сотни сообщений.</span><span class="sxs-lookup"><span data-stu-id="4410f-123">In this sample the client sends hundreds of messages as part of the batch.</span></span> <span data-ttu-id="4410f-124">Естественно, что обработка в служебном приложении этих сообщений займет определенное время.</span><span class="sxs-lookup"><span data-stu-id="4410f-124">It is normal for the service application to take some time to process these.</span></span>  
  
3.  <span data-ttu-id="4410f-125">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4410f-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="4410f-126">Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4410f-126">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="4410f-127">Запуск образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory</span><span class="sxs-lookup"><span data-stu-id="4410f-127">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="4410f-128">По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена.</span><span class="sxs-lookup"><span data-stu-id="4410f-128">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="4410f-129">Имеется два соответствующих свойства для обеспечения безопасности транспорта MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` по умолчанию, присваивается режим проверки подлинности `Windows` и уровень защиты `Sign`.</span><span class="sxs-lookup"><span data-stu-id="4410f-129">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="4410f-130">Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена возможность интеграции MSMQ со службой каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4410f-130">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="4410f-131">Если запустить данный образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="4410f-131">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
2.  <span data-ttu-id="4410f-132">Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4410f-132">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="4410f-133">Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="4410f-133">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4410f-134">Задание для `security``mode` значения `None` эквивалентно заданию для параметров безопасности <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> и `Message` значения `None`.</span><span class="sxs-lookup"><span data-stu-id="4410f-134">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
4.  <span data-ttu-id="4410f-135">Чтобы выполнить базу данных на удаленном компьютере, необходимо изменить строку подключения так, чтобы она указывала на компьютер, на котором находится база данных.</span><span class="sxs-lookup"><span data-stu-id="4410f-135">To run the database on a remote computer, change the connection string to point to the computer on which the database resides.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4410f-136">Требования</span><span class="sxs-lookup"><span data-stu-id="4410f-136">Requirements</span></span>  
 <span data-ttu-id="4410f-137">Для выполнения этого образца должна быть установлена MSMQ, необходимо также использовать SQL или SQL Express.</span><span class="sxs-lookup"><span data-stu-id="4410f-137">To run this sample, MSMQ must be installed and SQL or SQL Express is required.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4410f-138">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="4410f-138">Demonstrates</span></span>  
 <span data-ttu-id="4410f-139">В этом образце демонстрируется поведение пакетирования с поддержкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="4410f-139">The sample demonstrates transacted batching behavior.</span></span> <span data-ttu-id="4410f-140">Пакетирование с поддержкой транзакций - это функция оптимизации производительности, предоставляемая с транспортом очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4410f-140">Transacted batching is a performance optimization feature provided with MSMQ queued transport.</span></span>  
  
 <span data-ttu-id="4410f-141">При использовании транзакций для отправки и получения сообщений это фактически две отдельные транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-141">When transactions are used to send and receive messages there are actually 2 separate transactions.</span></span> <span data-ttu-id="4410f-142">При отправке клиентом сообщений в области транзакции эта транзакция локальна для клиента и диспетчера очереди клиента.</span><span class="sxs-lookup"><span data-stu-id="4410f-142">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="4410f-143">При получении службой сообщений в области транзакции эта транзакция локальна для службы и диспетчера принимающей очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-143">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="4410f-144">Очень важно помнить, что клиент и служба не участвуют в одной транзакции, а используют разные транзакции при выполнении операций с очередью (например, отправки и получения).</span><span class="sxs-lookup"><span data-stu-id="4410f-144">It is very important to remember that the client and the service are not participating in the same transaction; rather they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="4410f-145">В этом образце одна транзакция используется для выполнения нескольких операций службы.</span><span class="sxs-lookup"><span data-stu-id="4410f-145">In the sample we use a single transaction for the execution of multiple service operations.</span></span> <span data-ttu-id="4410f-146">Этот подход используется исключительно в качестве возможности оптимизации производительности и не влияет на семантику приложения.</span><span class="sxs-lookup"><span data-stu-id="4410f-146">This is used only as a performance optimization feature and does not impact the semantics of the application.</span></span> <span data-ttu-id="4410f-147">Этот образец основан на [транзакции привязки MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="4410f-147">The sample is based on [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="4410f-148">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4410f-148">Comments</span></span>  
 <span data-ttu-id="4410f-149">В этом образце клиент отправляет службе пакет сообщений из области транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-149">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="4410f-150">Чтобы продемонстрировать оптимизацию производительности, отправляется большое число сообщений (до 2 500 в данном случае).</span><span class="sxs-lookup"><span data-stu-id="4410f-150">To show the performance optimization, we send a large number of messages; in this case, up to 2500 messages.</span></span>  
  
 <span data-ttu-id="4410f-151">Сообщения, отправленные в очередь, принимаются после этого службой в области транзакции, определенной службой.</span><span class="sxs-lookup"><span data-stu-id="4410f-151">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span> <span data-ttu-id="4410f-152">Если не используется пакетирование, каждый вызов операции службы приводит к выполнению 2 500 транзакций.</span><span class="sxs-lookup"><span data-stu-id="4410f-152">Without batching, this results in 2500 transactions for each invocation of the service operation.</span></span> <span data-ttu-id="4410f-153">Это влияет на производительность системы.</span><span class="sxs-lookup"><span data-stu-id="4410f-153">This impacts performance of the system.</span></span> <span data-ttu-id="4410f-154">Так как участвуют два диспетчера ресурсов (очередь MSMQ и база данных `Orders`), каждая транзакция является транзакцией DTC.</span><span class="sxs-lookup"><span data-stu-id="4410f-154">Because two resource managers are involved -the MSMQ queue and the `Orders` database- each such transaction is a DTC transaction.</span></span> <span data-ttu-id="4410f-155">Оптимизация обеспечивается выполнением гораздо меньшего числа транзакций, что возможно благодаря вызову пакета сообщений и операции службы в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-155">We optimize this by using a much smaller number of transactions by ensuring that a batch of messages and service operation invocations happen in a single transaction.</span></span>  
  
 <span data-ttu-id="4410f-156">Ниже перечислены способы использования функции пакетирования.</span><span class="sxs-lookup"><span data-stu-id="4410f-156">We use the batching feature by:</span></span>  
  
-   <span data-ttu-id="4410f-157">При задании поведения пакетирования с поддержкой транзакций в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4410f-157">Specifying transacted batching behavior in configuration.</span></span>  
  
-   <span data-ttu-id="4410f-158">При задании размера пакета в терминах числа сообщений, считываемых в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-158">Specifying a batch size in terms of number of messages to be read using a single transaction.</span></span>  
  
-   <span data-ttu-id="4410f-159">При задании максимального числа одновременно выполняемых пакетов.</span><span class="sxs-lookup"><span data-stu-id="4410f-159">Specifying the maximum number of concurrent batches to run.</span></span>  
  
 <span data-ttu-id="4410f-160">В этом примере демонстрируется повышение производительности благодаря уменьшению числа транзакций вследствие того, что в одной транзакции вызывается 100 операций службы до фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-160">In this example, we show performance gains by reducing the number of transactions by ensuring that 100 service operations are invoked in a single transaction before committing the transaction.</span></span>  
  
 <span data-ttu-id="4410f-161">Поведение службы определяет поведение операции со значением `TransactionScopeRequired`, равным `true`.</span><span class="sxs-lookup"><span data-stu-id="4410f-161">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="4410f-162">Это обеспечивает использование любыми диспетчерами ресурсов, к которым обращается метод, той же области транзакции, что и для получения сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-162">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="4410f-163">В этом примере основная база данных используется для хранения сведений о заказе на покупку, содержащихся в сообщении.</span><span class="sxs-lookup"><span data-stu-id="4410f-163">In this example, we use a basic database to store the purchase order information contained in the message.</span></span> <span data-ttu-id="4410f-164">Область транзакции также гарантирует возврат сообщения в очередь, если метод создаст исключение.</span><span class="sxs-lookup"><span data-stu-id="4410f-164">The transaction scope also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="4410f-165">Если не установить такое поведение операции, канал в очереди создает транзакцию для чтения сообщения из очереди и автоматически фиксирует ее перед передачей, поэтому при ошибке операции сообщение теряется.</span><span class="sxs-lookup"><span data-stu-id="4410f-165">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before it is dispatched so that if the operation fails, the message is lost.</span></span> <span data-ttu-id="4410f-166">Наиболее стандартная схема для операций служб заключается в зачислении в транзакцию, которая используется для чтения сообщения из очереди, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4410f-166">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue as demonstrated in the following code.</span></span>  
  
 <span data-ttu-id="4410f-167">Обратите внимание, что `ReleaseServiceInstanceOnTransactionComplete` присвоено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4410f-167">Note that `ReleaseServiceInstanceOnTransactionComplete` is set to `false`.</span></span> <span data-ttu-id="4410f-168">Это важное требование при пакетировании.</span><span class="sxs-lookup"><span data-stu-id="4410f-168">This is an important requirement for batching.</span></span> <span data-ttu-id="4410f-169">Свойство `ReleaseServiceInstanceOnTransactionComplete` в `ServiceBehaviorAttribute` показывает, что делать с экземпляром службы после завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-169">The property `ReleaseServiceInstanceOnTransactionComplete` on `ServiceBehaviorAttribute` indicates what to do with the service instance once the transaction is completed.</span></span> <span data-ttu-id="4410f-170">По умолчанию после завершения транзакции экземпляр службы освобождается.</span><span class="sxs-lookup"><span data-stu-id="4410f-170">By default, the service instance is released upon completing the transaction.</span></span> <span data-ttu-id="4410f-171">Смысл пакетирования заключается в том, что одна транзакция используется для чтения и диспетчеризации большого числа сообщений в очереди.</span><span class="sxs-lookup"><span data-stu-id="4410f-171">The core aspect to batching is the use of a single transaction for reading and dispatching many messages in the queue.</span></span> <span data-ttu-id="4410f-172">Следовательно, освобождение экземпляра службы приводит к преждевременному завершению транзакции, что противоречит смыслу пакетирования.</span><span class="sxs-lookup"><span data-stu-id="4410f-172">Therefore releasing the service instance ends up completing the transaction prematurely negating the very use of batching.</span></span> <span data-ttu-id="4410f-173">Если этому свойству присвоено значение `true`, а поведение пакетирования с поддержкой транзакций добавляется в конечную точку, поведение проверки пакетирования создает исключение.</span><span class="sxs-lookup"><span data-stu-id="4410f-173">If this property is set to `true` and transacted batching behavior is added to the endpoint, the batching validation behavior throws an exception.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 <span data-ttu-id="4410f-174">Класс `Orders` инкапсулирует обработку заказа.</span><span class="sxs-lookup"><span data-stu-id="4410f-174">The `Orders` class encapsulates the processing of the order.</span></span> <span data-ttu-id="4410f-175">В этом образце он обновляет базу данных, внося сведения о заказе на покупку.</span><span class="sxs-lookup"><span data-stu-id="4410f-175">In the sample, it updates the database with purchase order information.</span></span>  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 <span data-ttu-id="4410f-176">Поведение пакетирования и его конфигурация заданы в конфигурации приложения службы.</span><span class="sxs-lookup"><span data-stu-id="4410f-176">The batching behavior and its configuration are specified in the service application configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="4410f-177">Размер пакета - это подсказка системе.</span><span class="sxs-lookup"><span data-stu-id="4410f-177">The batch size is a hint to the system.</span></span> <span data-ttu-id="4410f-178">Например, если задать размер пакета равным 20, именно столько сообщений считает и диспетчеризует одна транзакция, после чего произойдет фиксация транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-178">For example, if you specify a batch size of 20, then 20 messages would be read and dispatched using a single transaction and then the transaction is committed.</span></span> <span data-ttu-id="4410f-179">Однако в некоторых случаях транзакция может зафиксировать пакет раньше, чем будет достигнут размер пакета.</span><span class="sxs-lookup"><span data-stu-id="4410f-179">But there are cases where the transaction may commit the batch before the batch size is reached.</span></span>  
>   
>  <span data-ttu-id="4410f-180">С каждой транзакцией связан период ожидания, который отсчитывается после создания транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-180">Associated with every transaction is a timeout that starts ticking once the transaction is created.</span></span> <span data-ttu-id="4410f-181">По истечении этого времени ожидания транзакция прерывается.</span><span class="sxs-lookup"><span data-stu-id="4410f-181">When this timeout expires the transaction is aborted.</span></span> <span data-ttu-id="4410f-182">Этот период ожидания может истечь раньше, чем будет достигнут размер пакета.</span><span class="sxs-lookup"><span data-stu-id="4410f-182">It is possible for this timeout to expire even before the batch size is reached.</span></span> <span data-ttu-id="4410f-183">Чтобы избежать переработки пакета из-за прерывания, `TransactedBatchingBehavior` проверяет, сколько времени осталось до истечения периода ожидания для данной транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-183">To avoid re-working the batch because of the abort, the `TransactedBatchingBehavior` checks to see how much time is left on the transaction.</span></span> <span data-ttu-id="4410f-184">Транзакция фиксируется по истечении 80 % времени ожидания транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-184">If 80% of the transaction timeout is used up, then the transaction is committed.</span></span>  
>   
>  <span data-ttu-id="4410f-185">Если в очереди больше нет сообщений, вместо того, чтобы ждать достижения размера пакета, поведение <xref:System.ServiceModel.Description.TransactedBatchingBehavior> фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="4410f-185">If there are no more messages in the queue then instead of waiting for the fulfillment of the batch size the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> commits the transaction.</span></span>  
>   
>  <span data-ttu-id="4410f-186">Выбор размера пакета зависит от используемого приложения.</span><span class="sxs-lookup"><span data-stu-id="4410f-186">The choice of the batch size is dependent on your application.</span></span> <span data-ttu-id="4410f-187">Если размер пакета слишком маленький, производительность может быть ниже требуемого уровня.</span><span class="sxs-lookup"><span data-stu-id="4410f-187">If the batch size is too small, you may not get the desired performance.</span></span> <span data-ttu-id="4410f-188">С другой стороны, слишком большой размер пакета также может снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="4410f-188">On the other hand if the batch size is too big, it may deteriorate performance.</span></span> <span data-ttu-id="4410f-189">Например, время существования транзакции может увеличиться, и она может хранить блокировки используемой базы данных, либо возможна взаимоблокировка транзакции, в результате чего может произойти откат пакета и повторение всей процедуры.</span><span class="sxs-lookup"><span data-stu-id="4410f-189">For example, your transaction could live longer and hold locks on your database or your transaction could become dead locked, which could cause the batch to get rolled back and to redo the work.</span></span>  
  
 <span data-ttu-id="4410f-190">Клиент создает область транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-190">The client creates a transaction scope.</span></span> <span data-ttu-id="4410f-191">Связь с очередью происходит в области транзакции, поэтому она обрабатывается как единый модуль, в котором либо все сообщения отправляются в очередь, либо в очередь не отправляется ни одного сообщения.</span><span class="sxs-lookup"><span data-stu-id="4410f-191">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="4410f-192">Транзакция фиксируется вызовом метода <xref:System.Transactions.TransactionScope.Complete%2A> для области транзакции.</span><span class="sxs-lookup"><span data-stu-id="4410f-192">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
            PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
            lineItem2.ProductId = "Red Widget";  
            lineItem2.Quantity = 890;  
            lineItem2.UnitCost = 45.89F;  
  
            po.orderLineItems = new PurchaseOrderLineItem[2];  
            po.orderLineItems[0] = lineItem1;  
            po.orderLineItems[1] = lineItem2;  
  
            //Create a transaction scope.  
            using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
            {  
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 <span data-ttu-id="4410f-193">При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="4410f-193">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="4410f-194">Можно видеть, как служба получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="4410f-194">You can see the service receive messages from the client.</span></span> <span data-ttu-id="4410f-195">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="4410f-195">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="4410f-196">Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="4410f-196">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="4410f-197">Можно запустить клиент, выключить его, а затем запустить службу, которая все равно получит сообщения клиента.</span><span class="sxs-lookup"><span data-stu-id="4410f-197">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="4410f-198">При считывании и обработке пакета сообщений можно видеть чередующийся вывод.</span><span class="sxs-lookup"><span data-stu-id="4410f-198">You can see a rolling output as messages are read in a batch and processed.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="4410f-199">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4410f-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4410f-200">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4410f-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4410f-201">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="4410f-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4410f-202">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4410f-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a><span data-ttu-id="4410f-203">См. также</span><span class="sxs-lookup"><span data-stu-id="4410f-203">See Also</span></span>
