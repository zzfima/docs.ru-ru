---
title: Практическое руководство. Запуск служб
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: b3f04deb11a23957198864c444b4872aef45b2e4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176751"
---
# <a name="how-to-start-services"></a><span data-ttu-id="02240-102">Практическое руководство. Запуск служб</span><span class="sxs-lookup"><span data-stu-id="02240-102">How to: Start Services</span></span>
<span data-ttu-id="02240-103">Установленную службу необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="02240-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="02240-104">Процедура запуска вызывает метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> в классе службы.</span><span class="sxs-lookup"><span data-stu-id="02240-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="02240-105">Как правило, метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> определяет полезные действия, которые будет выполнять служба.</span><span class="sxs-lookup"><span data-stu-id="02240-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="02240-106">Запущенная служба остается активной, пока не будет приостановлена или остановлена вручную.</span><span class="sxs-lookup"><span data-stu-id="02240-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="02240-107">Службы можно настроить на запуск автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="02240-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="02240-108">Служба, которая запускается автоматически, будет запущена при первом включении или перезагрузке компьютера, на котором она установлена.</span><span class="sxs-lookup"><span data-stu-id="02240-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="02240-109">Службу, которая запускается вручную, должен запустить пользователь.</span><span class="sxs-lookup"><span data-stu-id="02240-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02240-110">По умолчанию службы, созданные с помощью Visual Studio, настроены на запуск вручную.</span><span class="sxs-lookup"><span data-stu-id="02240-110">By default, services created with Visual Studio are set to start manually.</span></span>  
  
 <span data-ttu-id="02240-111">Есть несколько способов запуска службы вручную: из **диспетчера служб** или **обозревателя сервера** либо из кода, используя компонент, который называется <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="02240-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="02240-112">Вы можете задать свойство <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> в классе <xref:System.ServiceProcess.ServiceInstaller>, чтобы определить способ запуска службы — вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="02240-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="02240-113">Настройка способа запуска службы</span><span class="sxs-lookup"><span data-stu-id="02240-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="02240-114">Создав службу, добавьте для нее необходимые установщики.</span><span class="sxs-lookup"><span data-stu-id="02240-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="02240-115">Дополнительные сведения см. в [руководстве по добавлению установщиков в приложение-службу](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="02240-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="02240-116">В конструкторе щелкните установщик процессов службы, с которой вы работаете.</span><span class="sxs-lookup"><span data-stu-id="02240-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="02240-117">В **окне свойств** задайте свойству <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="02240-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="02240-118">Чтобы установить службу</span><span class="sxs-lookup"><span data-stu-id="02240-118">To have your service install</span></span>|<span data-ttu-id="02240-119">Задайте это значение</span><span class="sxs-lookup"><span data-stu-id="02240-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="02240-120">При перезапуске компьютера</span><span class="sxs-lookup"><span data-stu-id="02240-120">When the computer is restarted</span></span>|<span data-ttu-id="02240-121">**Автоматический**</span><span class="sxs-lookup"><span data-stu-id="02240-121">**Automatic**</span></span>|  
    |<span data-ttu-id="02240-122">При запуске службы с помощью явного действия пользователя</span><span class="sxs-lookup"><span data-stu-id="02240-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="02240-123">**Manual** (Вручную)</span><span class="sxs-lookup"><span data-stu-id="02240-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="02240-124">Чтобы полностью запретить запуск службы, можно задать свойству <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение **Disabled** (Отключено).</span><span class="sxs-lookup"><span data-stu-id="02240-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="02240-125">Это можно сделать, если вы собираетесь перезагружать сервер несколько раз и хотите сэкономить время, запретив запуск служб, которые обычно запускаются одновременно.</span><span class="sxs-lookup"><span data-stu-id="02240-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02240-126">Эти и другие свойства можно изменить после установки службы.</span><span class="sxs-lookup"><span data-stu-id="02240-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="02240-127">Есть несколько способов запуска службы, для процесса <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> которой настроено значение **Manual** (Вручную): из **диспетчера служб** или **обозревателя серверов** либо из кода.</span><span class="sxs-lookup"><span data-stu-id="02240-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="02240-128">Важно отметить, что в действительности не все эти методы приводят к запуску службы в контексте **диспетчера служб**. При использовании **обозревателя сервера** и программных способов применяется контроллер.</span><span class="sxs-lookup"><span data-stu-id="02240-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="02240-129">Запуск службы вручную из обозревателя сервера</span><span class="sxs-lookup"><span data-stu-id="02240-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="02240-130">В **обозревателе сервера** добавьте нужный сервер, если его нет в списке.</span><span class="sxs-lookup"><span data-stu-id="02240-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="02240-131">Дополнительные сведения см. в руководстве по получению доступа и инициализации обозревателя сервера и обозревателя базы данных.</span><span class="sxs-lookup"><span data-stu-id="02240-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="02240-132">Разверните узел **Службы** и выберите службу, которую нужно запустить.</span><span class="sxs-lookup"><span data-stu-id="02240-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="02240-133">Щелкните службу правой кнопкой мыши и выберите команду **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="02240-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="02240-134">Запуск службы вручную из диспетчера служб</span><span class="sxs-lookup"><span data-stu-id="02240-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="02240-135">Откройте **диспетчер служб**, сделав следующее:</span><span class="sxs-lookup"><span data-stu-id="02240-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="02240-136">В Windows XP и 2000 Professional щелкните правой кнопкой мыши значок **Мой компьютер** на рабочем столе и выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="02240-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="02240-137">В открывшемся диалоговом окне разверните узел **Службы и приложения**.</span><span class="sxs-lookup"><span data-stu-id="02240-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="02240-138">\- или -</span><span class="sxs-lookup"><span data-stu-id="02240-138">\- or -</span></span>  
  
    -   <span data-ttu-id="02240-139">В Windows Server 2003 и Windows 2000 Server нажмите кнопку **Пуск**, выберите **Программы**, **Администрирование** и **Службы**.</span><span class="sxs-lookup"><span data-stu-id="02240-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="02240-140">В Windows NT версии 4.0 можно открыть это диалоговое окно на **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="02240-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="02240-141">Теперь ваша служба должна отобразиться в списке **Службы**.</span><span class="sxs-lookup"><span data-stu-id="02240-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="02240-142">Выберите службу в списке, щелкните ее правой кнопкой мыши и нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="02240-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="02240-143">Запуск службы вручную из кода</span><span class="sxs-lookup"><span data-stu-id="02240-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="02240-144">Создайте экземпляр класса <xref:System.ServiceProcess.ServiceController> и настройте его для взаимодействия со службой, которой нужно управлять.</span><span class="sxs-lookup"><span data-stu-id="02240-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="02240-145">Чтобы запустить службу, вызовите метод <xref:System.ServiceProcess.ServiceController.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="02240-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02240-146">См. также</span><span class="sxs-lookup"><span data-stu-id="02240-146">See Also</span></span>  
 [<span data-ttu-id="02240-147">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="02240-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="02240-148">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="02240-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="02240-149">Практическое руководство. Добавление установщиков в приложение служб</span><span class="sxs-lookup"><span data-stu-id="02240-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
