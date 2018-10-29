---
title: Создание приложения службы Windows в Visual Studio
ms.date: 09/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: 79447ede354de104607117f657182023a2e57127
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123674"
---
# <a name="walkthrough-create-a-windows-service-app"></a><span data-ttu-id="316bb-102">Пошаговое руководство. Создание приложения службы Windows</span><span class="sxs-lookup"><span data-stu-id="316bb-102">Walkthrough: Create a Windows service app</span></span>

<span data-ttu-id="316bb-103">Из этой статьи вы узнаете, как создать в Visual Studio простое приложение службы Windows, которое записывает сообщения в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="316bb-103">This article demonstrates how to create a simple Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="316bb-104">Создание службы</span><span class="sxs-lookup"><span data-stu-id="316bb-104">Create a service</span></span>

<span data-ttu-id="316bb-105">Для начала создайте проект и настройте значения, необходимые для правильной работы службы.</span><span class="sxs-lookup"><span data-stu-id="316bb-105">To begin, create the project and set values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="316bb-106">В Visual Studio в строке меню последовательно выберите **Файл** > **Создать** > **Проект** (или нажмите сочетание клавиш **CTRL**+**SHIFT**+**N**), чтобы открыть диалоговое окно **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="316bb-106">In Visual Studio, on the menu bar, choose **File** > **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** dialog.</span></span>

