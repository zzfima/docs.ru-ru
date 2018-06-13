---
title: Абсолютная задержка
ms.date: 03/30/2017
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
ms.openlocfilehash: 3a104f6b879e9cdc899bad2201ad1ed320a38a2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518389"
---
# <a name="absolute-delay"></a><span data-ttu-id="7a30f-102">Абсолютная задержка</span><span class="sxs-lookup"><span data-stu-id="7a30f-102">Absolute Delay</span></span>
<span data-ttu-id="7a30f-103">Основной сценарий в этом образце - задержка до указанного значения <xref:System.DateTime> с помощью устойчивых таймеров в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7a30f-103">The main scenario for this sample is to delay until a specified <xref:System.DateTime> using durable timers in a workflow application.</span></span> <span data-ttu-id="7a30f-104">Эффект будет отличаться от применения встроенного действия <xref:System.Activities.Statements.Delay>, так как в этом случае задержка возможна только в течение заданного значения <xref:System.TimeSpan> (или количества минут и секунд).</span><span class="sxs-lookup"><span data-stu-id="7a30f-104">This is different from using the built-in <xref:System.Activities.Statements.Delay> activity as this will only allow you to delay for a given <xref:System.TimeSpan> (or number of minutes/seconds).</span></span>  
  
 <span data-ttu-id="7a30f-105">В реальной жизни такое разделение может быть реализовано в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="7a30f-105">Some real-life scenarios in which you may want to make this distinction include the following:</span></span>  
  
1.  <span data-ttu-id="7a30f-106">Требуется отложить отправку почты на 30 секунд, чтобы убедиться, что в сообщении нет ошибок.</span><span class="sxs-lookup"><span data-stu-id="7a30f-106">You want to delay sending a mail for 30 seconds to make sure you didn’t make any errors.</span></span>  
  
2.  <span data-ttu-id="7a30f-107">Во время сверхурочной работы требуется отложить обработку почты до начала рабочего дня (например, до 8 часов утра).</span><span class="sxs-lookup"><span data-stu-id="7a30f-107">You are working overtime and want to delay all of your mails until normal business hours (such as 8 am).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7a30f-108">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="7a30f-108">Demonstrates</span></span>  
  
1.  <span data-ttu-id="7a30f-109"><xref:System.Activities.Statements.DurableTimerExtension> для реализации абсолютной задержки</span><span class="sxs-lookup"><span data-stu-id="7a30f-109"><xref:System.Activities.Statements.DurableTimerExtension> for implementing Absolute Delay</span></span>  
  
2.  <span data-ttu-id="7a30f-110">Настройка сохранения состояния с помощью устойчивых таймеров <xref:System.Activities.WorkflowApplication></span><span class="sxs-lookup"><span data-stu-id="7a30f-110">Setting up persistence using <xref:System.Activities.WorkflowApplication> for Durable Timers</span></span>  
  
3.  <span data-ttu-id="7a30f-111">Использование <xref:System.Activities.NativeActivity%601> для точек расширения</span><span class="sxs-lookup"><span data-stu-id="7a30f-111">Use of <xref:System.Activities.NativeActivity%601> for using Extensibility points</span></span>  
  
