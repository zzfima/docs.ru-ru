---
title: "Прием через буфер"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 974c053c3d5aae517e6acbd0e61e1bb96340ee65
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="buffered-receive"></a><span data-ttu-id="9a798-102">Прием через буфер</span><span class="sxs-lookup"><span data-stu-id="9a798-102">Buffered Receive</span></span>
<span data-ttu-id="9a798-103">Этот образец показывает, как настроить и сконфигурировать функцию буфера получения в [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a798-103">This sample demonstrates how to set up and configure the buffered receive feature in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="9a798-104">Функция буфера получения позволяет автору рабочего процесса создавать рабочий процесс, не заботясь о том, в каком порядке получаются сообщения.</span><span class="sxs-lookup"><span data-stu-id="9a798-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="9a798-105">Функция буфера получения осуществляет буферизацию сообщений на локальном уровне и доставляет их, как только рабочий процесс готов к их получению.</span><span class="sxs-lookup"><span data-stu-id="9a798-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9a798-106">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="9a798-106">Demonstrates</span></span>  
 <span data-ttu-id="9a798-107">Обработка внеочередных сообщений с использованием функции буфера получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="9a798-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a798-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9a798-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9a798-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9a798-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a798-110">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a798-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a798-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9a798-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="9a798-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="9a798-112">Discussion</span></span>  
 <span data-ttu-id="9a798-113">В этом образце служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] реализуется с использованием [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Эта служба выполняет последовательность действий <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="9a798-113">In this sample, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="9a798-114">Данный рабочий процесс моделирует простой процесс утверждения заявок на получение кредита. Рабочий процесс предполагает утверждение трех уведомлений на получение кредита.</span><span class="sxs-lookup"><span data-stu-id="9a798-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="9a798-115">Клиентское приложение [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] отправляет три связанных между собой уведомления в порядке, обратном тому, который ожидает служба.</span><span class="sxs-lookup"><span data-stu-id="9a798-115">A [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="9a798-116">Поскольку функция буфера получения в этой службе включена, любое внеочередное сообщение помещается в буфер службы и будет обработано, как только рабочий процесс будет готов к его получению.</span><span class="sxs-lookup"><span data-stu-id="9a798-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="9a798-117">Поскольку функция буфера получения требует поддержки <xref:System.ServiceModel.Activities.ReceiveContent> через привязку, в ней используется <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="9a798-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="9a798-118">Привязка не требует специальной настройки, поэтому используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a798-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="9a798-119">Служба также предоставляет метаданные службы, используя для этого <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="9a798-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="9a798-120">Конечная точка клиента настраивается аналогично, с использованием <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="9a798-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="9a798-121">Код клиента и его конфигурация формируются с помощью **добавить ссылку на службу** функция [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a798-121">The client code and configuration is generated by using the **Add Service Reference** feature of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="9a798-122">В следующем примере в файле App.config формируется конечная точка клиента.</span><span class="sxs-lookup"><span data-stu-id="9a798-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="9a798-123">Для этого образца необходимо включить следующие компоненты Windows.</span><span class="sxs-lookup"><span data-stu-id="9a798-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="9a798-124"> Совместимость управления, метабаза и совместимость конфигурации</span><span class="sxs-lookup"><span data-stu-id="9a798-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="9a798-125">Службы Интернета, компоненты разработки приложений и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9a798-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="9a798-126">Сервер очереди сообщений (Майкрософт) (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="9a798-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="9a798-127">Настройка и сборка образца</span><span class="sxs-lookup"><span data-stu-id="9a798-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="9a798-128">Находясь в командной строке [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], зарегистрируйте ASP.NET, введя команду `aspnet_regiis –I`, затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9a798-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="9a798-129">Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="9a798-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="9a798-130">Откройте LoanService.sln.</span><span class="sxs-lookup"><span data-stu-id="9a798-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="9a798-131">При появлении запроса, если вы хотите создать виртуальные каталоги для проекта LoanService, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="9a798-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="9a798-132">Настройка очередей обслуживания</span><span class="sxs-lookup"><span data-stu-id="9a798-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="9a798-133">Нажмите клавишу F5 для запуска приложения LoanClient, создающего очереди и активирующего службы, определенные в Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="9a798-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="9a798-134">Откройте **Управление компьютером** консоли, выполнив команду Compmgmt.msc из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9a798-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="9a798-135">В **Управление компьютером** консоли, разверните **службы**, **приложений**, **очереди сообщений**, **частные очереди** .</span><span class="sxs-lookup"><span data-stu-id="9a798-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="9a798-136">Щелкните правой кнопкой мыши очередь loanservice/service1.xamlx и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="9a798-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="9a798-137">Выберите **безопасности** и добавьте **сообщение получают все**, **Просмотр сообщения** и **Отправка сообщения** разрешения.</span><span class="sxs-lookup"><span data-stu-id="9a798-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="9a798-138">Откройте диспетчер служб [!INCLUDE[iis60](../../../../includes/iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a798-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="9a798-139">Перейдите к **сервера**, **сайтов**, **по умолчанию веб-сайт**, **закрытый**, **LoanService** и выберите  **Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="9a798-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="9a798-140">Изменение **включенные протоколы** быть **http**, **net.msmq**.</span><span class="sxs-lookup"><span data-stu-id="9a798-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="9a798-141">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="9a798-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="9a798-142">Чтобы убедиться, что служба запущена, перейдите на страницу http://localhost/private/loanservice/service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="9a798-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="9a798-143">Нажмите клавишу F5, чтобы запустить приложение LoanClient.</span><span class="sxs-lookup"><span data-stu-id="9a798-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="9a798-144">После завершения рабочего процесса в папке C:\Inbox должен быть сохранен файл out.txt с результатом обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9a798-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="9a798-145">Очистка</span><span class="sxs-lookup"><span data-stu-id="9a798-145">To clean up</span></span>  
  
1.  <span data-ttu-id="9a798-146">Откройте **Управление компьютером** консоли, выполнив команду Compmgmt.msc из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9a798-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="9a798-147">Разверните **службы** и **приложений**, **очереди сообщений**, **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="9a798-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="9a798-148">Удалите очередь loanservice/service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="9a798-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="9a798-149">Удалите каталог C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="9a798-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a798-150">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9a798-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9a798-151">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9a798-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a798-152">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a798-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a798-153">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9a798-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
