---
title: "Каналы WCF с поддержкой ReceiveContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 729bf8bd1371bf64b9b05a235331120608824083
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="8d730-102">Каналы WCF с поддержкой ReceiveContext</span><span class="sxs-lookup"><span data-stu-id="8d730-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="8d730-103">Данный образец демонстрирует применение каналов WCF с поддержкой <xref:System.ServiceModel.Channels.ReceiveContext>.</span><span class="sxs-lookup"><span data-stu-id="8d730-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="8d730-104">Образец реализует службу для нахождения произведения двух чисел с помощью канала NetMSMQ.</span><span class="sxs-lookup"><span data-stu-id="8d730-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="8d730-105">Класс <xref:System.ServiceModel.Channels.ReceiveContext> позволяет приложению решить, обратиться ли к сообщению или оставить его в очереди для дальнейшей обработки, даже если содержимое сообщения уже было проверено.</span><span class="sxs-lookup"><span data-stu-id="8d730-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="8d730-106">В данном образце клиент отправляет в транзакционную очередь случайные числа.</span><span class="sxs-lookup"><span data-stu-id="8d730-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="8d730-107">Служба `ProductCalculator` получает сообщения, анализирует их содержимое (целые числа) и определяет, можно ли вычислить произведение.</span><span class="sxs-lookup"><span data-stu-id="8d730-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="8d730-108">Если операция службы не вычисляет произведение, сообщение отправляется обратно в очередь и может быть получено вновь службой, прослушивающей очередь.</span><span class="sxs-lookup"><span data-stu-id="8d730-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d730-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d730-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8d730-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8d730-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8d730-111">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d730-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d730-112">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="8d730-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8d730-113">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="8d730-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="8d730-114">Убедитесь, что установлена служба очередей сообщений (Майкрософт) (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8d730-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="8d730-115">Установка службы MSMQ под управлением [!INCLUDE[lserver](../../../../includes/lserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d730-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="8d730-116">В **диспетчера сервера**, нажмите кнопку **функции**.</span><span class="sxs-lookup"><span data-stu-id="8d730-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="8d730-117">В правой панели в разделе **Сводка компонентов**, нажмите кнопку **добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="8d730-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="8d730-118">В появившемся окне разверните **очереди сообщений**.</span><span class="sxs-lookup"><span data-stu-id="8d730-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="8d730-119">Разверните **службы очереди сообщений**.</span><span class="sxs-lookup"><span data-stu-id="8d730-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="8d730-120">Нажмите кнопку **интеграция со службами каталогов** (для компьютеров, присоединенных к домену), а затем нажмите кнопку **поддержка HTTP**.</span><span class="sxs-lookup"><span data-stu-id="8d730-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="8d730-121">Нажмите кнопку **Далее**, а затем нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="8d730-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="8d730-122">Установка службы MSMQ под управлением [!INCLUDE[wv](../../../../includes/wv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d730-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="8d730-123">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="8d730-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="8d730-124">Нажмите кнопку **программы** и затем в разделе **программы и компоненты**, нажмите кнопку **Включение и отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="8d730-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="8d730-125">Разверните **сервер очереди сообщений Microsoft (MSMQ)**, разверните **ядро сервера очереди сообщений Microsoft (MSMQ)**, а затем установите флажки для следующих функций очереди сообщений для установки:</span><span class="sxs-lookup"><span data-stu-id="8d730-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="8d730-126">Сервер службы очередей сообщений</span><span class="sxs-lookup"><span data-stu-id="8d730-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="8d730-127">Интеграция со службами доменов MSMQ Active Directory (для компьютеров, подключенных к домену)</span><span class="sxs-lookup"><span data-stu-id="8d730-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="8d730-128">Поддержка MSMQ HTTP</span><span class="sxs-lookup"><span data-stu-id="8d730-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="8d730-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8d730-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="8d730-130">При появлении запроса на перезагрузку компьютера нажмите кнопку **ОК** для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="8d730-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="8d730-131">Убедитесь, что на компьютере установлена среда [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d730-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="8d730-132">Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл решения ReceiveContextProductGenerator.sln.</span><span class="sxs-lookup"><span data-stu-id="8d730-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="8d730-133">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="8d730-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="8d730-134">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="8d730-134">To run the solution, press CTRL+F5.</span></span>
