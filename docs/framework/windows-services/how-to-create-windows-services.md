---
title: Практическое руководство. Создание служб Windows
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
manager: douge
ms.openlocfilehash: 7719af9393bee816665040d6e4ced191419d0855
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="d51e5-102">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="d51e5-102">How to: Create Windows Services</span></span>
<span data-ttu-id="d51e5-103">При создании службы, можно использовать шаблон проекта Visual Studio называется **службы Windows**.</span><span class="sxs-lookup"><span data-stu-id="d51e5-103">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="d51e5-104">Этот шаблон автоматически выполняет основную часть работы, ссылаясь на необходимые классы и пространства имен, устанавливая наследование от базового класса для служб и переопределяя некоторые методы, которые вы обычно хотите переопределять.</span><span class="sxs-lookup"><span data-stu-id="d51e5-104">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d51e5-105">Шаблон проекта "Службы Windows" в экспресс-выпуске Visual Studio отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d51e5-105">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="d51e5-106">Для создания функциональной службы необходимо выполнить, как минимум, следующее:</span><span class="sxs-lookup"><span data-stu-id="d51e5-106">At a minimum, to create a functional service you must:</span></span>  
  
-   <span data-ttu-id="d51e5-107">Задайте свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.</span><span class="sxs-lookup"><span data-stu-id="d51e5-107">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
-   <span data-ttu-id="d51e5-108">Создайте установщики, необходимые для приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-108">Create the necessary installers for your service application.</span></span>  
  
-   <span data-ttu-id="d51e5-109">Переопределите и задайте код для методов <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> для настройки режимов поведения службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-109">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="d51e5-110">Создание приложения службы Windows</span><span class="sxs-lookup"><span data-stu-id="d51e5-110">To create a Windows Service application</span></span>  
  
1.  <span data-ttu-id="d51e5-111">Создание **службы Windows** проекта.</span><span class="sxs-lookup"><span data-stu-id="d51e5-111">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d51e5-112">Инструкции по созданию службы без использования шаблона см. в разделе [как: запись службы программным образом](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="d51e5-112">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
2.  <span data-ttu-id="d51e5-113">В **свойства** задайте <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства для службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-113">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="d51e5-114">![Задайте свойство ServiceName. ] (../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span><span class="sxs-lookup"><span data-stu-id="d51e5-114">![Set the ServiceName property.](../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d51e5-115">Значение <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства всегда должно соответствовать имени, указанному в классах установщика.</span><span class="sxs-lookup"><span data-stu-id="d51e5-115">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="d51e5-116">При изменении этого свойства необходимо также обновить свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> классов установщика.</span><span class="sxs-lookup"><span data-stu-id="d51e5-116">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3.  <span data-ttu-id="d51e5-117">Установите любые из следующих свойств для определения режима работы службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-117">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="d51e5-118">Свойство</span><span class="sxs-lookup"><span data-stu-id="d51e5-118">Property</span></span>|<span data-ttu-id="d51e5-119">Параметр</span><span class="sxs-lookup"><span data-stu-id="d51e5-119">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="d51e5-120">`True`, чтобы указать, что служба может принимать запросы на останов работы; `false` для предотвращения останова службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-120">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="d51e5-121">`True`, чтобы указать, что служба хочет принимать уведомления о выключении компьютера, на котором она работает, позволяя ему вызывать процедуру <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.</span><span class="sxs-lookup"><span data-stu-id="d51e5-121">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="d51e5-122">`True`, чтобы указать, что служба может принимать запросы на приостановку или возобновление выполнения; `false` для предотвращения приостановки и возобновления работы службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-122">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="d51e5-123">`True` Чтобы указать, что служба может обрабатывать уведомления об изменениях состояния питания компьютера; `false` для предотвращения службе оповещен этих изменений.</span><span class="sxs-lookup"><span data-stu-id="d51e5-123">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="d51e5-124">`True` для внесения информационных записей в журнал событий приложения, когда служба выполняет некоторое действие; `false` для отключения этой функции.</span><span class="sxs-lookup"><span data-stu-id="d51e5-124">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="d51e5-125">Дополнительные сведения см. в разделе [как: сведения о журналам](../../../docs/framework/windows-services/how-to-log-information-about-services.md).</span><span class="sxs-lookup"><span data-stu-id="d51e5-125">For more information, see [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md).</span></span> <span data-ttu-id="d51e5-126">**Примечание:** по умолчанию <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> равно `true`.</span><span class="sxs-lookup"><span data-stu-id="d51e5-126">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d51e5-127">Когда <xref:System.ServiceProcess.ServiceBase.CanStop%2A> или <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> присваиваются `false`, **диспетчера управления службами** отключит с соответствующими параметрами меню можно остановить, приостановить или продолжить работу службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-127">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4.  <span data-ttu-id="d51e5-128">Откройте редактор кода и введите данные для выполнения операций для процедур <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.</span><span class="sxs-lookup"><span data-stu-id="d51e5-128">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5.  <span data-ttu-id="d51e5-129">Переопределите все прочие методы, для которых необходимо определить функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="d51e5-129">Override any other methods for which you want to define functionality.</span></span>  
  
6.  <span data-ttu-id="d51e5-130">Добавить установщики, необходимые для приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-130">Add the necessary installers for your service application.</span></span> <span data-ttu-id="d51e5-131">Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="d51e5-131">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
7.  <span data-ttu-id="d51e5-132">Постройте проект, выбрав **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="d51e5-132">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d51e5-133">Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.</span><span class="sxs-lookup"><span data-stu-id="d51e5-133">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8.  <span data-ttu-id="d51e5-134">Установите службу.</span><span class="sxs-lookup"><span data-stu-id="d51e5-134">Install the service.</span></span> <span data-ttu-id="d51e5-135">Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="d51e5-135">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51e5-136">См. также</span><span class="sxs-lookup"><span data-stu-id="d51e5-136">See Also</span></span>  
 [<span data-ttu-id="d51e5-137">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="d51e5-137">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="d51e5-138">Практическое руководство. Создание службы программным способом</span><span class="sxs-lookup"><span data-stu-id="d51e5-138">How to: Write Services Programmatically</span></span>](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)  
 [<span data-ttu-id="d51e5-139">Практическое руководство. Добавление установщиков в приложение служб</span><span class="sxs-lookup"><span data-stu-id="d51e5-139">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="d51e5-140">Практическое руководство. Запись сведений о службах в журнал</span><span class="sxs-lookup"><span data-stu-id="d51e5-140">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="d51e5-141">Практическое руководство. Запуск служб</span><span class="sxs-lookup"><span data-stu-id="d51e5-141">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="d51e5-142">Практическое руководство. Назначение службам контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="d51e5-142">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)  
 [<span data-ttu-id="d51e5-143">Практическое руководство. Установка и удаление служб</span><span class="sxs-lookup"><span data-stu-id="d51e5-143">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="d51e5-144">Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов</span><span class="sxs-lookup"><span data-stu-id="d51e5-144">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
