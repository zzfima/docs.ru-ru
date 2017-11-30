---
title: "Практическое руководство. Запись сведений о службах в журнал"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 612b983f53f147102ddf7bab03d4ec6783dc4026
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-log-information-about-services"></a><span data-ttu-id="f86c7-102">Практическое руководство. Запись сведений о службах в журнал</span><span class="sxs-lookup"><span data-stu-id="f86c7-102">How to: Log Information About Services</span></span>
<span data-ttu-id="f86c7-103">По умолчанию все проекты служб Windows могут взаимодействовать с журналом событий приложения и записывать в него сведения и исключения.</span><span class="sxs-lookup"><span data-stu-id="f86c7-103">By default, all Windows Service projects have the ability to interact with the Application event log and write information and exceptions to it.</span></span> <span data-ttu-id="f86c7-104">Чтобы указать, что эта функциональность должна быть в вашем приложении, можно использовать свойство <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> .</span><span class="sxs-lookup"><span data-stu-id="f86c7-104">You use the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to indicate whether you want this functionality in your application.</span></span> <span data-ttu-id="f86c7-105">По умолчанию ведение журнала включено для любой службы, созданной с помощью шаблона проекта службы Windows.</span><span class="sxs-lookup"><span data-stu-id="f86c7-105">By default, logging is turned on for any service you create with the Windows Service project template.</span></span> <span data-ttu-id="f86c7-106">Можно использовать статическую форму класса <xref:System.Diagnostics.EventLog> для записи сведений в журнал, и тогда не потребуется создавать экземпляр компонента <xref:System.Diagnostics.EventLog> или вручную регистрировать источник.</span><span class="sxs-lookup"><span data-stu-id="f86c7-106">You can use a static form of the <xref:System.Diagnostics.EventLog> class to write service information to a log without having to create an instance of an <xref:System.Diagnostics.EventLog> component or manually register a source.</span></span>  
  
 <span data-ttu-id="f86c7-107">Установщик службы автоматически регистрирует каждую службу в проекте как допустимый источник событий для журнала приложений на компьютере, где установлена служба, если включено ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="f86c7-107">The installer for your service automatically registers each service in your project as a valid source of events with the Application log on the computer where the service is installed, when logging is turned on.</span></span> <span data-ttu-id="f86c7-108">Служба записывает сведения каждый раз, когда служба запускается, останавливается, приостанавливается, возобновляется, устанавливается или удаляется.</span><span class="sxs-lookup"><span data-stu-id="f86c7-108">The service logs information each time the service is started, stopped, paused, resumed, installed, or uninstalled.</span></span> <span data-ttu-id="f86c7-109">Она также записывает все возникающие ошибки.</span><span class="sxs-lookup"><span data-stu-id="f86c7-109">It also logs any failures that occur.</span></span> <span data-ttu-id="f86c7-110">Вам не нужно писать никакой код для записи в журнал при использовании этого поведения по умолчанию; служба обрабатывает это автоматически.</span><span class="sxs-lookup"><span data-stu-id="f86c7-110">You do not need to write any code to write entries to the log when using the default behavior; the service handles this for you automatically.</span></span>  
  
 <span data-ttu-id="f86c7-111">Если вы хотите выполнять запись в другой журнал событий, отличный от журнала приложения, то необходимо задать для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> значение `false`, создать собственный пользовательский журнал событий в коде службы и зарегистрировать службу в качестве источника записей для этого журнала.</span><span class="sxs-lookup"><span data-stu-id="f86c7-111">If you want to write to an event log other than the Application log, you must set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`, create your own custom event log within your services code, and register your service as a valid source of entries for that log.</span></span> <span data-ttu-id="f86c7-112">Затем вам придется написать код для выполнения записи в журнал всякий раз, когда происходит интересующее вас действие.</span><span class="sxs-lookup"><span data-stu-id="f86c7-112">You must then write code to record entries to the log whenever an action you're interested in occurs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f86c7-113">Если вы используете пользовательский журнал событий и настроили службу для записи в этот журнал, не пытайтесь обратиться к этому журналу до установки свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> службы в коде.</span><span class="sxs-lookup"><span data-stu-id="f86c7-113">If you use a custom event log and configure your service application to write to it, you must not attempt to access the event log before setting the service's <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property in your code.</span></span> <span data-ttu-id="f86c7-114">Журналу событий нужно значение этого свойства, чтобы зарегистрировать службу в качестве допустимого источника событий.</span><span class="sxs-lookup"><span data-stu-id="f86c7-114">The event log needs this property's value to register your service as a valid source of events.</span></span>  
  
### <a name="to-enable-default-event-logging-for-your-service"></a><span data-ttu-id="f86c7-115">Включение ведения журнала событий по умолчанию для службы</span><span class="sxs-lookup"><span data-stu-id="f86c7-115">To enable default event logging for your service</span></span>  
  
-   <span data-ttu-id="f86c7-116">Установите для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> вашего компонента значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f86c7-116">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f86c7-117">По умолчанию для свойства задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f86c7-117">By default, this property is set to `true`.</span></span> <span data-ttu-id="f86c7-118">Вам не нужно задавать это явно, если только вы не создаете более сложную обработку, такую как оценка условия и последующая установка свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> в зависимости от результата этого условия.</span><span class="sxs-lookup"><span data-stu-id="f86c7-118">You do not need to set this explicitly unless you are building more complex processing, such as evaluating a condition and then setting the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property based on the result of that condition.</span></span>  
  
### <a name="to-disable-event-logging-for-your-service"></a><span data-ttu-id="f86c7-119">Отключение ведения журнала событий для службы</span><span class="sxs-lookup"><span data-stu-id="f86c7-119">To disable event logging for your service</span></span>  
  
-   <span data-ttu-id="f86c7-120">Установите для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> вашего компонента значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f86c7-120">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `false`.</span></span>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a><span data-ttu-id="f86c7-121">Настройка ведения пользовательского журнала</span><span class="sxs-lookup"><span data-stu-id="f86c7-121">To set up logging to a custom log</span></span>  
  
1.  <span data-ttu-id="f86c7-122">Задайте для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f86c7-122">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f86c7-123">Чтобы использовать пользовательский журнал, необходимо задать в свойстве <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> значение false.</span><span class="sxs-lookup"><span data-stu-id="f86c7-123">You must set <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> to false in order to use a custom log.</span></span>  
  
2.  <span data-ttu-id="f86c7-124">Настройте экземпляр компонента <xref:System.Diagnostics.EventLog> в приложении службы Windows.</span><span class="sxs-lookup"><span data-stu-id="f86c7-124">Set up an instance of an <xref:System.Diagnostics.EventLog> component in your Windows Service application.</span></span>  
  
3.  <span data-ttu-id="f86c7-125">Создайте пользовательский журнал, вызвав метод <xref:System.Diagnostics.EventLog.CreateEventSource%2A> и задав исходную строку и имя файла журнала, который хотите создать.</span><span class="sxs-lookup"><span data-stu-id="f86c7-125">Create a custom log by calling the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method and specifying the source string and the name of the log file you want to create.</span></span>  
  
4.  <span data-ttu-id="f86c7-126">Укажите в свойстве <xref:System.Diagnostics.EventLog.Source%2A> компонента <xref:System.Diagnostics.EventLog> исходную строку, созданную на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f86c7-126">Set the <xref:System.Diagnostics.EventLog.Source%2A> property on the <xref:System.Diagnostics.EventLog> component instance to the source string you created in step 3.</span></span>  
  
5.  <span data-ttu-id="f86c7-127">Выполняйте запись в журнал, вызывая метод <xref:System.Diagnostics.EventLog.WriteEntry%2A> в экземпляре компонента <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="f86c7-127">Write your entries by accessing the <xref:System.Diagnostics.EventLog.WriteEntry%2A> method on the <xref:System.Diagnostics.EventLog> component instance.</span></span>  
  
     <span data-ttu-id="f86c7-128">Следующий код показывает, как настроить ведение пользовательского журнала.</span><span class="sxs-lookup"><span data-stu-id="f86c7-128">The following code shows how to set up logging to a custom log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f86c7-129">В этом примере кода экземпляр компонента <xref:System.Diagnostics.EventLog> называется `eventLog1` (`EventLog1` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f86c7-129">In this code example, an instance of an <xref:System.Diagnostics.EventLog> component is named `eventLog1` (`EventLog1` in Visual Basic).</span></span> <span data-ttu-id="f86c7-130">Если на шаге 2 вы создали экземпляр с другим именем, измените код соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f86c7-130">If you created an instance with another name in step 2, change the code accordingly.</span></span>  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="f86c7-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f86c7-131">See Also</span></span>  
 [<span data-ttu-id="f86c7-132">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="f86c7-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
