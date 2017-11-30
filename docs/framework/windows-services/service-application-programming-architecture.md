---
title: "Программная архитектура приложений служб"
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
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e9c16f2e603a3ce9bbc59be4e01aa492239d2c63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="b1c81-102">Программная архитектура приложений служб</span><span class="sxs-lookup"><span data-stu-id="b1c81-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="b1c81-103">Приложения служб Windows основаны на класс, наследующий от <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="b1c81-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b1c81-104">Переопределите методы этого класса и определить функциональные возможности для их определить поведение службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="b1c81-105">Ниже перечислены основные классы, используемые при создании службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="b1c81-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>— Необходимо переопределить методы <xref:System.ServiceProcess.ServiceBase> класса при создании службы и определить код, чтобы определить, как функциональные возможности службы в этом наследуется класс.</span><span class="sxs-lookup"><span data-stu-id="b1c81-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="b1c81-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>и <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> — эти классы используются для установки и удаления службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="b1c81-108">Кроме того, класс с именем <xref:System.ServiceProcess.ServiceController> можно использовать для управления службой.</span><span class="sxs-lookup"><span data-stu-id="b1c81-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="b1c81-109">Этот класс не используется при создании службы, но может использоваться для запуска и остановки службы, передавать ей команды и возвращать последовательности перечислений.</span><span class="sxs-lookup"><span data-stu-id="b1c81-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="b1c81-110">Определение поведения службы</span><span class="sxs-lookup"><span data-stu-id="b1c81-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="b1c81-111">В классе службы переопределить функции базового класса, которые определяют, что происходит при изменении состояния службы в диспетчере управления службами.</span><span class="sxs-lookup"><span data-stu-id="b1c81-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="b1c81-112"><xref:System.ServiceProcess.ServiceBase> Класс предоставляет следующие методы, которые можно переопределить, чтобы добавить пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="b1c81-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="b1c81-113">Метод</span><span class="sxs-lookup"><span data-stu-id="b1c81-113">Method</span></span>|<span data-ttu-id="b1c81-114">Переопределение позволяет</span><span class="sxs-lookup"><span data-stu-id="b1c81-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="b1c81-115">Укажите, какие действия должны быть выполнены, при запуске службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="b1c81-116">В этой процедуре для службы для выполнения требуемых задач, необходимо написать код.</span><span class="sxs-lookup"><span data-stu-id="b1c81-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="b1c81-117">Указывает, что должно происходить при приостановке службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="b1c81-118">Указывает, что должно происходить при остановке службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="b1c81-119">Указывает, что должно происходить при возобновлении работы после ее приостановки вашей службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="b1c81-120">Указывает, что должно происходить непосредственно перед завершением работы, системы, если служба запущена в это время.</span><span class="sxs-lookup"><span data-stu-id="b1c81-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="b1c81-121">Указывает, что должно происходить, когда служба получает пользовательской команды.</span><span class="sxs-lookup"><span data-stu-id="b1c81-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="b1c81-122">Дополнительные сведения о пользовательских командах см. в разделе MSDN online.</span><span class="sxs-lookup"><span data-stu-id="b1c81-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="b1c81-123">Укажите реакцию службы при получении события управления питанием, например низкого заряда батарей или режима приостановки.</span><span class="sxs-lookup"><span data-stu-id="b1c81-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b1c81-124">Эти методы соответствуют состояниям, которые служба перемещается по времени существования; Служба переходит из одного состояния к другому.</span><span class="sxs-lookup"><span data-stu-id="b1c81-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="b1c81-125">Например, вы никогда не получите службе отвечать на <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> перед тем как <xref:System.ServiceProcess.ServiceBase.OnStart%2A> был вызван.</span><span class="sxs-lookup"><span data-stu-id="b1c81-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="b1c81-126">Существует несколько других свойств и методов, которые представляют интерес.</span><span class="sxs-lookup"><span data-stu-id="b1c81-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="b1c81-127">К ним относятся следующие методы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-127">These include:</span></span>  
  
-   <span data-ttu-id="b1c81-128"><xref:System.ServiceProcess.ServiceBase.Run%2A> Метод <xref:System.ServiceProcess.ServiceBase> класса.</span><span class="sxs-lookup"><span data-stu-id="b1c81-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="b1c81-129">Это главная точка входа для службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-129">This is the main entry point for the service.</span></span> <span data-ttu-id="b1c81-130">При создании службы с помощью шаблона служб Windows, код вставляется в вашем приложении `Main` метод для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="b1c81-131">Этот код выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b1c81-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="b1c81-132">В этих примерах используются массивом типа <xref:System.ServiceProcess.ServiceBase>, в который каждой службы, который содержит приложение можно добавить и затем все службы могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="b1c81-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="b1c81-133">Если создается только одна служба, тем не менее, можно не использовать массив, а объявить новый объект, наследуемый от <xref:System.ServiceProcess.ServiceBase> и запустите его.</span><span class="sxs-lookup"><span data-stu-id="b1c81-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="b1c81-134">Пример см. в разделе [как: запись службы программным образом](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="b1c81-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="b1c81-135">Наборы свойств <xref:System.ServiceProcess.ServiceBase> класса.</span><span class="sxs-lookup"><span data-stu-id="b1c81-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="b1c81-136">Они определяют, какие методы могут вызываться в службе.</span><span class="sxs-lookup"><span data-stu-id="b1c81-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="b1c81-137">Например, если <xref:System.ServiceProcess.ServiceBase.CanStop%2A> свойству `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> возможность вызова метода в службе.</span><span class="sxs-lookup"><span data-stu-id="b1c81-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="b1c81-138">Когда <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> свойству `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> и <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> можно вызывать методы.</span><span class="sxs-lookup"><span data-stu-id="b1c81-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="b1c81-139">Если задано одно из этих свойств для `true`, необходимо переопределить и реализовать соответствующий метод.</span><span class="sxs-lookup"><span data-stu-id="b1c81-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1c81-140">Служба должна переопределять по крайней мере <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> для использования.</span><span class="sxs-lookup"><span data-stu-id="b1c81-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="b1c81-141">Можно также использовать компонент, называемый <xref:System.ServiceProcess.ServiceController> для связи и управлять поведением существующую службу.</span><span class="sxs-lookup"><span data-stu-id="b1c81-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c81-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b1c81-142">See Also</span></span>  
 [<span data-ttu-id="b1c81-143">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="b1c81-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="b1c81-144">Как: создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="b1c81-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
