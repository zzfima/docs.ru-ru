---
title: "Управление приостановленным экземпляром"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02c3d6b3a522dd4337dcdf22f884f63cdddd4aa4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="suspended-instance-management"></a><span data-ttu-id="cf403-102">Управление приостановленным экземпляром</span><span class="sxs-lookup"><span data-stu-id="cf403-102">Suspended Instance Management</span></span>
<span data-ttu-id="cf403-103">Этот образец демонстрирует управление экземплярами рабочего процесса, которые были приостановлены.</span><span class="sxs-lookup"><span data-stu-id="cf403-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="cf403-104">Действием по умолчанию для поведения <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> является `AbandonAndSuspend`.</span><span class="sxs-lookup"><span data-stu-id="cf403-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="cf403-105">Это означает, что по умолчанию при появлении необработанных исключений, сформированных экземпляром рабочего процесса, который размещен на узле <xref:System.ServiceModel.WorkflowServiceHost>, экземпляр удаляется из памяти (отбрасывается) и устойчивая/сохраненная версия экземпляра отмечается как приостановленная.</span><span class="sxs-lookup"><span data-stu-id="cf403-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="cf403-106">Приостановленный экземпляр рабочего процесса не будет в состоянии выполняться до отмены приостановки.</span><span class="sxs-lookup"><span data-stu-id="cf403-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>  
  
 <span data-ttu-id="cf403-107">Этот образец показывает, как можно реализовать программу командной строки для выполнения запроса приостановленных экземпляров и как дать пользователю возможность возобновлять или завершать работу экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cf403-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="cf403-108">В этом образце служба рабочего процесса преднамеренно вызывает исключение, в результате чего она приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="cf403-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="cf403-109">Затем с помощью программы командной строки можно будет запросить экземпляр, а после этого возобновить или завершить его работу.</span><span class="sxs-lookup"><span data-stu-id="cf403-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="cf403-110">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="cf403-110">Demonstrates</span></span>  
 <span data-ttu-id="cf403-111">Узел <xref:System.ServiceModel.WorkflowServiceHost> с поведением <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> и <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> в [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf403-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="cf403-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="cf403-112">Discussion</span></span>  
 <span data-ttu-id="cf403-113">Программа командной строки, реализованная в этом образце, предназначена для работы с реализацией хранилища экземпляра SQL Server, который поставляется в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf403-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="cf403-114">Если имеется пользовательская реализация хранилища экземпляра, то можно приспособить и эту программу, заменяя в образце реализации `WorkflowInstanceCommand` реализациями, которые относятся к применяемому хранилищу экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cf403-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>  
  
 <span data-ttu-id="cf403-115">Команды SQL в предоставленной реализации запускаются непосредственно по отношению к хранилищу экземпляра SQL для формирования списка приостановленных экземпляров, а для возобновления или завершения работы экземпляров в ней используется конечная точка <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>, добавленная к узлу <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="cf403-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cf403-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cf403-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cf403-117">Для этого образца необходимо включить следующие компоненты Windows.</span><span class="sxs-lookup"><span data-stu-id="cf403-117">This sample requires that the following Windows components are enabled:</span></span>  
  
    1.  <span data-ttu-id="cf403-118">Сервер очереди сообщений (Майкрософт) (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="cf403-118">Microsoft Message Queues (MSMQ) Server</span></span>  
  
    2.  <span data-ttu-id="cf403-119">SQL Server, экспресс-выпуск</span><span class="sxs-lookup"><span data-stu-id="cf403-119">SQL Server Express</span></span>  
  
2.  <span data-ttu-id="cf403-120">Установка базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf403-120">Set up the SQL Server database.</span></span>  
  
    1.  <span data-ttu-id="cf403-121">Из [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] командной строки запустите команду «setup.cmd» из каталога образцов SuspendedInstanceManagement, которая выполняет следующее:</span><span class="sxs-lookup"><span data-stu-id="cf403-121">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>  
  
        1.  <span data-ttu-id="cf403-122">Создает базу данных сохраняемости с использованием SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="cf403-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="cf403-123">Если база данных сохраняемости уже существует, то она будет удалена и создана повторно.</span><span class="sxs-lookup"><span data-stu-id="cf403-123">If the persistence database already exists, then it is dropped and re-created</span></span>  
  
        2.  <span data-ttu-id="cf403-124">Настраивает базу данных с учетом требований сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="cf403-124">Sets up the database for persistence.</span></span>  
  
        3.  <span data-ttu-id="cf403-125">Добавляет IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service к роли InstanceStoreUsers, которая была определена при настройке базы данных для сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="cf403-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>  
  
3.  <span data-ttu-id="cf403-126">Настройка очереди обслуживания.</span><span class="sxs-lookup"><span data-stu-id="cf403-126">Set up the service queue.</span></span>  
  
    1.  <span data-ttu-id="cf403-127">В [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], щелкните правой кнопкой мыши **SampleWorkflowApp** проекта и нажмите кнопку **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="cf403-127">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>  
  
    2.  <span data-ttu-id="cf403-128">Скомпилируйте и запустите образец SampleWorkflowApp, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="cf403-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="cf403-129">Будет создана требуемая очередь.</span><span class="sxs-lookup"><span data-stu-id="cf403-129">This will create the required queue.</span></span>  
  
    3.  <span data-ttu-id="cf403-130">Нажмите клавишу **ввод** остановить приложение SampleWorkflowApp.</span><span class="sxs-lookup"><span data-stu-id="cf403-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>  
  
    4.  <span data-ttu-id="cf403-131">Откройте консоль «Управление компьютером», выполнив команду Compmgmt.msc из командной строки.</span><span class="sxs-lookup"><span data-stu-id="cf403-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>  
  
    5.  <span data-ttu-id="cf403-132">Разверните **службы и приложения**, **очереди сообщений**, **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="cf403-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    6.  <span data-ttu-id="cf403-133">Щелкните правой кнопкой мыши **ReceiveTx** очередь, а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="cf403-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>  
  
    7.  <span data-ttu-id="cf403-134">Выберите **безопасности** вкладку и разрешить **все** могут иметь разрешения на **получение сообщения**, **Просмотр сообщения**, и  **Отправить сообщение**.</span><span class="sxs-lookup"><span data-stu-id="cf403-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>  
  
4.  <span data-ttu-id="cf403-135">После этого выполните образец.</span><span class="sxs-lookup"><span data-stu-id="cf403-135">Now, run the sample.</span></span>  
  
    1.  <span data-ttu-id="cf403-136">В [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], снова запустите проект SampleWorkflowApp без отладки, нажав **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="cf403-136">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="cf403-137">В окне консоли будут выведены два адреса конечных точек: один для конечной точки приложения и еще один из <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cf403-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="cf403-138">Затем будет создан экземпляр рабочего процесса и в окне консоли появятся записи отслеживания для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cf403-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="cf403-139">Экземпляр рабочего процесса вызовет исключение, в результате чего работа экземпляра будет приостановлена и прервана.</span><span class="sxs-lookup"><span data-stu-id="cf403-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>  
  
    2.  <span data-ttu-id="cf403-140">После этого с помощью программы командной строки можно будет выполнить дальнейшие действий с любым из этих экземпляров.</span><span class="sxs-lookup"><span data-stu-id="cf403-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="cf403-141">Синтаксис аргументов командной строки:</span><span class="sxs-lookup"><span data-stu-id="cf403-141">The syntax for command line arguments is as follows::</span></span>  
  
         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`  
  
         <span data-ttu-id="cf403-142">Поддерживаемые команды: `Query`, `Resume` и `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="cf403-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="cf403-143">Параметр InstanceId требуется только для операций `Resume` и `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="cf403-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="cf403-144">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="cf403-144">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="cf403-145">Откройте консоль управления компьютером, запустив команду Compmgmt.msc в командной строке `vs2010`.</span><span class="sxs-lookup"><span data-stu-id="cf403-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>  
  
2.  <span data-ttu-id="cf403-146">Разверните **службы и приложения**, **очереди сообщений**, **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="cf403-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="cf403-147">Удалить **ReceiveTx** очереди.</span><span class="sxs-lookup"><span data-stu-id="cf403-147">Delete the **ReceiveTx** queue.</span></span>  
  
4.  <span data-ttu-id="cf403-148">Для удаления базы данных сохраняемости выполните команду cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="cf403-148">To remove the persistence database, run cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf403-149">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf403-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cf403-150">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf403-150">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cf403-151">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf403-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cf403-152">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cf403-152">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