2. <span data-ttu-id="316bb-107">Найдите и выберите шаблон проекта **Служба Windows**.</span><span class="sxs-lookup"><span data-stu-id="316bb-107">Navigate to and select the **Windows Service** project template.</span></span> <span data-ttu-id="316bb-108">Разверните элементы **Установленные** > [**Visual C#** или **Visual Basic**] > **Windows Desktop** или введите строку **Служба Windows** в поле поиска в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="316bb-108">Expand **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, or type **Windows Service** in the search box on the upper right.</span></span>

   ![Шаблон приложения Windows в диалоговом окне нового проекта Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="316bb-110">Если вы не видите здесь шаблон **Служба Windows**, попробуйте установить рабочую нагрузку **Разработка классических приложений .NET**.</span><span class="sxs-lookup"><span data-stu-id="316bb-110">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload.</span></span> <span data-ttu-id="316bb-111">В диалоговом окне **Новый проект** щелкните ссылку с текстом **Открыть Visual Studio Installer** в левом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="316bb-111">In the **New Project** dialog, click the link that says **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="316bb-112">В окне **Visual Studio Installer** выберите рабочую нагрузку **Разработка классических приложений .NET** и щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="316bb-112">In **Visual Studio Installer**, select the **.NET desktop development** workload and then choose **Modify**.</span></span>

3. <span data-ttu-id="316bb-113">Присвойте проекту имя **MyNewService** и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="316bb-113">Name the project **MyNewService**, and then choose **OK**.</span></span>

   <span data-ttu-id="316bb-114">Этот шаблон проекта содержит класс компонента с именем `Service1`, наследуемый от <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="316bb-114">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="316bb-115">В нем собран основной служебный код, в том числе код для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="316bb-115">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="316bb-116">Переименование службы</span><span class="sxs-lookup"><span data-stu-id="316bb-116">Rename the service</span></span>

<span data-ttu-id="316bb-117">Измените имя службы с **Service1** на **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="316bb-117">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="316bb-118">В представлении **Конструктор** для файла Service1.cs (или Service1.vb) щелкните ссылку **перехода к представлению кода**.</span><span class="sxs-lookup"><span data-stu-id="316bb-118">In the **Design** view for Service1.cs (or Service1.vb), click the link to **switch to code view**.</span></span> <span data-ttu-id="316bb-119">Щелкните **Service1** правой кнопкой мыши и выберите в контекстном меню действие **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="316bb-119">Right-click on **Service1** and select **Rename** from the context menu.</span></span> <span data-ttu-id="316bb-120">Введите **MyNewService** и нажмите клавишу **ВВОД** или щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="316bb-120">Enter **MyNewService** and then press **Enter** or click **Apply**.</span></span>

2. <span data-ttu-id="316bb-121">В окне **Свойства** для **Service1.cs [Проект]** или **Service1.vb [Проект]**, измените значение **ServiceName** на **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="316bb-121">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, change the **ServiceName** value to **MyNewService**.</span></span>

3. <span data-ttu-id="316bb-122">В **обозревателе решений** переименуйте **Service1.cs** в **MyNewService.cs** (или **Service1.vb** в **MyNewService.vb**).</span><span class="sxs-lookup"><span data-stu-id="316bb-122">In **Solution Explorer**, rename **Service1.cs** to **MyNewService.cs**, or rename **Service1.vb** to **MyNewService.vb**.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="316bb-123">Добавление компонентов в службу</span><span class="sxs-lookup"><span data-stu-id="316bb-123">Add features to the service</span></span>

<span data-ttu-id="316bb-124">В этом разделе к службе Windows будет добавлен настраиваемый журнал событий.</span><span class="sxs-lookup"><span data-stu-id="316bb-124">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="316bb-125">Журналы событий никак не связаны со службами Windows.</span><span class="sxs-lookup"><span data-stu-id="316bb-125">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="316bb-126">Компонент <xref:System.Diagnostics.EventLog> используется здесь в качестве примера типа компонента, который можно добавить в службу Windows.</span><span class="sxs-lookup"><span data-stu-id="316bb-126">The <xref:System.Diagnostics.EventLog> component is used here as an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="316bb-127">Добавление возможности работы с настраиваемым журналом событий</span><span class="sxs-lookup"><span data-stu-id="316bb-127">Add custom event log functionality</span></span>

1. <span data-ttu-id="316bb-128">В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="316bb-128">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="316bb-129">Из раздела **Компоненты** **панели элементов**перетащите в окно конструктора компонент <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="316bb-129">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>

3. <span data-ttu-id="316bb-130">В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="316bb-130">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>

4. <span data-ttu-id="316bb-131">Измените конструктор, чтобы определить настраиваемый журнал событий:</span><span class="sxs-lookup"><span data-stu-id="316bb-131">Edit the constructor to define a custom event log:</span></span>

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new System.Diagnostics.EventLog();
        if (!System.Diagnostics.EventLog.SourceExists("MySource"))
        {
            System.Diagnostics.EventLog.CreateEventSource(
                "MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="316bb-132">Определение действий при запуске службы</span><span class="sxs-lookup"><span data-stu-id="316bb-132">Define what occurs when the service starts</span></span>

<span data-ttu-id="316bb-133">В редакторе кода найдите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, который был автоматически переопределен при создании проекта.</span><span class="sxs-lookup"><span data-stu-id="316bb-133">In the code editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project.</span></span> <span data-ttu-id="316bb-134">Добавьте строку кода, с помощью которой запись сохраняется в журнале событий при запуске службы:</span><span class="sxs-lookup"><span data-stu-id="316bb-134">Add a line of code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

<span data-ttu-id="316bb-135">Приложение службы предполагает длительное время выполнения, поэтому оно обычно опрашивает или отслеживает что-либо в системе.</span><span class="sxs-lookup"><span data-stu-id="316bb-135">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="316bb-136">Отслеживание настраивается в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="316bb-136">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="316bb-137">Тем не менее, метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> не отвечает за фактическое отслеживание.</span><span class="sxs-lookup"><span data-stu-id="316bb-137">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="316bb-138">После начала работы службы метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> должен возвращать управление операционной системе.</span><span class="sxs-lookup"><span data-stu-id="316bb-138">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="316bb-139">Он не должен уходить в бесконечный цикл или блокироваться.</span><span class="sxs-lookup"><span data-stu-id="316bb-139">It must not loop forever or block.</span></span> <span data-ttu-id="316bb-140">Для простого механизма опроса можно использовать компонент <xref:System.Timers.Timer?displayProperty=nameWithType> следующим образом: в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> задайте параметры компонента, а затем установите для свойства <xref:System.Timers.Timer.Enabled%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="316bb-140">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="316bb-141">Таймер периодическую генерирует события в вашем коде, при возникновении которых служба сможет выполнять отслеживание.</span><span class="sxs-lookup"><span data-stu-id="316bb-141">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="316bb-142">Для этого можно использовать следующий код:</span><span class="sxs-lookup"><span data-stu-id="316bb-142">You can use the following code to do this:</span></span>

```csharp
// Set up a timer that triggers every minute.
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 60000; // 60 seconds
timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);
timer.Start();
```

```vb
' Set up a timer that triggers every minute.
Dim timer As System.Timers.Timer = New System.Timers.Timer()
timer.Interval = 60000 ' 60 seconds
AddHandler timer.Elapsed, AddressOf Me.OnTimer
timer.Start()
```

<span data-ttu-id="316bb-143">Добавьте в класс переменную-член.</span><span class="sxs-lookup"><span data-stu-id="316bb-143">Add a member variable to the class.</span></span> <span data-ttu-id="316bb-144">Она содержит идентификатор следующего события, которое сохраняется в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="316bb-144">It contains the identifier of the next event to write into the event log.</span></span>

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

<span data-ttu-id="316bb-145">Добавьте новый метод для обработки этого события таймера:</span><span class="sxs-lookup"><span data-stu-id="316bb-145">Add a new method to handle the timer event:</span></span>

```csharp
public void OnTimer(object sender, System.Timers.ElapsedEventArgs args)
{
    // TODO: Insert monitoring activities here.
    eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);
}
```

```vb
Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)
    ' TODO: Insert monitoring activities here.
    eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)
    eventId = eventId + 1
End Sub
```

<span data-ttu-id="316bb-146">Задачи можно выполнять с помощью фоновых рабочих потоков, а не выполнять всю работу в основном потоке.</span><span class="sxs-lookup"><span data-stu-id="316bb-146">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="316bb-147">Дополнительные сведения см. в разделе <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="316bb-147">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="316bb-148">Определение действий при остановке службы</span><span class="sxs-lookup"><span data-stu-id="316bb-148">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="316bb-149">Добавьте в метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A> строку кода, с помощью которой запись сохраняется в журнале событий при остановке службы:</span><span class="sxs-lookup"><span data-stu-id="316bb-149">Add a line of code to the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="316bb-150">Определение других действий для службы</span><span class="sxs-lookup"><span data-stu-id="316bb-150">Define other actions for the service</span></span>

<span data-ttu-id="316bb-151">Вы можете переопределить методы <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> и <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>, добавив дополнительные процессы обработки.</span><span class="sxs-lookup"><span data-stu-id="316bb-151">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span> <span data-ttu-id="316bb-152">Следующий код показывает, как можно переопределить метод <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :</span><span class="sxs-lookup"><span data-stu-id="316bb-152">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

<span data-ttu-id="316bb-153">Когда служба Windows устанавливается классом <xref:System.Configuration.Install.Installer> , должны выполняться некоторые специализированные действия.</span><span class="sxs-lookup"><span data-stu-id="316bb-153">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="316bb-154">С помощью Visual Studio для службы Windows можно специально создавать подобные установщики и добавлять их в проект.</span><span class="sxs-lookup"><span data-stu-id="316bb-154">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>

## <a name="set-service-status"></a><span data-ttu-id="316bb-155">Установка состояния службы</span><span class="sxs-lookup"><span data-stu-id="316bb-155">Set service status</span></span>

<span data-ttu-id="316bb-156">Службы сообщают о своем состоянии диспетчеру управления службами, чтобы пользователи могли определить, работает ли служба корректно.</span><span class="sxs-lookup"><span data-stu-id="316bb-156">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="316bb-157">По умолчанию, службы, которые наследуют из <xref:System.ServiceProcess.ServiceBase> , сообщают ограниченный набор параметров состояния, включая "Остановлена", Приостановлена" и "Выполняется".</span><span class="sxs-lookup"><span data-stu-id="316bb-157">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="316bb-158">Если служба сразу не запускается, то может быть полезно обеспечить индикацию состояния "Ожидание запуска".</span><span class="sxs-lookup"><span data-stu-id="316bb-158">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="316bb-159">Параметры состояния ожидания запуска и ожидания остановки также можно реализовать путем добавления кода, вызывающего функцию Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).</span><span class="sxs-lookup"><span data-stu-id="316bb-159">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).</span></span>

<span data-ttu-id="316bb-160">Чтобы реализовать состояние ожидания службы, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="316bb-160">To implement service pending status:</span></span>

1. <span data-ttu-id="316bb-161">Добавьте оператор `using` или объявление `Imports` в пространство имен <xref:System.Runtime.InteropServices?displayProperty=nameWithType> в файле MyNewService.cs или MyNewService.vb.</span><span class="sxs-lookup"><span data-stu-id="316bb-161">Add a `using` statement or `Imports` declaration for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="316bb-162">Добавьте следующий код в файл MyNewService.cs для объявления значений `ServiceState` и добавления структуры для состояния, которая будет использоваться при вызове неуправляемого кода:</span><span class="sxs-lookup"><span data-stu-id="316bb-162">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

    ```csharp
    public enum ServiceState
    {
        SERVICE_STOPPED = 0x00000001,
        SERVICE_START_PENDING = 0x00000002,
        SERVICE_STOP_PENDING = 0x00000003,
        SERVICE_RUNNING = 0x00000004,
        SERVICE_CONTINUE_PENDING = 0x00000005,
        SERVICE_PAUSE_PENDING = 0x00000006,
        SERVICE_PAUSED = 0x00000007,
    }

    [StructLayout(LayoutKind.Sequential)]
    public struct ServiceStatus
    {
        public int dwServiceType;
        public ServiceState dwCurrentState;
        public int dwControlsAccepted;
        public int dwWin32ExitCode;
        public int dwServiceSpecificExitCode;
        public int dwCheckPoint;
        public int dwWaitHint;
    };
    ```

    ```vb
    Public Enum ServiceState
        SERVICE_STOPPED = 1
        SERVICE_START_PENDING = 2
        SERVICE_STOP_PENDING = 3
        SERVICE_RUNNING = 4
        SERVICE_CONTINUE_PENDING = 5
        SERVICE_PAUSE_PENDING = 6
        SERVICE_PAUSED = 7
    End Enum

    <StructLayout(LayoutKind.Sequential)>
    Public Structure ServiceStatus
        Public dwServiceType As Long
        Public dwCurrentState As ServiceState
        Public dwControlsAccepted As Long
        Public dwWin32ExitCode As Long
        Public dwServiceSpecificExitCode As Long
        Public dwCheckPoint As Long
        Public dwWaitHint As Long
    End Structure
    ```

3. <span data-ttu-id="316bb-163">Теперь в классе `MyNewService` объявите [функцию SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) с помощью вызова [неуправляемого кода](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="316bb-163">Now, in the `MyNewService` class, declare the [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="316bb-164">Для реализации состояния ожидания запуска добавьте следующий код в начало метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :</span><span class="sxs-lookup"><span data-stu-id="316bb-164">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

    ```csharp
    // Update the service state to Start Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Start Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

5. <span data-ttu-id="316bb-165">Для присвоения состоянию значения "Запуск" добавьте код в конце метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="316bb-165">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>

    ```csharp
    // Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

6. <span data-ttu-id="316bb-166">(Необязательно) Повторите данную процедуру для метода <xref:System.ServiceProcess.ServiceBase.OnStop%2A> .</span><span class="sxs-lookup"><span data-stu-id="316bb-166">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="316bb-167">[Диспетчер служб](/windows/desktop/Services/service-control-manager) использует члены `dwWaitHint` и `dwCheckpoint` [структуры SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status), чтобы определить время, в течение которого нужно ожидать запуск или завершение работы службы Windows.</span><span class="sxs-lookup"><span data-stu-id="316bb-167">The [Service Control Manager](/windows/desktop/Services/service-control-manager) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/desktop/api/winsvc/ns-winsvc-_service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="316bb-168">Если ваши методы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> выполняются долго, ваша служба может запросить больше времени, повторно вызвав функцию [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) с увеличенным значением `dwCheckPoint`.</span><span class="sxs-lookup"><span data-stu-id="316bb-168">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) again with an incremented `dwCheckPoint` value.</span></span>

## <a name="add-installers-to-the-service"></a><span data-ttu-id="316bb-169">Добавление установщиков в службу</span><span class="sxs-lookup"><span data-stu-id="316bb-169">Add installers to the service</span></span>

<span data-ttu-id="316bb-170">Чтобы получить возможность запустить службу Windows, выполните установку, при которой служба будет зарегистрирована в диспетчере служб.</span><span class="sxs-lookup"><span data-stu-id="316bb-170">Before you can run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="316bb-171">В проект можно добавить установщики, которые обрабатывают  сведения о регистрации.</span><span class="sxs-lookup"><span data-stu-id="316bb-171">You can add installers to your project that handle the registration details.</span></span>

1. <span data-ttu-id="316bb-172">В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="316bb-172">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="316bb-173">Щелкните фон конструктора, чтобы выбрать саму службу, а не какой-либо из ее элементов.</span><span class="sxs-lookup"><span data-stu-id="316bb-173">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>

3. <span data-ttu-id="316bb-174">Откройте контекстное меню в окне конструктора (в случае применения указательного устройства щелкните правой кнопкой мыши внутри окна) и нажмите **Добавить установщик**.</span><span class="sxs-lookup"><span data-stu-id="316bb-174">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>

   <span data-ttu-id="316bb-175">По умолчанию в проект добавляется класс компонента, содержащий два установщика.</span><span class="sxs-lookup"><span data-stu-id="316bb-175">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="316bb-176">Компоненту присваивается имя **ProjectInstaller**, а содержащиеся в нем установщики предназначаются для установки службы и связанного со службой процесса.</span><span class="sxs-lookup"><span data-stu-id="316bb-176">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>

4. <span data-ttu-id="316bb-177">В представлении **Конструктор** для **ProjectInstaller**выберите **serviceInstaller1** для проекта Visual C# или **ServiceInstaller1** для проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="316bb-177">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>

5. <span data-ttu-id="316bb-178">Убедитесь, что в окне **Свойства** свойство <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> имеет значение **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="316bb-178">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

6. <span data-ttu-id="316bb-179">Введите для свойства **Описание** какой нибудь текст, например, "Пример службы".</span><span class="sxs-lookup"><span data-stu-id="316bb-179">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="316bb-180">Этот текст отображается в окне «Службы» и помогает пользователю идентифицировать службу, а также и понять, для чего она используется.</span><span class="sxs-lookup"><span data-stu-id="316bb-180">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>

7. <span data-ttu-id="316bb-181">Введите для свойства <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> текст, который будет отображаться в окне «Службы» в столбце **Имя** .</span><span class="sxs-lookup"><span data-stu-id="316bb-181">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="316bb-182">Например, можно ввести «Отображаемое имя MyNewService».</span><span class="sxs-lookup"><span data-stu-id="316bb-182">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="316bb-183">Это имя может отличаться от значения свойства <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , которое представляет собой имя, используемое в системе (например, если для запуска своей службы вы используете команду `net start` ).</span><span class="sxs-lookup"><span data-stu-id="316bb-183">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>

8. <span data-ttu-id="316bb-184">Задайте для свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="316bb-184">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>

     <span data-ttu-id="316bb-185">![Свойства установщика для службы Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span><span class="sxs-lookup"><span data-stu-id="316bb-185">![Installer Properties for a Windows service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>

9. <span data-ttu-id="316bb-186">В конструкторе щелкните **serviceProcessInstaller1** для проекта Visual C# или **ServiceProcessInstaller1** для проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="316bb-186">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="316bb-187">Задайте для свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> значение <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span><span class="sxs-lookup"><span data-stu-id="316bb-187">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="316bb-188">Это позволит установить и запускать службу от имени локальной системной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="316bb-188">This causes the service to be installed and to run using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="316bb-189">У учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalSystem> имеется множество разрешений, включая разрешение на запись в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="316bb-189">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="316bb-190">Эту учетную запись следует использовать с осторожностью, поскольку это может увеличить риск атак с помощью вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="316bb-190">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="316bb-191">Для других задач следует рассмотреть возможность использования учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalService>, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя.</span><span class="sxs-lookup"><span data-stu-id="316bb-191">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="316bb-192">В этом примере произойдет ошибка, если вы попытаетесь использовать учетную запись <xref:System.ServiceProcess.ServiceAccount.LocalService> , так как для нее требуется разрешение на запись в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="316bb-192">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="316bb-193">Дополнительные сведения об установщиках см. в статье [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="316bb-193">For more information about installers, see [How to: Add Installers to Your service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="316bb-194">Установка параметров запуска (необязательно)</span><span class="sxs-lookup"><span data-stu-id="316bb-194">(Optional) Set startup parameters</span></span>

<span data-ttu-id="316bb-195">Служба Windows, как и любой другой исполняемый файл, может принимать аргументы командной строки или параметры запуска.</span><span class="sxs-lookup"><span data-stu-id="316bb-195">A Windows service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="316bb-196">При добавлении кода в параметры запуска процесса пользователи могут запускать свою службу со своими собственными специальными параметрами с помощью окна "Службы" на панели управления Windows.</span><span class="sxs-lookup"><span data-stu-id="316bb-196">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="316bb-197">Тем не менее, эти параметры запуска не сохраняются при следующем запуске службы.</span><span class="sxs-lookup"><span data-stu-id="316bb-197">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="316bb-198">Чтобы окончательно задать параметры запуска, их можно указать в реестре, как показано в данной процедуре.</span><span class="sxs-lookup"><span data-stu-id="316bb-198">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="316bb-199">Прежде чем добавить параметры запуска, убедитесь, что это наилучший способ передачи информации в службу.</span><span class="sxs-lookup"><span data-stu-id="316bb-199">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="316bb-200">Хотя параметры запуска просты при использовании и синтаксическом анализе, и пользователи могут легко их переопределять, для пользователей их поиск и применение может оказаться затрудненным (без документации).</span><span class="sxs-lookup"><span data-stu-id="316bb-200">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="316bb-201">Как правило, если для вашей службы требуется всего несколько параметров запуска, то целесообразно использовать реестр или файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="316bb-201">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="316bb-202">Для каждой службы Windows создается запись в разделе реестра **HKLM\System\CurrentControlSet\services**.</span><span class="sxs-lookup"><span data-stu-id="316bb-202">Every Windows service has an entry in the registry under **HKLM\System\CurrentControlSet\services**.</span></span> <span data-ttu-id="316bb-203">Для хранения информации, к которой может обращаться ваша служба, в разделе ключа службы можно использовать подраздел **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="316bb-203">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="316bb-204">Файлы конфигурации приложения для службы Windows можно использовать так же, как и для программ других типов.</span><span class="sxs-lookup"><span data-stu-id="316bb-204">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="316bb-205">Пример кода см. в разделе <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="316bb-205">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>

<span data-ttu-id="316bb-206">Чтобы добавить параметры запуска, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="316bb-206">To add startup parameters:</span></span>

1. <span data-ttu-id="316bb-207">Добавьте в метод `Main` файла Program.cs или MyNewService.Designer.vb входной параметр, который будет передавать конструктор службы.</span><span class="sxs-lookup"><span data-stu-id="316bb-207">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an input parameter to pass to the service constructor:</span></span>

   ```csharp
   static void Main(string[] args)
   {
       ServiceBase[] ServicesToRun;
       ServicesToRun = new ServiceBase[]
       {
           new MyNewService(args)
       };
       ServiceBase.Run(ServicesToRun);
   }
   ```

   ```vb
   Shared Sub Main(ByVal cmdArgs() As String)
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. <span data-ttu-id="316bb-208">Измените конструктор `MyNewService` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="316bb-208">Change the `MyNewService` constructor as follows:</span></span>

   ```csharp
   public MyNewService(string[] args)
   {
       InitializeComponent();

        string eventSourceName = "MySource";
        string logName = "MyNewLog";

        if (args.Length > 0)
        {
            eventSourceName = args[0];
        }

        if (args.Length > 1)
        {
            logName = args[1];
        }

        eventLog1 = new System.Diagnostics.EventLog();

        if (!System.Diagnostics.EventLog.SourceExists(eventSourceName))
        {
            System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName);
        }

        eventLog1.Source = eventSourceName;
        eventLog1.Log = logName;
   }
   ```

   ```vb
   Public Sub New(ByVal cmdArgs() As String)
       InitializeComponent()
       Dim eventSourceName As String = "MySource"
       Dim logName As String = "MyNewLog"
       If (cmdArgs.Count() > 0) Then
           eventSourceName = cmdArgs(0)
       End If
       If (cmdArgs.Count() > 1) Then
           logName = cmdArgs(1)
       End If
       eventLog1 = New System.Diagnostics.EventLog()
       If (Not System.Diagnostics.EventLog.SourceExists(eventSourceName)) Then
           System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="316bb-209">Этот код задает имя источника события и журнала в соответствии с заданными параметрами запуска или использует значения по умолчанию, если никакие аргументы не заданы.</span><span class="sxs-lookup"><span data-stu-id="316bb-209">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>

3. <span data-ttu-id="316bb-210">Чтобы задать аргументы командной строки, добавьте следующий код в класс `ProjectInstaller` в файле ProjectInstaller.cs или ProjectInstaller.vb:</span><span class="sxs-lookup"><span data-stu-id="316bb-210">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>

   ```csharp
   protected override void OnBeforeInstall(IDictionary savedState)
   {
       string parameter = "MySource1\" \"MyLogFile1";
       Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
       base.OnBeforeInstall(savedState);
   }
   ```

   ```vb
   Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
       Dim parameter As String = "MySource1"" ""MyLogFile1"
       Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
       MyBase.OnBeforeInstall(savedState)
   End Sub
   ```

   <span data-ttu-id="316bb-211">С помощью этого кода изменяется раздел реестра **ImagePath**, который обычно содержит полный путь к исполняемому файлу для службы Windows, путем добавления значений параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="316bb-211">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows service, by adding the default parameter values.</span></span> <span data-ttu-id="316bb-212">Для корректного запуска службы путь (а также каждый параметр) должен быть заключен в кавычки.</span><span class="sxs-lookup"><span data-stu-id="316bb-212">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="316bb-213">Чтобы изменить параметры запуска службы Windows, пользователи могут изменять параметры в разделе реестра **ImagePath**. Но лучше изменять их программными средствами и создать для пользователей удобный интерфейс для этой возможности (например, в программе управления или настройки).</span><span class="sxs-lookup"><span data-stu-id="316bb-213">To change the startup parameters for this Windows service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>

## <a name="build-the-service"></a><span data-ttu-id="316bb-214">Сборка службы</span><span class="sxs-lookup"><span data-stu-id="316bb-214">Build the service</span></span>

1. <span data-ttu-id="316bb-215">В **Обозревателе решений**откройте контекстное меню для своего проекта и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="316bb-215">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span>

   <span data-ttu-id="316bb-216">Отобразятся страницы свойств для проекта.</span><span class="sxs-lookup"><span data-stu-id="316bb-216">The property pages for your project appear.</span></span>

2. <span data-ttu-id="316bb-217">На вкладке **Приложение** в списке **Автоматически запускаемый объект** выберите **MyNewService.Program**.</span><span class="sxs-lookup"><span data-stu-id="316bb-217">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>

3. <span data-ttu-id="316bb-218">В **обозревателе решений** откройте контекстное меню проекта и щелкните **Сборка**, чтобы выполнить компиляцию проекта (или нажмите сочетание клавиш **CTRL**+**SHIFT**+**B**).</span><span class="sxs-lookup"><span data-stu-id="316bb-218">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="316bb-219">Установка службы</span><span class="sxs-lookup"><span data-stu-id="316bb-219">Install the service</span></span>

<span data-ttu-id="316bb-220">После создания службы Windows ее можно установить.</span><span class="sxs-lookup"><span data-stu-id="316bb-220">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="316bb-221">Чтобы установить службу Windows, необходимо иметь разрешения администратора на том компьютере, где выполняется установка.</span><span class="sxs-lookup"><span data-stu-id="316bb-221">To install a Windows service, you must have administrator credentials on the computer on which you're installing it.</span></span>

1. <span data-ttu-id="316bb-222">Откройте **Командную строку разработчика Visual Studio** с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="316bb-222">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span> <span data-ttu-id="316bb-223">Если вы используете мышь, щелкните правой кнопкой элемент **Developer Command Prompt for VS 2017** (Командная строка разработчика для VS 2017) в меню "Пуск" Windows и последовательно выберите **Дополнительно** > **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="316bb-223">If you’re using a mouse, right-click on **Developer Command Prompt for VS 2017** in the Windows Start menu, and then choose **More** > **Run as Administrator**.</span></span>

2. <span data-ttu-id="316bb-224">В окне **Командной строки разработчика** перейдите к папке, которая содержит выходные данные проекта (по умолчанию это подкаталог *\bin\Debug* в проекте).</span><span class="sxs-lookup"><span data-stu-id="316bb-224">In the **Developer Command Prompt** window, navigate to the folder that contains your project's output (by default, it's the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="316bb-225">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="316bb-225">Enter the following command:</span></span>

    ```shell
    installutil.exe MyNewService.exe
    ```

    <span data-ttu-id="316bb-226">Если служба установлена успешно, **installutil.exe** сообщит об успешном выполнении.</span><span class="sxs-lookup"><span data-stu-id="316bb-226">If the service installs successfully, **installutil.exe** reports success.</span></span> <span data-ttu-id="316bb-227">Если система не может найти файл **InstallUtil.exe**, убедитесь, что он есть на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="316bb-227">If the system could not find **InstallUtil.exe**, make sure that it exists on your computer.</span></span> <span data-ttu-id="316bb-228">Этот инструмент устанавливается вместе с платформой .NET Framework в папку *%windir%\Microsoft.NET\Framework[64]\\[версия платформы]*.</span><span class="sxs-lookup"><span data-stu-id="316bb-228">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\[framework version]*.</span></span> <span data-ttu-id="316bb-229">Например, для 32-разрядной версии по умолчанию используется путь *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="316bb-229">For example, the default path for the 32-bit version is *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="316bb-230">Если процесс **installutil.exe** сообщает о сбое, найдите причину в журнале установки.</span><span class="sxs-lookup"><span data-stu-id="316bb-230">If the **installutil.exe** process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="316bb-231">По умолчанию журнал находится в той же папке, что и исполняемый файл службы.</span><span class="sxs-lookup"><span data-stu-id="316bb-231">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="316bb-232">Установка может завершиться сбоем, если класс <xref:System.ComponentModel.RunInstallerAttribute> отсутствует в классе `ProjectInstaller`, значение атрибута отличается от **true** или класс `ProjectInstaller` не имеет атрибута **public**.</span><span class="sxs-lookup"><span data-stu-id="316bb-232">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, if the attribute is not set to **true**, or if the `ProjectInstaller` class is not marked **public**.</span></span>

<span data-ttu-id="316bb-233">Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="316bb-233">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="316bb-234">Запуск и выполнение службы</span><span class="sxs-lookup"><span data-stu-id="316bb-234">Start and run the service</span></span>

1. <span data-ttu-id="316bb-235">В Windows откройте классическое приложение **Службы**.</span><span class="sxs-lookup"><span data-stu-id="316bb-235">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="316bb-236">Нажмите сочетание клавиш **Windows**+**R**, чтобы открыть окно **Запуск**, введите имя файла **services.msc** и нажмите клавишу **ВВОД** или щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="316bb-236">Press **Windows**+**R** to open the **Run** box, and then enter **services.msc** and press **Enter** or click **OK**.</span></span>

     <span data-ttu-id="316bb-237">Заданное вами отображаемое имя службы отобразится в списке **Службы**, представленном в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="316bb-237">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService в окне "Службы".](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="316bb-239">В окне **Службы** откройте контекстное меню службы и нажмите **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="316bb-239">In **Services**, open the shortcut menu for your service, and then choose **Start**.</span></span>

3. <span data-ttu-id="316bb-240">Чтобы остановить работу службы, снова откройте контекстное меню службы и нажмите **Стоп**.</span><span class="sxs-lookup"><span data-stu-id="316bb-240">To stop the service, open the shortcut menu for the service, and then choose **Stop**.</span></span>

4. <span data-ttu-id="316bb-241">Для запуска и остановки службы из командной строки можно использовать команды `net start ServiceName` и `net stop ServiceName` (необязательно).</span><span class="sxs-lookup"><span data-stu-id="316bb-241">(Optional) From the command line, you can use the commands `net start ServiceName` and `net stop ServiceName` to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="316bb-242">Проверка журнала событий для службы</span><span class="sxs-lookup"><span data-stu-id="316bb-242">Verify the event log output of your service</span></span>

1. <span data-ttu-id="316bb-243">Чтобы открыть компонент **Просмотр событий**, начните вводить строку **Просмотр событий** в поле поиска на панели задач Windows и выберите **Просмотр событий** в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="316bb-243">Open **Event Viewer** by starting to type **Event Viewer** in the search box on the Windows task bar, and then selecting **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="316bb-244">В Visual Studio доступ к журналам событий можно получить, открыв **обозреватель сервера** (сочетание клавиш **CTRL**+**ALT**+**S**) и развернув узел **Журналы событий** для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="316bb-244">In Visual Studio, you can access event logs by opening **Server Explorer** (Keyboard: **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="316bb-245">В **средстве просмотра событий** разверните узел **Журналы приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="316bb-245">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="316bb-246">Найдите в списке элемент **MyNewLog** (или **MyLogFile1**, если вы использовали необязательную процедуру с аргументами командной строки) и разверните его.</span><span class="sxs-lookup"><span data-stu-id="316bb-246">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you followed the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="316bb-247">Вы увидите записи для двух действий (запуск и остановка), которые выполнила ваша служба.</span><span class="sxs-lookup"><span data-stu-id="316bb-247">You should see entries for the two actions (start and stop) that your service performed.</span></span>

     ![Просмотр записей в журнале событий с помощью компонента "Просмотр событий"](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a><span data-ttu-id="316bb-249">Удаление службы</span><span class="sxs-lookup"><span data-stu-id="316bb-249">Uninstall the service</span></span>

1. <span data-ttu-id="316bb-250">Откройте **Командную строку разработчика Visual Studio** с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="316bb-250">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="316bb-251">В окне командной строки перейдите к папке, которая содержит выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="316bb-251">In the command prompt window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="316bb-252">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="316bb-252">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="316bb-253">Если служба удалена успешно, **installutil.exe** сообщит об этом.</span><span class="sxs-lookup"><span data-stu-id="316bb-253">If the service uninstalls successfully, **installutil.exe** reports that your service was successfully removed.</span></span> <span data-ttu-id="316bb-254">Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="316bb-254">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="316bb-255">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="316bb-255">Next steps</span></span>

<span data-ttu-id="316bb-256">Завершив создание службы, вы можете создать автономную программу установки, с помощью которой другие пользователи будут устанавливать вашу службу Windows.</span><span class="sxs-lookup"><span data-stu-id="316bb-256">Now that you've created the service, you might want to create a standalone setup program that others can use to install your Windows service.</span></span> <span data-ttu-id="316bb-257">ClickOnce не поддерживает службы Windows, но вы можете создать установщик службы Windows с помощью [набора средств WiX](http://wixtoolset.org/).</span><span class="sxs-lookup"><span data-stu-id="316bb-257">ClickOnce doesn't support Windows services, but you can use the [WiX Toolset](http://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="316bb-258">Другие идеи можно почерпнуть в статье [о создании пакета установщика](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span><span class="sxs-lookup"><span data-stu-id="316bb-258">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>

<span data-ttu-id="316bb-259">Также изучите возможности компонента <xref:System.ServiceProcess.ServiceController>, который позволяет отправлять команды в установленную службу.</span><span class="sxs-lookup"><span data-stu-id="316bb-259">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

<span data-ttu-id="316bb-260">Для создания журнала событий при установке приложения можно воспользоваться установщиком, а не создавать журнал после запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="316bb-260">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="316bb-261">Кроме того, в этом случае журнал событий будет удален установщиком при удалении приложения.</span><span class="sxs-lookup"><span data-stu-id="316bb-261">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="316bb-262">Дополнительные сведения см. на странице <xref:System.Diagnostics.EventLogInstaller> .</span><span class="sxs-lookup"><span data-stu-id="316bb-262">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>

## <a name="see-also"></a><span data-ttu-id="316bb-263">См. также</span><span class="sxs-lookup"><span data-stu-id="316bb-263">See also</span></span>

- [<span data-ttu-id="316bb-264">Приложения служб Windows</span><span class="sxs-lookup"><span data-stu-id="316bb-264">Windows service applications</span></span>](../../../docs/framework/windows-services/index.md)
- [<span data-ttu-id="316bb-265">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="316bb-265">Introduction to Windows service applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="316bb-266">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="316bb-266">How to: Debug Windows service applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="316bb-267">Службы (Windows)</span><span class="sxs-lookup"><span data-stu-id="316bb-267">Services (Windows)</span></span>](https://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
