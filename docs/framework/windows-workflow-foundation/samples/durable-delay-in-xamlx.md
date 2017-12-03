---
title: "Сохраняемая задержка в XAMLX"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7396c5ca2119dcf096036695233d5c89a3f014f7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="3ace3-102">Сохраняемая задержка в XAMLX</span><span class="sxs-lookup"><span data-stu-id="3ace3-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="3ace3-103">В этом образце показано, как использовать сохраняемую задержку, при которой рабочий процесс сохраняется на физическом устройстве.</span><span class="sxs-lookup"><span data-stu-id="3ace3-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3ace3-104">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ace3-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3ace3-105">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3ace3-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3ace3-106">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ace3-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3ace3-107">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3ace3-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="3ace3-108">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="3ace3-108">Discussion</span></span>  
 <span data-ttu-id="3ace3-109">Образец рабочего процесса содержит два сообщения для локального файла, разделенных задержкой.</span><span class="sxs-lookup"><span data-stu-id="3ace3-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="3ace3-110">Когда запускается задержка, рабочий процесс выгружается и в течение 5 секунд хранится в хранилище экземпляров рабочих процессов, а затем снова загружается в память.</span><span class="sxs-lookup"><span data-stu-id="3ace3-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="3ace3-111">Файл XAMLX представляет собой службу Workflow Service, размещенную в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ace3-111">The .xamlx file is a workflow service that is hosted in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="3ace3-112"> использует сервер Cassini, в котором для размещения рабочего процесса применяется узел службы Workflow Service.</span><span class="sxs-lookup"><span data-stu-id="3ace3-112"> uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="3ace3-113">Кроме размещения рабочего процесса, узел службы рабочего процесса управляет экземплярами рабочих процессов, загружая их и выгружая.</span><span class="sxs-lookup"><span data-stu-id="3ace3-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="3ace3-114">Для запуска экземпляра определения [!INCLUDE[wf](../../../../includes/wf-md.md)] (на узле службы рабочего процесса) укажите клиент, который отправляет сообщение действию <xref:System.ServiceModel.Activities.Receive> рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3ace3-114">To start an instance of the [!INCLUDE[wf](../../../../includes/wf-md.md)] definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="3ace3-115">Объект <xref:System.ServiceModel.Activities.Receive> используется со значением свойства <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>, равным `true`, что позволяет ему создать новый экземпляр рабочего процесса при получении сообщения.</span><span class="sxs-lookup"><span data-stu-id="3ace3-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="3ace3-116">В процессе инициализации в файл конфигурации добавляется поведение выгрузки экземпляра, которое указывает узлу службы рабочего процесса, при каких обстоятельствах он должен выгружать экземпляр в хранилище (базу данных) сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="3ace3-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="3ace3-117">В этом образце экземпляр выгружается сразу после того, как рабочий процесс становится бездействующим (когда запускается задержка).</span><span class="sxs-lookup"><span data-stu-id="3ace3-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3ace3-118">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="3ace3-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="3ace3-119">Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ace3-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="3ace3-120">Перейдите в папку DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="3ace3-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="3ace3-121">Запустите команду Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="3ace3-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="3ace3-122">Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3ace3-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="3ace3-123">Откройте файл решения DurableDelayXamlx.sln.</span><span class="sxs-lookup"><span data-stu-id="3ace3-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="3ace3-124">В **обозревателе решений**, щелкните правой кнопкой мыши решение и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="3ace3-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="3ace3-125">Выберите **несколько запускаемых проектов** и задайте обоим проектам значение **запустить**.</span><span class="sxs-lookup"><span data-stu-id="3ace3-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="3ace3-126">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="3ace3-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="3ace3-127">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="3ace3-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="3ace3-128">Удаление этого образца</span><span class="sxs-lookup"><span data-stu-id="3ace3-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="3ace3-129">Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ace3-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="3ace3-130">Перейдите в папку DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="3ace3-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="3ace3-131">Запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="3ace3-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3ace3-132">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ace3-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3ace3-133">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3ace3-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3ace3-134">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ace3-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3ace3-135">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3ace3-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
