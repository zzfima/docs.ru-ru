---
title: Управление приостановленным экземпляром
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: 3f1f4f8edcbe0e05067d3ca739ef3d5f4fe4d798
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715945"
---
# <a name="suspended-instance-management"></a><span data-ttu-id="ca779-102">Управление приостановленным экземпляром</span><span class="sxs-lookup"><span data-stu-id="ca779-102">Suspended Instance Management</span></span>
<span data-ttu-id="ca779-103">Этот образец демонстрирует управление экземплярами рабочего процесса, которые были приостановлены.</span><span class="sxs-lookup"><span data-stu-id="ca779-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="ca779-104">Действием по умолчанию для поведения <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> является `AbandonAndSuspend`.</span><span class="sxs-lookup"><span data-stu-id="ca779-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="ca779-105">Это означает, что по умолчанию при появлении необработанных исключений, сформированных экземпляром рабочего процесса, который размещен на узле <xref:System.ServiceModel.WorkflowServiceHost>, экземпляр удаляется из памяти (отбрасывается) и устойчивая/сохраненная версия экземпляра отмечается как приостановленная.</span><span class="sxs-lookup"><span data-stu-id="ca779-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="ca779-106">Приостановленный экземпляр рабочего процесса не будет в состоянии выполняться до отмены приостановки.</span><span class="sxs-lookup"><span data-stu-id="ca779-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>

 <span data-ttu-id="ca779-107">Этот образец показывает, как можно реализовать программу командной строки для выполнения запроса приостановленных экземпляров и как дать пользователю возможность возобновлять или завершать работу экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ca779-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="ca779-108">В этом образце служба рабочего процесса преднамеренно вызывает исключение, в результате чего она приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="ca779-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="ca779-109">Затем с помощью программы командной строки можно будет запросить экземпляр, а после этого возобновить или завершить его работу.</span><span class="sxs-lookup"><span data-stu-id="ca779-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ca779-110">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="ca779-110">Demonstrates</span></span>
 <span data-ttu-id="ca779-111"><xref:System.ServiceModel.WorkflowServiceHost> с <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> и <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> в Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="ca779-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>

