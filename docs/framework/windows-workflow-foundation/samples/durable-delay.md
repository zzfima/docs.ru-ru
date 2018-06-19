---
title: Сохраняемая задержка
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 5307b8144e17f91cd3ba8c2e385492f86c167820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516026"
---
# <a name="durable-delay"></a><span data-ttu-id="81804-102">Сохраняемая задержка</span><span class="sxs-lookup"><span data-stu-id="81804-102">Durable Delay</span></span>
<span data-ttu-id="81804-103">В этом образце показано, как использовать сохраняемую задержку, при которой рабочий процесс сохраняется на физическом устройстве.</span><span class="sxs-lookup"><span data-stu-id="81804-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="81804-104">Образец рабочего процесса содержит два сообщения на консоль, разделенных задержкой.</span><span class="sxs-lookup"><span data-stu-id="81804-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="81804-105">Когда запускается задержка, рабочий процесс выгружается и в течение 5 секунд хранится в хранилище экземпляров рабочих процессов, а затем снова загружается в память.</span><span class="sxs-lookup"><span data-stu-id="81804-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="81804-106">Подробные сведения о рабочем процессе</span><span class="sxs-lookup"><span data-stu-id="81804-106">Workflow Details</span></span>  
 <span data-ttu-id="81804-107">Узел службы рабочего процесса, на котором размещен рабочий процесс, управляет экземплярами рабочих процессов, загружая и выгружая их.</span><span class="sxs-lookup"><span data-stu-id="81804-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="81804-108">Для запуска экземпляра определения рабочего процесса в образце создается прокси, отправляющий сообщение действию <xref:System.ServiceModel.Activities.Receive> в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="81804-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="81804-109">Свойство <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> устанавливается в значение `true`, что позволяет ему после получения сообщения создать новый экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81804-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="81804-110">В следующем списке показана настройка узла службы рабочего процесса во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="81804-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="81804-111">Создает узел службы с адресом (http://localhost:8080/Client).</span><span class="sxs-lookup"><span data-stu-id="81804-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="81804-112">Создается конечная точка в узле службы для обеспечения взаимодействия с действием <xref:System.ServiceModel.Activities.Receive> в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="81804-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="81804-113">Настраивается хранилище экземпляров SQL.</span><span class="sxs-lookup"><span data-stu-id="81804-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="81804-114">Добавляется поведение выгрузки экземпляра, устанавливающее условия, при которых узел службы рабочего процесса будет производить выгрузку экземпляров рабочего процесса в хранилище сохраняемости SQL.</span><span class="sxs-lookup"><span data-stu-id="81804-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="81804-115">В этом образце экземпляр выгружается сразу после того, как рабочий процесс становится бездействующим (когда запускается задержка).</span><span class="sxs-lookup"><span data-stu-id="81804-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="81804-116">Создается прокси, отправляющий сообщение действию <xref:System.ServiceModel.Activities.Receive> в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="81804-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="81804-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="81804-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="81804-118">Настройка базы данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="81804-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="81804-119">Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81804-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="81804-120">Перейдите к [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] каталога (C:\Windows\Microsoft.NET\Framework\v4. X\\).</span><span class="sxs-lookup"><span data-stu-id="81804-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="81804-121">Измените файл WorkflowManagementService.exe.config и добавьте следующую строку подключения в элемент <`database`>.</span><span class="sxs-lookup"><span data-stu-id="81804-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="81804-122">Перейдите в каталог DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="81804-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="81804-123">Запустите команду Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="81804-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="81804-124">Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными правами, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="81804-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="81804-125">Откройте файл решения Delay.sln.</span><span class="sxs-lookup"><span data-stu-id="81804-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="81804-126">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="81804-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="81804-127">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="81804-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="81804-128">Удаление этого образца</span><span class="sxs-lookup"><span data-stu-id="81804-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="81804-129">Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81804-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="81804-130">Перейдите в каталог DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="81804-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="81804-131">Запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="81804-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81804-132">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="81804-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="81804-133">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="81804-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="81804-134">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="81804-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="81804-135">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="81804-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`