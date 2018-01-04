---
title: "Практическое руководство. Запуск служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 8352edaa9386adc1fbf3057c6e98f5a9cf9ce4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-start-services"></a><span data-ttu-id="9387a-102">Практическое руководство. Запуск служб</span><span class="sxs-lookup"><span data-stu-id="9387a-102">How to: Start Services</span></span>
<span data-ttu-id="9387a-103">После установки службы ее необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="9387a-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="9387a-104">Запуск вызовы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метод в классе службы.</span><span class="sxs-lookup"><span data-stu-id="9387a-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="9387a-105">Как правило <xref:System.ServiceProcess.ServiceBase.OnStart%2A> полезные действия, служба выполнит определяет метод.</span><span class="sxs-lookup"><span data-stu-id="9387a-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="9387a-106">После запуска служба остается активной до вручную приостановлена или остановлена.</span><span class="sxs-lookup"><span data-stu-id="9387a-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="9387a-107">Службы можно настроить на автоматический или ручной запуск.</span><span class="sxs-lookup"><span data-stu-id="9387a-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="9387a-108">Будет запущена служба, которая запускается автоматически при включении или перезагрузке компьютера, на котором он установлен.</span><span class="sxs-lookup"><span data-stu-id="9387a-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="9387a-109">Пользователь должен запустить службу, которая запускается вручную.</span><span class="sxs-lookup"><span data-stu-id="9387a-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9387a-110">По умолчанию службы созданные с помощью [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] настроены на запуск вручную.</span><span class="sxs-lookup"><span data-stu-id="9387a-110">By default, services created with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] are set to start manually.</span></span>  
  
 <span data-ttu-id="9387a-111">Существует несколько способов запустить службу вручную — из **обозревателя серверов**, из **диспетчера управления службами**, или из кода с помощью компонента вызывается <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="9387a-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="9387a-112">Задать <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> свойство <xref:System.ServiceProcess.ServiceInstaller> класс, чтобы определить, является ли служба должна быть запущена вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="9387a-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="9387a-113">Чтобы настроить способ запуска службы</span><span class="sxs-lookup"><span data-stu-id="9387a-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="9387a-114">После создания службы, добавьте установщики, необходимые для него.</span><span class="sxs-lookup"><span data-stu-id="9387a-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="9387a-115">Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="9387a-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="9387a-116">В конструкторе щелкните установщик службы для службы, с которой вы работаете.</span><span class="sxs-lookup"><span data-stu-id="9387a-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="9387a-117">В **свойства** задайте <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> в одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9387a-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="9387a-118">Для запуска службы</span><span class="sxs-lookup"><span data-stu-id="9387a-118">To have your service install</span></span>|<span data-ttu-id="9387a-119">Это значение</span><span class="sxs-lookup"><span data-stu-id="9387a-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="9387a-120">При перезапуске компьютера</span><span class="sxs-lookup"><span data-stu-id="9387a-120">When the computer is restarted</span></span>|<span data-ttu-id="9387a-121">**Автоматический**</span><span class="sxs-lookup"><span data-stu-id="9387a-121">**Automatic**</span></span>|  
    |<span data-ttu-id="9387a-122">При запуске службы в явному действию пользователя</span><span class="sxs-lookup"><span data-stu-id="9387a-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="9387a-123">**Вручную**</span><span class="sxs-lookup"><span data-stu-id="9387a-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="9387a-124">Чтобы запретить запуск службы, можно задать <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> свойства **отключено**.</span><span class="sxs-lookup"><span data-stu-id="9387a-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="9387a-125">Это можно сделать при будет перезагрузить сервер несколько раз и можно уменьшить время, так как службы, которые бы обычно запуск.</span><span class="sxs-lookup"><span data-stu-id="9387a-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9387a-126">Эти и другие свойства можно изменить после установки службы.</span><span class="sxs-lookup"><span data-stu-id="9387a-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="9387a-127">Существует несколько способов, которые можно запустить службу с его <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> присвоено процесс **вручную** — из **обозревателя серверов**, из **диспетчер управления службами Windows**, или из кода.</span><span class="sxs-lookup"><span data-stu-id="9387a-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="9387a-128">Важно отметить, что в действительности не все эти методы приводят к запуску службы в контексте **диспетчера управления службами**; **Обозревателя серверов** и программном методе для запуска службы используется компонент-контроллер.</span><span class="sxs-lookup"><span data-stu-id="9387a-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="9387a-129">Чтобы запустить службу вручную из обозревателя серверов</span><span class="sxs-lookup"><span data-stu-id="9387a-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="9387a-130">В **обозревателя серверов**, добавьте сервер, требуется, если его нет в списке.</span><span class="sxs-lookup"><span data-stu-id="9387a-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="9387a-131">Дополнительные сведения см. в разделе как: подключение и инициализация обозревателя базы данных обозревателя сервера.</span><span class="sxs-lookup"><span data-stu-id="9387a-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="9387a-132">Разверните **служб** узел и выберите службу, которую требуется запустить.</span><span class="sxs-lookup"><span data-stu-id="9387a-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="9387a-133">Щелкните правой кнопкой мыши имя службы и нажмите кнопку **запустить**.</span><span class="sxs-lookup"><span data-stu-id="9387a-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="9387a-134">Чтобы запустить службу вручную из диспетчера управления службами</span><span class="sxs-lookup"><span data-stu-id="9387a-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="9387a-135">Откройте **диспетчера управления службами** , выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9387a-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="9387a-136">В 2000 Professional и Windows XP, щелкните правой кнопкой мыши **Мой компьютер** на рабочем столе и нажмите кнопку **управление**.</span><span class="sxs-lookup"><span data-stu-id="9387a-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="9387a-137">В появившемся диалоговом окне, разверните **службы и приложения** узла.</span><span class="sxs-lookup"><span data-stu-id="9387a-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="9387a-138">\- или -</span><span class="sxs-lookup"><span data-stu-id="9387a-138">\- or -</span></span>  
  
    -   <span data-ttu-id="9387a-139">В Windows Server 2003 и Windows 2000 Server, нажмите кнопку **запустить**, пункты **программы**, нажмите кнопку **Администрирование**и нажмите кнопку **служб**.</span><span class="sxs-lookup"><span data-stu-id="9387a-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9387a-140">В Windows NT версии 4.0, можно открыть это диалоговое окно из **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="9387a-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="9387a-141">Теперь вы увидите список **служб** окна.</span><span class="sxs-lookup"><span data-stu-id="9387a-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="9387a-142">Выберите службу в списке, щелкните его правой кнопкой мыши и выберите команду **запустить**.</span><span class="sxs-lookup"><span data-stu-id="9387a-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="9387a-143">Чтобы вручную запустить службу из кода</span><span class="sxs-lookup"><span data-stu-id="9387a-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="9387a-144">Создайте экземпляр класса <xref:System.ServiceProcess.ServiceController> класса и настройте его для взаимодействия со службой, которым требуется управлять.</span><span class="sxs-lookup"><span data-stu-id="9387a-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="9387a-145">Чтобы запустить службу, вызовите метод <xref:System.ServiceProcess.ServiceController.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="9387a-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9387a-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9387a-146">See Also</span></span>  
 [<span data-ttu-id="9387a-147">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="9387a-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="9387a-148">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="9387a-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="9387a-149">Практическое руководство. Добавление установщиков в приложение служб</span><span class="sxs-lookup"><span data-stu-id="9387a-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