## <a name="discussion"></a><span data-ttu-id="ca779-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="ca779-112">Discussion</span></span>
 <span data-ttu-id="ca779-113">Программа командной строки, реализованная в этом образце, предназначена для работы с реализацией хранилища экземпляра SQL Server, который поставляется в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca779-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="ca779-114">Если имеется пользовательская реализация хранилища экземпляра, то можно приспособить и эту программу, заменяя в образце реализации `WorkflowInstanceCommand` реализациями, которые относятся к применяемому хранилищу экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ca779-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>

 <span data-ttu-id="ca779-115">Команды SQL в предоставленной реализации запускаются непосредственно по отношению к хранилищу экземпляра SQL для формирования списка приостановленных экземпляров, а для возобновления или завершения работы экземпляров в ней используется конечная точка <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>, добавленная к узлу <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="ca779-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ca779-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ca779-116">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ca779-117">Для этого образца необходимо включить следующие компоненты Windows.</span><span class="sxs-lookup"><span data-stu-id="ca779-117">This sample requires that the following Windows components are enabled:</span></span>

    1. <span data-ttu-id="ca779-118">Сервер очереди сообщений (Майкрософт) (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="ca779-118">Microsoft Message Queues (MSMQ) Server</span></span>

    2. <span data-ttu-id="ca779-119">SQL Server, экспресс-выпуск</span><span class="sxs-lookup"><span data-stu-id="ca779-119">SQL Server Express</span></span>

2. <span data-ttu-id="ca779-120">Установка базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca779-120">Set up the SQL Server database.</span></span>

    1. <span data-ttu-id="ca779-121">В командной строке Visual Studio 2010 выполните команду Setup. cmd из каталога примеров Суспендединстанцеманажемент, который выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ca779-121">From a Visual Studio 2010 command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>

        1. <span data-ttu-id="ca779-122">Создает базу данных сохраняемости с использованием SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="ca779-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="ca779-123">Если база данных сохраняемости уже существует, то она будет удалена и создана повторно.</span><span class="sxs-lookup"><span data-stu-id="ca779-123">If the persistence database already exists, then it is dropped and re-created</span></span>

        2. <span data-ttu-id="ca779-124">Настраивает базу данных с учетом требований сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="ca779-124">Sets up the database for persistence.</span></span>

        3. <span data-ttu-id="ca779-125">Добавляет IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service к роли InstanceStoreUsers, которая была определена при настройке базы данных для сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="ca779-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>

3. <span data-ttu-id="ca779-126">Настройка очереди обслуживания.</span><span class="sxs-lookup"><span data-stu-id="ca779-126">Set up the service queue.</span></span>

    1. <span data-ttu-id="ca779-127">В Visual Studio 2010 щелкните правой кнопкой мыши проект **самплеворкфловапп** и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="ca779-127">In Visual Studio 2010, right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>

    2. <span data-ttu-id="ca779-128">Скомпилируйте и запустите Самплеворкфловапп, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ca779-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="ca779-129">Будет создана требуемая очередь.</span><span class="sxs-lookup"><span data-stu-id="ca779-129">This will create the required queue.</span></span>

    3. <span data-ttu-id="ca779-130">Нажмите клавишу **Ввод** , чтобы прерывать самплеворкфловапп.</span><span class="sxs-lookup"><span data-stu-id="ca779-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>

    4. <span data-ttu-id="ca779-131">Откройте консоль Управление компьютером, выполнив команду Compmgmt.msc из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ca779-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>

    5. <span data-ttu-id="ca779-132">Разверните узел **служба и приложения**, **очередь сообщений**, **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="ca779-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

    6. <span data-ttu-id="ca779-133">Щелкните правой кнопкой мыши очередь **рецеиветкс** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca779-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>

    7. <span data-ttu-id="ca779-134">Перейдите на вкладку **Безопасность** и разрешите **всем пользователям** иметь разрешения на **Получение сообщения**, **Просмотр сообщения**и **Отправка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="ca779-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>

4. <span data-ttu-id="ca779-135">После этого выполните образец.</span><span class="sxs-lookup"><span data-stu-id="ca779-135">Now, run the sample.</span></span>

    1. <span data-ttu-id="ca779-136">В Visual Studio 2010 снова запустите проект Самплеворкфловапп без отладки, нажав клавиши **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="ca779-136">In Visual Studio 2010, run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="ca779-137">В окне консоли будут выведены два адреса конечных точек: один для конечной точки приложения и еще один из <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="ca779-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="ca779-138">Затем будет создан экземпляр рабочего процесса и в окне консоли появятся записи отслеживания для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ca779-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="ca779-139">Экземпляр рабочего процесса вызовет исключение, в результате чего работа экземпляра будет приостановлена и прервана.</span><span class="sxs-lookup"><span data-stu-id="ca779-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>

    2. <span data-ttu-id="ca779-140">После этого с помощью программы командной строки можно будет выполнить дальнейшие действий с любым из этих экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ca779-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="ca779-141">Синтаксис аргументов командной строки:</span><span class="sxs-lookup"><span data-stu-id="ca779-141">The syntax for command line arguments is as follows::</span></span>

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         <span data-ttu-id="ca779-142">Поддерживаемые команды: `Query`, `Resume` и `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="ca779-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="ca779-143">Параметр InstanceId требуется только для операций `Resume` и `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="ca779-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="ca779-144">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ca779-144">To cleanup (Optional)</span></span>

1. <span data-ttu-id="ca779-145">Откройте консоль управления компьютером, запустив команду Compmgmt.msc в командной строке `vs2010`.</span><span class="sxs-lookup"><span data-stu-id="ca779-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>

2. <span data-ttu-id="ca779-146">Разверните узел **служба и приложения**, **очередь сообщений**, **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="ca779-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

3. <span data-ttu-id="ca779-147">Удалите очередь **рецеиветкс** .</span><span class="sxs-lookup"><span data-stu-id="ca779-147">Delete the **ReceiveTx** queue.</span></span>

4. <span data-ttu-id="ca779-148">Для удаления базы данных сохраняемости выполните команду cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="ca779-148">To remove the persistence database, run cleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca779-149">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ca779-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ca779-150">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ca779-150">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="ca779-151">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="ca779-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ca779-152">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ca779-152">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
