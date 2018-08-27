---
title: Практическое руководство. Отладка приложений служб Windows
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
manager: douge
ms.openlocfilehash: 5de4c90361033df603bb63fbb365514d6bb5ea0c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935691"
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="35fcb-102">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="35fcb-102">How to: Debug Windows Service Applications</span></span>
<span data-ttu-id="35fcb-103">Служба должна запускаться из диспетчера управления службами, а не из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="35fcb-103">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="35fcb-104">Поэтому, процесс отладки службы сложнее, чем отладка приложений Visual Studio других типов.</span><span class="sxs-lookup"><span data-stu-id="35fcb-104">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="35fcb-105">Для отладки службы необходимо запустить службу, а затем подключить отладчик к процессу, в котором она выполняется.</span><span class="sxs-lookup"><span data-stu-id="35fcb-105">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="35fcb-106">Приложение можно отлаживать с помощью всех стандартных средств отладки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="35fcb-106">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="35fcb-107">Не следует присоединять к процессу, если неизвестно, что собой представляет данный процесс, и неясны последствия подключения к процессу (включая даже уничтожение этого процесса).</span><span class="sxs-lookup"><span data-stu-id="35fcb-107">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="35fcb-108">Например, при подключении к процессу WinLogon и последующей остановке процесса отладки система будет остановлена, так как она не может работать без данного процесса.</span><span class="sxs-lookup"><span data-stu-id="35fcb-108">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="35fcb-109">Отладчик можно прикреплять только к выполняющейся службе.</span><span class="sxs-lookup"><span data-stu-id="35fcb-109">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="35fcb-110">Процесс подключения прерывает текущую работу службы (фактически он не останавливает и не приостанавливает ее).</span><span class="sxs-lookup"><span data-stu-id="35fcb-110">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="35fcb-111">То есть, если служба уже выполнялась на момент запуска процесса отладки, она по-прежнему технически находится в состоянии "Started" в ходе отладки, однако ее работа приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="35fcb-111">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="35fcb-112">После присоединения к процессу можно установить точки останова и использовать их для отладки кода.</span><span class="sxs-lookup"><span data-stu-id="35fcb-112">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="35fcb-113">После выхода из диалогового окна, используемого для подключения к процессу, вы продолжаете оставаться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="35fcb-113">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="35fcb-114">Для запуска, остановки, приостановки и продолжения работы служб (то есть, попадания в заданные точки) можно использовать диспетчер управления службами.</span><span class="sxs-lookup"><span data-stu-id="35fcb-114">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="35fcb-115">Позднее эту фиктивную службу можно удалить после успешного завершения отладки.</span><span class="sxs-lookup"><span data-stu-id="35fcb-115">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="35fcb-116">В этой статье рассматривается процесс отладки службы, выполняемой на локальном компьютере (также можно выполнять отладку служб Windows, которые выполняются на удаленном компьютере).</span><span class="sxs-lookup"><span data-stu-id="35fcb-116">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="35fcb-117">См. статью об [удаленной отладке](/visualstudio/debugger/debug-installed-app-package).</span><span class="sxs-lookup"><span data-stu-id="35fcb-117">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35fcb-118">Процесс отладки метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> может быть сложным, так как диспетчер управления службами накладывает ограничение в 30 секунд на все попытки запуска службы.</span><span class="sxs-lookup"><span data-stu-id="35fcb-118">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="35fcb-119">Дополнительные сведения см. в статье [Устранение неполадок: отладка служб Windows](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fcb-119">For more information, see [Troubleshooting: Debugging Windows Services](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="35fcb-120">Для получения значимой информации для отладки отладчик Visual Studio должен найти файлы символов для двоичных файлов, для которых выполняется отладка.</span><span class="sxs-lookup"><span data-stu-id="35fcb-120">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="35fcb-121">При отладке службы, созданной в Visual Studio, файлы символов (PDB-файлы) находятся в той же папке, что и исполняемый файл или библиотека, и отладчик загружает их автоматически.</span><span class="sxs-lookup"><span data-stu-id="35fcb-121">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="35fcb-122">При отладке службы, которая не была построена, сначала следует найти символы для службы и убедиться, что они могут быть найдены отладчиком.</span><span class="sxs-lookup"><span data-stu-id="35fcb-122">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="35fcb-123">См. статью [Указание файлов символов (.pdb) и файлов с исходным кодом в отладчике Visual Studio](http://msdn.microsoft.com/library/1105e169-5272-4e7c-b3e7-cda1b7798a6b).</span><span class="sxs-lookup"><span data-stu-id="35fcb-123">See [Specify Symbol (.pdb) and Source Files](http://msdn.microsoft.com/library/1105e169-5272-4e7c-b3e7-cda1b7798a6b).</span></span> <span data-ttu-id="35fcb-124">Если вы выполняете отладку системного процесса или хотите иметь символы для системных вызовов в своих службах, то необходимо добавить серверы символов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35fcb-124">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="35fcb-125">См. статью [об отладке с помощью символов](/windows/desktop/DxTechArts/debugging-with-symbols).</span><span class="sxs-lookup"><span data-stu-id="35fcb-125">See [Debugging Symbols](/windows/desktop/DxTechArts/debugging-with-symbols).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="35fcb-126">Отладка службы</span><span class="sxs-lookup"><span data-stu-id="35fcb-126">To debug a service</span></span>  
  
1.  <span data-ttu-id="35fcb-127">Постройте службу в конфигурации отладки.</span><span class="sxs-lookup"><span data-stu-id="35fcb-127">Build your service in the Debug configuration.</span></span>  
  
2.  <span data-ttu-id="35fcb-128">Установите службу.</span><span class="sxs-lookup"><span data-stu-id="35fcb-128">Install your service.</span></span> <span data-ttu-id="35fcb-129">Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fcb-129">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
3.  <span data-ttu-id="35fcb-130">Запустите службу из **диспетчера служб**, **обозревателя сервера** или из кода.</span><span class="sxs-lookup"><span data-stu-id="35fcb-130">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="35fcb-131">Дополнительные сведения см. в [практическом руководстве по запуску служб](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fcb-131">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>  
  
4.  <span data-ttu-id="35fcb-132">Запустите Visual Studio с учетными данными администратора, чтобы вы могли подключиться к системным процессам.</span><span class="sxs-lookup"><span data-stu-id="35fcb-132">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5.  <span data-ttu-id="35fcb-133">(Необязательное действие.) В строке меню Visual Studio последовательно выберите **Инструменты** и **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-133">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="35fcb-134">В диалоговом окне **Параметры** последовательно выберите **Отладка** и **Символы**, установите флажок **Серверы символов Microsoft** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-134">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="35fcb-135">В строке меню в меню **Отладка** или **Инструменты** выберите пункт **Присоединение к процессу**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-135">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="35fcb-136">(Комбинация клавиш: Ctrl+Alt+P)</span><span class="sxs-lookup"><span data-stu-id="35fcb-136">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="35fcb-137">Откроется диалоговое окно **Процессы**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-137">The **Processes** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="35fcb-138">Установите флажок **Показать процессы, запущенные всеми пользователями**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-138">Select the **Show processes from all users** check box.</span></span>  
  
8.  <span data-ttu-id="35fcb-139">В разделе **Доступные процессы** выберите процесс для службы и нажмите кнопку **Присоединиться**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-139">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="35fcb-140">Процесс будет иметь то же имя, что и исполняемый файл для службы.</span><span class="sxs-lookup"><span data-stu-id="35fcb-140">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="35fcb-141">Откроется диалоговое окно **Присоединение к процессу** .</span><span class="sxs-lookup"><span data-stu-id="35fcb-141">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="35fcb-142">Выберите соответствующие параметры, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="35fcb-142">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35fcb-143">Теперь вы находитесь в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="35fcb-143">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="35fcb-144">Установите точки останова, которые буден нужно использовать в коде.</span><span class="sxs-lookup"><span data-stu-id="35fcb-144">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="35fcb-145">Откройте диспетчер управления службами и выполните несколько операций со своей службой (выполните команды остановки, приостановки и продолжения), чтобы обнаружить свои точки останова.</span><span class="sxs-lookup"><span data-stu-id="35fcb-145">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="35fcb-146">Дополнительные сведения о запуске диспетчера служб см. в статье [Практическое руководство. Запуск служб](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fcb-146">For more information about running the Services Control Manager, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span> <span data-ttu-id="35fcb-147">Также см. статью [Устранение неполадок: отладка служб Windows](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fcb-147">Also, see [Troubleshooting: Debugging Windows Services](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="35fcb-148">Советы по отладке для служб Windows</span><span class="sxs-lookup"><span data-stu-id="35fcb-148">Debugging Tips for Windows Services</span></span>  
 <span data-ttu-id="35fcb-149">Присоединение к процессу службы позволяет отлаживать основную часть кода (но не весь код) для этой службы.</span><span class="sxs-lookup"><span data-stu-id="35fcb-149">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="35fcb-150">Например, так как служба уже была запущена, нельзя выполнять отладку кода в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> службы или кода в методе `Main`, который используется для загрузки службы подобным образом.</span><span class="sxs-lookup"><span data-stu-id="35fcb-150">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="35fcb-151">Одним из способов обхода этого ограничения является создание временной второй службы в приложении службы, которая предназначена только для отладки.</span><span class="sxs-lookup"><span data-stu-id="35fcb-151">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="35fcb-152">Можно установить обе службы,а затем запустить эту фиктивную службу для загрузки процесса службы.</span><span class="sxs-lookup"><span data-stu-id="35fcb-152">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="35fcb-153">Когда временная служба запустит процесс, в Visual Studio в меню **Отладка** можно будет присоединиться к процессу службы.</span><span class="sxs-lookup"><span data-stu-id="35fcb-153">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="35fcb-154">Попробуйте добавлять вызовы в метод <xref:System.Threading.Thread.Sleep%2A> с целью задержки выполнения действия, пока вы не присоединитесь к процессу.</span><span class="sxs-lookup"><span data-stu-id="35fcb-154">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="35fcb-155">Попробуйте заменить программу на обычное консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="35fcb-155">Try changing the program to a regular console application.</span></span> <span data-ttu-id="35fcb-156">Для этого измените метод `Main` следующим образом, чтобы он мог быть запущен и как служба Windows, и как консольное приложение (в зависимости от способа запуска).</span><span class="sxs-lookup"><span data-stu-id="35fcb-156">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="35fcb-157">Запуск службы Windows как консольного приложения</span><span class="sxs-lookup"><span data-stu-id="35fcb-157">How to: Run a Windows Service as a console application</span></span>  
  
1.  <span data-ttu-id="35fcb-158">Добавьте метод в свою службу, которая запускает методы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>:</span><span class="sxs-lookup"><span data-stu-id="35fcb-158">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2.  <span data-ttu-id="35fcb-159">Перепишите метод `Main` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="35fcb-159">Rewrite the `Main` method as follows:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3.  <span data-ttu-id="35fcb-160">В окне свойств проекта на вкладке **Приложение** задайте для параметра **Тип выходных данных** значение **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-160">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4.  <span data-ttu-id="35fcb-161">Щелкните **Начать отладку** (F5).</span><span class="sxs-lookup"><span data-stu-id="35fcb-161">Choose **Start Debugging** (F5).</span></span>  
  
5.  <span data-ttu-id="35fcb-162">Чтобы снова запустить программу как службу Windows, установите ее и запустите обычным образом (для службы Windows).</span><span class="sxs-lookup"><span data-stu-id="35fcb-162">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="35fcb-163">Отменять эти изменения необязательно.</span><span class="sxs-lookup"><span data-stu-id="35fcb-163">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="35fcb-164">В некоторых случаях, например, если требуется устранить некоторую проблему, которая возникает только при запуске системы, необходимо использовать отладчик Windows.</span><span class="sxs-lookup"><span data-stu-id="35fcb-164">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="35fcb-165">Установите [средства отладки для Windows](http://msdn.microsoft.com/windows/hardware/hh852365) и прочтите статью [Отладка служб Windows](http://support.microsoft.com/kb/824344).</span><span class="sxs-lookup"><span data-stu-id="35fcb-165">Install [Debugging Tools for Windows](http://msdn.microsoft.com/windows/hardware/hh852365) and see [How to debug Windows Services](http://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35fcb-166">См. также</span><span class="sxs-lookup"><span data-stu-id="35fcb-166">See Also</span></span>  
 [<span data-ttu-id="35fcb-167">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="35fcb-167">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="35fcb-168">Практическое руководство. Установка и удаление служб</span><span class="sxs-lookup"><span data-stu-id="35fcb-168">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="35fcb-169">Практическое руководство. Запуск служб</span><span class="sxs-lookup"><span data-stu-id="35fcb-169">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="35fcb-170">Отладка службы</span><span class="sxs-lookup"><span data-stu-id="35fcb-170">Debugging a Service</span></span>](/windows/desktop/Services/debugging-a-service)
