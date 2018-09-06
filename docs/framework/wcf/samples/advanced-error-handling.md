---
title: Расширенная обработка ошибок
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 72fb9885408759f5781501b548f81625d258d13c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745262"
---
# <a name="advanced-error-handling"></a><span data-ttu-id="02041-102">Расширенная обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="02041-102">Advanced Error Handling</span></span>
<span data-ttu-id="02041-103">В этом примере демонстрируется служба маршрутизации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="02041-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="02041-104">Служба маршрутизации является компонентом WCF, который упрощает Включение маршрутизатора на основе содержимого в приложении.</span><span class="sxs-lookup"><span data-stu-id="02041-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="02041-105">В этом образце показано, как служба маршрутизации выполняет интеллектуальное восстановление работы после ошибок с использованием транзакций и более сложных понятий обмена сообщениями, таких как многоадресная передача.</span><span class="sxs-lookup"><span data-stu-id="02041-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02041-106">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="02041-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="02041-107">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="02041-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="02041-108">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="02041-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="02041-109">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="02041-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="02041-110">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="02041-110">Sample Details</span></span>  
 <span data-ttu-id="02041-111">В этом образце служба маршрутизации настраивается для считывания сообщения из очереди MSMQ и многоадресной передачи этого сообщения в два списка очередей.</span><span class="sxs-lookup"><span data-stu-id="02041-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="02041-112">Один список используется для очередей обслуживания, а другой - для очередей журнала.</span><span class="sxs-lookup"><span data-stu-id="02041-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="02041-113">Поскольку по умолчанию привязка MSMQ, которая используется службой маршрутизации, поддерживает использование транзакций, служба маршрутизации проверяет, что сообщение входит в транзакцию и принято хотя бы одной очередью из каждого списка, а затем сообщает очереди входящих сообщений (`InQ`) об успешной маршрутизации сообщения.</span><span class="sxs-lookup"><span data-stu-id="02041-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="02041-114">Поэтому в случае, когда обе очереди службы обслуживания или обе очереди журнала становятся недоступны, служба маршрутизации сообщает, что не удалось выполнить маршрутизацию сообщения, и очередь входящих сообщений должна выполнить какое-либо действие.</span><span class="sxs-lookup"><span data-stu-id="02041-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="02041-115">Это действие заключается в перемещении сообщения в системную очередь недоставленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="02041-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="02041-116">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="02041-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="02041-117">Перед запуском этого образца установите очередь MSMQ.</span><span class="sxs-lookup"><span data-stu-id="02041-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="02041-118">Если очередь MSMQ не установлена, то при запуске образца возвращается сообщение исключения.</span><span class="sxs-lookup"><span data-stu-id="02041-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="02041-119">Инструкции по установке MSMQ можно найти в [Установка очереди сообщений (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span><span class="sxs-lookup"><span data-stu-id="02041-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="02041-120">Откройте файл AdvancedErrorHandling.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02041-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="02041-121">Нажмите клавишу **F5** или **CTRL + SHIFT + B** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="02041-121">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="02041-122">Если приложение построено с помощью нажатия клавиш CTRL+SHIFT+B, его необходимо запустить из файла ./RoutingService/bin/debug/RoutingService.exe.</span><span class="sxs-lookup"><span data-stu-id="02041-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="02041-123">Чтобы запустить клиент, нажмите клавишу ВВОД в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="02041-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="02041-124">В каждом случае клиент возвращает разную статистику об очередях.</span><span class="sxs-lookup"><span data-stu-id="02041-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="02041-125">Далее представлены данные, возвращаемые для случая 1 (без ошибок).</span><span class="sxs-lookup"><span data-stu-id="02041-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="02041-126">Далее представлены данные, возвращаемые для случая 3 (ошибки в основной очереди и очереди журнала).</span><span class="sxs-lookup"><span data-stu-id="02041-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="02041-127">Далее представлены данные, возвращаемые для случая 4 (ошибки в основной очереди обслуживания, а также в основной и резервной очередях журнала).</span><span class="sxs-lookup"><span data-stu-id="02041-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="02041-128">Далее представлены данные, возвращаемые для случая 2 (ошибка в основной очереди обслуживания).</span><span class="sxs-lookup"><span data-stu-id="02041-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="02041-129">Настраивается в коде или в файле App.config</span><span class="sxs-lookup"><span data-stu-id="02041-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="02041-130">В поставляемой конфигурации образца поведение маршрутизатора определяется в файле App.config.</span><span class="sxs-lookup"><span data-stu-id="02041-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="02041-131">Кроме того, можно изменить имя файла RoutingService\App.config, чтобы он не распознавался, и изменить значение поля `configDriven` в файле RoutingService\Program.cs на `false`, чтобы использовать конфигурацию, определенную в коде.</span><span class="sxs-lookup"><span data-stu-id="02041-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="02041-132">Поведение маршрутизатора будет одинаковым для обоих методов.</span><span class="sxs-lookup"><span data-stu-id="02041-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="02041-133">Сценарий</span><span class="sxs-lookup"><span data-stu-id="02041-133">Scenario</span></span>  
 <span data-ttu-id="02041-134">В этом образце показано, что служба маршрутизации обладает расширенными возможностями по обработки сообщений. В частности, поддерживаются транзакции и контекст получения. Эти возможности применяются для верной обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="02041-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="02041-135">Реальный сценарий</span><span class="sxs-lookup"><span data-stu-id="02041-135">Real World Scenario</span></span>  
 <span data-ttu-id="02041-136">Компания Contoso планирует транзакционные операции получения сообщений в службе маршрутизации, чтобы обеспечить доставку данных во всех необходимые службы даже при возникновении ошибок.</span><span class="sxs-lookup"><span data-stu-id="02041-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="02041-137">Кроме того, требуется правильная автоматическая обработка ошибок и отправка предупреждения в случае, когда сообщение не удается доставить даже путем применения логики обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="02041-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="02041-138">Для этого в службе маршрутизации настраивается резервное переключение на специальные конечные точки, и служба маршрутизации обрабатывает ошибки. В этом процессе выполняется создание, завершение, откат и прерывание транзакций и контекстов получения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="02041-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02041-139">См. также</span><span class="sxs-lookup"><span data-stu-id="02041-139">See Also</span></span>  
 [<span data-ttu-id="02041-140">Образцы размещения AppFabric и сохраняемости</span><span class="sxs-lookup"><span data-stu-id="02041-140">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