4.  <span data-ttu-id="7a30f-112">Использование <xref:System.Activities.CodeActivity%601> в действии SendEmail</span><span class="sxs-lookup"><span data-stu-id="7a30f-112">Use of <xref:System.Activities.CodeActivity%601> in the SendEmail activity</span></span>  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  <span data-ttu-id="7a30f-113">Только для рабочего процесса XAML</span><span class="sxs-lookup"><span data-stu-id="7a30f-113">XAML-only workflow</span></span>  
  
 <span data-ttu-id="7a30f-114">В этом образце показано создание пользовательского действия, которое принимает значение <xref:System.DateTime> и использует устойчивые таймеры для регистрации длительности задержки.</span><span class="sxs-lookup"><span data-stu-id="7a30f-114">This sample demonstrates how to create a custom activity which takes in a <xref:System.DateTime> and uses durable timers to register the delay duration.</span></span> <span data-ttu-id="7a30f-115">При использовании устойчивого таймера необходимо создать закладку с помощью <xref:System.Activities.NativeActivity>, так как она должна быть зарегистрирована в расширении таймера.</span><span class="sxs-lookup"><span data-stu-id="7a30f-115">When using durable timers, you must use a <xref:System.Activities.NativeActivity> to create a bookmark, as you will need to register this bookmark with the timer extension.</span></span> <span data-ttu-id="7a30f-116">В этом образце по истечении устойчивого таймера будет вызван метод `OnTimerExpired`.</span><span class="sxs-lookup"><span data-stu-id="7a30f-116">In this sample, when the durable timer expires, the `OnTimerExpired` method will be called.</span></span> <span data-ttu-id="7a30f-117">Убедитесь, что в событие <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> добавляется расширение таймера, чтобы обеспечить получение этих сведений средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="7a30f-117">Make sure that you are adding the timer extension in the <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> event to ensure you are providing the runtime with this information.</span></span> <span data-ttu-id="7a30f-118">Единственное отличие в реализации состоит в том, что потребуется реализовать логику для преобразования <xref:System.DateTime> в <xref:System.TimeSpan>, так как устойчивые таймеры принимают только значения <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="7a30f-118">The only other implementation detail is that you will need to implement logic to convert from <xref:System.DateTime> to <xref:System.TimeSpan>, as durable timers only take in a <xref:System.DateTime>.</span></span> <span data-ttu-id="7a30f-119">Помните, что при этом возникнет некоторая потеря точности</span><span class="sxs-lookup"><span data-stu-id="7a30f-119">Do note that there is a small lapse in accuracy by doing</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a30f-120">При преобразовании из <xref:System.DateTime> в <xref:System.TimeSpan> произойдет небольшая потеря точности.</span><span class="sxs-lookup"><span data-stu-id="7a30f-120">There is a small loss of accuracy by converting from <xref:System.DateTime> to <xref:System.TimeSpan>.</span></span>  
  
 <span data-ttu-id="7a30f-121">В этом образце также демонстрируется включение сохранения для <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="7a30f-121">This sample also demonstrates how to turn on persistence for a <xref:System.Activities.WorkflowApplication>.</span></span> <span data-ttu-id="7a30f-122">В этом образце мы будем использовать устойчивые таймеры, которые предполагают выгрузку данных рабочего процесса в базу данных сохраняемости во время простоя до истечения срока действия таймера.</span><span class="sxs-lookup"><span data-stu-id="7a30f-122">For this particular sample, we will be using durable timers in which the workflow data will be unloaded into the persistence database during the idle time while waiting for timer to expire.</span></span> <span data-ttu-id="7a30f-123">Эта реализация может быть также использована для других действий сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="7a30f-123">This implementation can also be used for other persistence actions.</span></span> <span data-ttu-id="7a30f-124">В этом образце показано, как настроить строку подключения сохранения в SQL Server и как создать хранилище экземпляра для сохранения данных экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="7a30f-124">This sample shows how to set up the persistence connection string with SQL Server, and how to create the instance store in order to persist the data for workflow instances.</span></span> <span data-ttu-id="7a30f-125">Приведена логика, позволяющая возобновить рабочий процесс после возникновения события, после которого экземпляр рабочего процесса станет готов к запуску.</span><span class="sxs-lookup"><span data-stu-id="7a30f-125">Logic is provided on how to resume the workflow once an event is raised which makes the workflow instance runnable.</span></span>  
  
 <span data-ttu-id="7a30f-126">При пошаговом выполнении в этом примере вы увидите, что время, в котором встроенной задержки начала и завершения, который в свою очередь, вызовет сообщение электронной почты, отправляемых.</span><span class="sxs-lookup"><span data-stu-id="7a30f-126">As you step through this sample, you will see the time in which the built-in delay begins and completes, which in turn will cause an email message to be sent.</span></span> <span data-ttu-id="7a30f-127">Таким образом, действие AbsoluteDelay создаст задержку до наступления указанного значения <xref:System.DateTime> (или 0 секунд, если срок <xref:System.DateTime> истек), что, в свою очередь, вызовет отправку сообщения после истечения срока.</span><span class="sxs-lookup"><span data-stu-id="7a30f-127">From there, the AbsoluteDelay activity will halt until a specified <xref:System.DateTime> (or 0 seconds if the <xref:System.DateTime> has expired) which in turn will send out an email upon expiration.</span></span> <span data-ttu-id="7a30f-128">Будет показано два случая применения встроенной функции <xref:System.Activities.Statements.Delay> по сравнению с использованием действия AbsoluteDelay.</span><span class="sxs-lookup"><span data-stu-id="7a30f-128">This will show the two different use cases of the built-in <xref:System.Activities.Statements.Delay> functionality versus using an AbsoluteDelay activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7a30f-129">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="7a30f-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7a30f-130">Убедитесь, что на компьютере установлен SQL Server Express (или более новая версия).</span><span class="sxs-lookup"><span data-stu-id="7a30f-130">Ensure you have SQL Server Express (or higher) installed on your machine</span></span>  
  
2.  <span data-ttu-id="7a30f-131">Запустите файл setup.cmd (из каталога WF/Basic/Services/AbsoluteDelay/CS) в командной строке [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], чтобы создать базу данных AbsoluteDelaySampleDB, схему сохраняемости и логику сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="7a30f-131">Run setup.cmd (from WF/Basic/Services/AbsoluteDelay/CS) in a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt to create the AbsoluteDelaySampleDB database, create the persistence schema and create the persistence logic.</span></span>  
  
3.  <span data-ttu-id="7a30f-132">Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a30f-132">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="7a30f-133">Укажите длительность действия Delay.</span><span class="sxs-lookup"><span data-stu-id="7a30f-133">Specify the Duration in the Delay activity.</span></span>  
  
5.  <span data-ttu-id="7a30f-134">Укажите параметр ExpirationTime в действии AbsoluteDelay.</span><span class="sxs-lookup"><span data-stu-id="7a30f-134">Specify the ExpirationTime in the AbsoluteDelay activity.</span></span>  
  
6.  <span data-ttu-id="7a30f-135">Обновите поля SendMailTo, SendMailFrom, SendMailSubject, SendMailBody и SmtpHost в действии SendMail.</span><span class="sxs-lookup"><span data-stu-id="7a30f-135">Update the SendMailTo, SendMailFrom, SendMailSubject, SendMailBody, and SmtpHost fields in the SendMail activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a30f-136">Если не указан допустимый узел SMTP, приложение выдаст исключение SMTP.</span><span class="sxs-lookup"><span data-stu-id="7a30f-136">If you do not enter a valid SMTP host, the application will throw a SMTP exception.</span></span>  
  
7.  <span data-ttu-id="7a30f-137">Постройте решение, выбрав **построения**, **построить решение**.</span><span class="sxs-lookup"><span data-stu-id="7a30f-137">Build the solution by selecting **Build**, **Build Solution**.</span></span>  
  
8.  <span data-ttu-id="7a30f-138">Запустите решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="7a30f-138">Run the solution by pressing **F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7a30f-139">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7a30f-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7a30f-140">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7a30f-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7a30f-141">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="7a30f-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7a30f-142">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7a30f-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
