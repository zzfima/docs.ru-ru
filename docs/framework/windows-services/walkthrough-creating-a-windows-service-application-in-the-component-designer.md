---
title: Учебник. Создание приложения службы Windows
ms.date: 03/14/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: 786b9e28607cced0a15793415ff5fd470b559374
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262490"
---
# <a name="tutorial-create-a-windows-service-app"></a><span data-ttu-id="321f1-102">Учебник. Создание приложения службы Windows</span><span class="sxs-lookup"><span data-stu-id="321f1-102">Tutorial: Create a Windows service app</span></span>

<span data-ttu-id="321f1-103">Из этой статьи вы узнаете, как создать в Visual Studio приложение службы Windows, которое записывает сообщения в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="321f1-103">This article demonstrates how to create a Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="321f1-104">Создание службы</span><span class="sxs-lookup"><span data-stu-id="321f1-104">Create a service</span></span>

<span data-ttu-id="321f1-105">Для начала создайте проект и настройте значения, необходимые для правильной работы службы.</span><span class="sxs-lookup"><span data-stu-id="321f1-105">To begin, create the project and set the values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="321f1-106">В Visual Studio в меню **Файл** последовательно выберите пункты **Создать** > **Проект** (или нажмите клавиши **CTRL**+**SHIFT**+**N**), чтобы открыть окно **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="321f1-106">From the Visual Studio **File** menu, select **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** window.</span></span>

2. <span data-ttu-id="321f1-107">Найдите и выберите шаблон проекта **Служба Windows (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="321f1-107">Navigate to and select the **Windows Service (.NET Framework)** project template.</span></span> <span data-ttu-id="321f1-108">Чтобы найти его, разверните узел **Установленные**, затем узел **Visual C#** или **Visual Basic** и выберите **Рабочий стол Windows**.</span><span class="sxs-lookup"><span data-stu-id="321f1-108">To find it, expand **Installed** and **Visual C#** or **Visual Basic**, then select **Windows Desktop**.</span></span> <span data-ttu-id="321f1-109">Можно также ввести запрос *Служба Windows* в поле поиска в правом верхнем углу и нажать клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="321f1-109">Or, enter *Windows Service* in the search box on the upper right and press **Enter**.</span></span>

   ![Шаблон приложения Windows в диалоговом окне нового проекта Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="321f1-111">Если вы не видите здесь шаблон **Служба Windows**, попробуйте установить рабочую нагрузку **Разработка классических приложений .NET**.</span><span class="sxs-lookup"><span data-stu-id="321f1-111">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload:</span></span>
   >  
   > <span data-ttu-id="321f1-112">В диалоговом окне **Новый проект** выберите ссылку **Открыть установщик Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="321f1-112">In the **New Project** dialog, select **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="321f1-113">Выберите рабочую нагрузку **Разработка классических приложений .NET** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="321f1-113">Select the **.NET desktop development** workload, and then select **Modify**.</span></span>

3. <span data-ttu-id="321f1-114">В поле **Имя** введите *MyNewService*, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="321f1-114">For **Name**, enter *MyNewService*, and then select **OK**.</span></span>

   <span data-ttu-id="321f1-115">Откроется вкладка **Проект** (**Service1.cs [Проект]** или **Service1.vb [Проект]**).</span><span class="sxs-lookup"><span data-stu-id="321f1-115">The **Design** tab appears (**Service1.cs [Design]** or **Service1.vb [Design]**).</span></span>
   
   <span data-ttu-id="321f1-116">Этот шаблон проекта содержит класс компонента с именем `Service1`, наследуемый от <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-116">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="321f1-117">В нем собран основной служебный код, в том числе код для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="321f1-117">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="321f1-118">Переименование службы</span><span class="sxs-lookup"><span data-stu-id="321f1-118">Rename the service</span></span>

<span data-ttu-id="321f1-119">Измените имя службы с **Service1** на **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="321f1-119">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="321f1-120">В **обозревателе решений** выберите файл **Service1.cs** или **Service1.vb**, а затем выберите в контекстном меню команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="321f1-120">In **Solution Explorer**, select **Service1.cs**, or **Service1.vb**, and choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="321f1-121">Переименуйте файл в **MyNewService.cs** или **MyNewService.vb** и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="321f1-121">Rename the file to **MyNewService.cs**, or **MyNewService.vb**, and then press **Enter**</span></span>

    <span data-ttu-id="321f1-122">Появится всплывающее окно, предлагающее переименовать все ссылки на элемент кода *Service1*.</span><span class="sxs-lookup"><span data-stu-id="321f1-122">A pop-up window appears asking whether you would like to rename all references to the code element *Service1*.</span></span>

2. <span data-ttu-id="321f1-123">Выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="321f1-123">In the pop-up window, select **Yes**.</span></span>

    <span data-ttu-id="321f1-124">![Запрос на переименование](media/windows-service-rename.png "Запрос на переименование службы Windows")</span><span class="sxs-lookup"><span data-stu-id="321f1-124">![Rename prompt](media/windows-service-rename.png "Windows service rename prompt")</span></span>

2. <span data-ttu-id="321f1-125">На вкладке **Проект** выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="321f1-125">In the **Design** tab, select **Properties** from the shortcut menu.</span></span> <span data-ttu-id="321f1-126">В окне **Свойства** измените значение **ServiceName** на *MyNewService*.</span><span class="sxs-lookup"><span data-stu-id="321f1-126">From the **Properties** window, change the **ServiceName** value to *MyNewService*.</span></span>

    <span data-ttu-id="321f1-127">![Свойства службы](media/windows-service-properties.png "Свойства службы Windows")</span><span class="sxs-lookup"><span data-stu-id="321f1-127">![Service properties](media/windows-service-properties.png "Windows service properties")</span></span>

3. <span data-ttu-id="321f1-128">В меню **Файл** выберите команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="321f1-128">Select **Save All** from the **File** menu.</span></span>


## <a name="add-features-to-the-service"></a><span data-ttu-id="321f1-129">Добавление компонентов в службу</span><span class="sxs-lookup"><span data-stu-id="321f1-129">Add features to the service</span></span>

<span data-ttu-id="321f1-130">В этом разделе к службе Windows будет добавлен настраиваемый журнал событий.</span><span class="sxs-lookup"><span data-stu-id="321f1-130">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="321f1-131">Компонент <xref:System.Diagnostics.EventLog> — это пример типа компонента, который можно добавить в службу Windows.</span><span class="sxs-lookup"><span data-stu-id="321f1-131">The <xref:System.Diagnostics.EventLog> component is an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="321f1-132">Добавление возможности работы с настраиваемым журналом событий</span><span class="sxs-lookup"><span data-stu-id="321f1-132">Add custom event log functionality</span></span>

1. <span data-ttu-id="321f1-133">В **обозревателе решений** в контекстном меню для файла **MyNewService.cs** или **MyNewService.vb** выберите пункт **Показать конструктор**.</span><span class="sxs-lookup"><span data-stu-id="321f1-133">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="321f1-134">На **панели элементов** разверните раздел **Компоненты** и перетащите компонент **EventLog** на вкладку **Service1.cs [Проект]** или **Service1.vb [Проект]**.</span><span class="sxs-lookup"><span data-stu-id="321f1-134">In **Toolbox**, expand **Components**, and then drag the **EventLog** component to the **Service1.cs [Design]**, or **Service1.vb [Design]** tab.</span></span>

3. <span data-ttu-id="321f1-135">В **обозревателе решений** в контекстном меню для файла **MyNewService.cs** или **MyNewService.vb** выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="321f1-135">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Code**.</span></span>

4. <span data-ttu-id="321f1-136">Определите пользовательский журнал событий.</span><span class="sxs-lookup"><span data-stu-id="321f1-136">Define a custom event log.</span></span> <span data-ttu-id="321f1-137">Для C# измените существующий конструктор `MyNewService()`. Для Visual Basic добавьте конструктор `New()`.</span><span class="sxs-lookup"><span data-stu-id="321f1-137">For C#, edit the existing `MyNewService()` constructor; for Visual Basic, add the `New()` constructor:</span></span>

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new EventLog();
        if (!EventLog.SourceExists("MySource"))
        {
            EventLog.CreateEventSource("MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <span data-ttu-id="321f1-138">Добавьте оператор `using` в файл **MyNewService.cs** (если его еще нет) или оператор `Imports` в файл **MyNewService.vb** для пространства имен <xref:System.Diagnostics?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-138">Add a `using` statement to **MyNewService.cs** (if it doesn't already exist), or an `Imports` statement **MyNewService.vb**, for the <xref:System.Diagnostics?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. <span data-ttu-id="321f1-139">В меню **Файл** выберите команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="321f1-139">Select **Save All** from the **File** menu.</span></span>

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="321f1-140">Определение действий при запуске службы</span><span class="sxs-lookup"><span data-stu-id="321f1-140">Define what occurs when the service starts</span></span>

<span data-ttu-id="321f1-141">В редакторе кода для файла **MyNewService.cs** или **MyNewService.vb** найдите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Пустое определение метода было автоматически добавлено при создании проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="321f1-141">In the code editor for **MyNewService.cs** or **MyNewService.vb**, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method; Visual Studio automatically created an empty method definition when you created the project.</span></span> <span data-ttu-id="321f1-142">Добавьте код, с помощью которой запись сохраняется в журнале событий при запуске службы:</span><span class="sxs-lookup"><span data-stu-id="321f1-142">Add code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a><span data-ttu-id="321f1-143">Опрос</span><span class="sxs-lookup"><span data-stu-id="321f1-143">Polling</span></span>

<span data-ttu-id="321f1-144">Так как приложение службы предполагает длительное время выполнения, оно обычно опрашивает или отслеживает систему. Отслеживание настраивается в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="321f1-144">Because a service application is designed to be long-running, it usually polls or monitors the system, which you set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="321f1-145">После начала работы службы метод `OnStart` должен возвращать управление операционной системе, чтобы она не блокировалась.</span><span class="sxs-lookup"><span data-stu-id="321f1-145">The `OnStart` method must return to the operating system after the service's operation has begun so that the system isn't blocked.</span></span> 

<span data-ttu-id="321f1-146">Для создания простого механизма опроса используйте компонент <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-146">To set up a simple polling mechanism, use the <xref:System.Timers.Timer?displayProperty=nameWithType> component.</span></span> <span data-ttu-id="321f1-147">Таймер через определенные интервалы времени генерирует событие <xref:System.Timers.Timer.Elapsed>, при возникновении которых служба может выполнять отслеживание.</span><span class="sxs-lookup"><span data-stu-id="321f1-147">The timer raises an <xref:System.Timers.Timer.Elapsed> event at regular intervals, at which time your service can do its monitoring.</span></span> <span data-ttu-id="321f1-148">Компонент <xref:System.Timers.Timer> используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="321f1-148">You use the <xref:System.Timers.Timer> component as follows:</span></span>

- <span data-ttu-id="321f1-149">Задайте свойства компонента <xref:System.Timers.Timer> в методе `MyNewService.OnStart`.</span><span class="sxs-lookup"><span data-stu-id="321f1-149">Set the properties of the <xref:System.Timers.Timer> component in the `MyNewService.OnStart` method.</span></span>
- <span data-ttu-id="321f1-150">Запустите таймер, вызвав метод <xref:System.Timers.Timer.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="321f1-150">Start the timer by calling the <xref:System.Timers.Timer.Start%2A> method.</span></span>

##### <a name="set-up-the-polling-mechanism"></a><span data-ttu-id="321f1-151">Настройка механизма опроса.</span><span class="sxs-lookup"><span data-stu-id="321f1-151">Set up the polling mechanism.</span></span>

1. <span data-ttu-id="321f1-152">Чтобы настроить механизм опроса, добавьте следующий код в событие `MyNewService.OnStart`:</span><span class="sxs-lookup"><span data-stu-id="321f1-152">Add the following code in the `MyNewService.OnStart` event to set up the polling mechanism:</span></span>

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. <span data-ttu-id="321f1-153">Добавьте оператор `using` в файл **MyNewService.cs** или оператор `Imports` в файл **MyNewService.vb** для пространства имен <xref:System.Timers?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-153">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Timers?displayProperty=nameWithType> namespace:</span></span>


   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```


3. <span data-ttu-id="321f1-154">В классе `MyNewService` добавьте метод `OnTimer` для обработки события <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-154">In the `MyNewService` class, add the `OnTimer` method to handle the <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> event:</span></span>

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
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

4. <span data-ttu-id="321f1-155">В класс `MyNewService` добавьте переменную-член.</span><span class="sxs-lookup"><span data-stu-id="321f1-155">In the `MyNewService` class, add a member variable.</span></span> <span data-ttu-id="321f1-156">Она содержит идентификатор следующего события, которое сохраняется в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="321f1-156">It contains the identifier of the next event to write into the event log:</span></span>

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

<span data-ttu-id="321f1-157">Задачи можно выполнять с помощью фоновых рабочих потоков, а не выполнять всю работу в основном потоке.</span><span class="sxs-lookup"><span data-stu-id="321f1-157">Instead of running all your work on the main thread, you can run tasks by using background worker threads.</span></span> <span data-ttu-id="321f1-158">Для получения дополнительной информации см. <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="321f1-158">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="321f1-159">Определение действий при остановке службы</span><span class="sxs-lookup"><span data-stu-id="321f1-159">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="321f1-160">Вставьте в метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A> строку кода, с помощью которой запись сохраняется в журнале событий при остановке службы:</span><span class="sxs-lookup"><span data-stu-id="321f1-160">Insert a line of code in the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="321f1-161">Определение других действий для службы</span><span class="sxs-lookup"><span data-stu-id="321f1-161">Define other actions for the service</span></span>

<span data-ttu-id="321f1-162">Вы можете переопределить методы <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> и <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>, добавив дополнительные процессы обработки.</span><span class="sxs-lookup"><span data-stu-id="321f1-162">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span> 

<span data-ttu-id="321f1-163">Следующий код показывает, как можно переопределить метод <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> в классе `MyNewService`:</span><span class="sxs-lookup"><span data-stu-id="321f1-163">The following code shows how you to override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method in the `MyNewService` class:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]


## <a name="set-service-status"></a><span data-ttu-id="321f1-164">Установка состояния службы</span><span class="sxs-lookup"><span data-stu-id="321f1-164">Set service status</span></span>

<span data-ttu-id="321f1-165">Службы сообщают о своем состоянии [диспетчеру служб](/windows/desktop/Services/service-control-manager), чтобы пользователь мог определить, работает ли служба правильно.</span><span class="sxs-lookup"><span data-stu-id="321f1-165">Services report their status to the [Service Control Manager](/windows/desktop/Services/service-control-manager) so that a user can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="321f1-166">По умолчанию служба, которая наследуется от <xref:System.ServiceProcess.ServiceBase>, сообщает ограниченный набор состояний, включая SERVICE_STOPPED, SERVICE_PAUSED и SERVICE_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="321f1-166">By default, a service that inherits from <xref:System.ServiceProcess.ServiceBase> reports a limited set of status settings, which include SERVICE_STOPPED, SERVICE_PAUSED, and SERVICE_RUNNING.</span></span> <span data-ttu-id="321f1-167">Если служба запускается не сразу, полезно обеспечить сообщение состояния SERVICE_START_PENDING.</span><span class="sxs-lookup"><span data-stu-id="321f1-167">If a service takes a while to start up, it's useful to report a SERVICE_START_PENDING status.</span></span> 

<span data-ttu-id="321f1-168">Состояния ERVICE_START_PENDING и SERVICE_STOP_PENDING можно реализовать путем добавления кода, вызывающего функцию Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).</span><span class="sxs-lookup"><span data-stu-id="321f1-168">You can implement the SERVICE_START_PENDING and SERVICE_STOP_PENDING status settings by adding code that calls the Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function.</span></span>


### <a name="implement-service-pending-status"></a><span data-ttu-id="321f1-169">Реализация состояния ожидания службы</span><span class="sxs-lookup"><span data-stu-id="321f1-169">Implement service pending status</span></span>

1. <span data-ttu-id="321f1-170">Добавьте оператор `using` в файл **MyNewService.cs** или оператор `Imports` в файл **MyNewService.vb** для пространства имен <xref:System.Runtime.InteropServices?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-170">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="321f1-171">Добавьте следующий код в файл **MyNewService.cs** или **MyNewService.vb** для объявления значений `ServiceState` и добавления структуры для состояния, которая будет использоваться при вызове неуправляемого кода:</span><span class="sxs-lookup"><span data-stu-id="321f1-171">Add the following code to **MyNewService.cs**, or **MyNewService.vb**, to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

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

3. <span data-ttu-id="321f1-172">В классе `MyNewService` объявите функцию [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) с помощью [вызова неуправляемого кода](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="321f1-172">In the `MyNewService` class, declare the [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="321f1-173">Для реализации состояния SERVICE_START_PENDING добавьте следующий код в начало метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>:</span><span class="sxs-lookup"><span data-stu-id="321f1-173">To implement the SERVICE_START_PENDING status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

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

5. <span data-ttu-id="321f1-174">Для установки состояния SERVICE_RUNNING добавьте код в конце метода `OnStart`:</span><span class="sxs-lookup"><span data-stu-id="321f1-174">Add code to the end of the `OnStart` method to set the status to SERVICE_RUNNING:</span></span>

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

6. <span data-ttu-id="321f1-175">Если метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A> выполняется долго, повторите данную процедуру для `OnStop` (необязательно).</span><span class="sxs-lookup"><span data-stu-id="321f1-175">(Optional) If <xref:System.ServiceProcess.ServiceBase.OnStop%2A> is a long-running method, repeat this procedure in the `OnStop` method.</span></span> <span data-ttu-id="321f1-176">Реализуйте состояние SERVICE_STOP_PENDING и обеспечьте возврат состояния SERVICE_STOPPED до того, как метод `OnStop` вернет управление.</span><span class="sxs-lookup"><span data-stu-id="321f1-176">Implement the SERVICE_STOP_PENDING status and return the SERVICE_STOPPED status before the `OnStop` method exits.</span></span>

   <span data-ttu-id="321f1-177">Например:</span><span class="sxs-lookup"><span data-stu-id="321f1-177">For example:</span></span>

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)    
    ```

> [!NOTE]
> <span data-ttu-id="321f1-178">Диспетчер служб использует члены `dwWaitHint` и `dwCheckpoint` [структуры SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status), чтобы определить время, в течение которого нужно ожидать запуска или завершения работы службы Windows.</span><span class="sxs-lookup"><span data-stu-id="321f1-178">The Service Control Manager uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/desktop/api/winsvc/ns-winsvc-_service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="321f1-179">Если методы `OnStart` и `OnStop` выполняются долго, служба может запросить больше времени, повторно вызвав функцию `SetServiceStatus` с увеличенным значением `dwCheckPoint`.</span><span class="sxs-lookup"><span data-stu-id="321f1-179">If your `OnStart` and `OnStop` methods run long, your service can request more time by calling `SetServiceStatus` again with an incremented `dwCheckPoint` value.</span></span>

## <a name="add-installers-to-the-service"></a><span data-ttu-id="321f1-180">Добавление установщиков в службу</span><span class="sxs-lookup"><span data-stu-id="321f1-180">Add installers to the service</span></span>

<span data-ttu-id="321f1-181">Перед тем как запускать службу Windows, ее нужно установить. При этом она регистрируется в диспетчере служб.</span><span class="sxs-lookup"><span data-stu-id="321f1-181">Before you run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="321f1-182">В проект можно добавить установщики, которые обрабатывают сведения о регистрации.</span><span class="sxs-lookup"><span data-stu-id="321f1-182">Add installers to your project to handle the registration details.</span></span>

1. <span data-ttu-id="321f1-183">В **обозревателе решений** в контекстном меню для файла **MyNewService.cs** или **MyNewService.vb** выберите пункт **Показать конструктор**.</span><span class="sxs-lookup"><span data-stu-id="321f1-183">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="321f1-184">В представлении **Конструктор** щелкните область фона правой кнопкой мыши и выберите в контекстном меню команду **Добавить установщик**.</span><span class="sxs-lookup"><span data-stu-id="321f1-184">In the **Design** view, select the background area, then choose **Add Installer** from the shortcut menu.</span></span>

     <span data-ttu-id="321f1-185">По умолчанию Visual Studio добавляет в проект класс компонента `ProjectInstaller`, содержащий два установщика.</span><span class="sxs-lookup"><span data-stu-id="321f1-185">By default, Visual Studio adds a component class named `ProjectInstaller`, which contains two installers, to your project.</span></span> <span data-ttu-id="321f1-186">Они предназначены для установки службы и связанного со службой процесса.</span><span class="sxs-lookup"><span data-stu-id="321f1-186">These installers are for your service and for the service's associated process.</span></span>

4. <span data-ttu-id="321f1-187">В представлении **Конструктор** для **ProjectInstaller** выберите **serviceInstaller1** для проекта Visual C# или **ServiceInstaller1** для проекта Visual Basic. Затем в контекстном меню выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="321f1-187">In the **Design** view for **ProjectInstaller**, select **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span>

5. <span data-ttu-id="321f1-188">Убедитесь в том, что в окне **Свойства** свойство <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> имеет значение **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="321f1-188">In the **Properties** window, verify the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

6. <span data-ttu-id="321f1-189">Введите для свойства <xref:System.ServiceProcess.ServiceInstaller.Description%2A> какой нибудь текст, например *Пример службы*.</span><span class="sxs-lookup"><span data-stu-id="321f1-189">Add text to the <xref:System.ServiceProcess.ServiceInstaller.Description%2A> property, such as *A sample service*.</span></span> 

     <span data-ttu-id="321f1-190">Этот текст отображается в столбце **Описание** в окне **Службы** и помогает пользователю понять, для чего служба нужна.</span><span class="sxs-lookup"><span data-stu-id="321f1-190">This text appears in the **Description** column of the **Services** window and describes the service to the user.</span></span>

    <span data-ttu-id="321f1-191">![Описание службы в окне "Службы".](media/windows-service-description.png "Описание службы")</span><span class="sxs-lookup"><span data-stu-id="321f1-191">![Service description in the Services window.](media/windows-service-description.png "Service description")</span></span>

7. <span data-ttu-id="321f1-192">Введите текст для свойства <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A>,</span><span class="sxs-lookup"><span data-stu-id="321f1-192">Add text to the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property.</span></span> <span data-ttu-id="321f1-193">например *Отображаемое имя MyNewService*.</span><span class="sxs-lookup"><span data-stu-id="321f1-193">For example, *MyNewService Display Name*.</span></span> 

     <span data-ttu-id="321f1-194">Этот текст отображается в столбце **Отображаемое имя** в окне **Службы**.</span><span class="sxs-lookup"><span data-stu-id="321f1-194">This text appears in the **Display Name** column of the **Services** window.</span></span> <span data-ttu-id="321f1-195">Это имя может отличаться от значения свойства <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>, которое представляет собой имя, используемое в системе (например, когда вы запускаете службу с помощью команды `net start`).</span><span class="sxs-lookup"><span data-stu-id="321f1-195">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name the system uses (for example, the name you use for the `net start` command to start your service).</span></span>

8. <span data-ttu-id="321f1-196">Выберите для свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение <xref:System.ServiceProcess.ServiceStartMode.Automatic> в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="321f1-196">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic> from the drop-down list.</span></span>

9. <span data-ttu-id="321f1-197">В итоге окно **Свойства** должно выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="321f1-197">When you're finished, the **Properties** windows should look like the following figure:</span></span>

     <span data-ttu-id="321f1-198">![Свойства установщика для службы Windows](media/windows-service-installer-properties.png "Свойства установщика службы Windows")</span><span class="sxs-lookup"><span data-stu-id="321f1-198">![Installer Properties for a Windows service](media/windows-service-installer-properties.png "Windows service installer properties")</span></span>

9. <span data-ttu-id="321f1-199">В представлении **Конструктор** для **ProjectInstaller** выберите **serviceProcessInstaller1** для проекта Visual C# или **ServiceProcessInstaller1** для проекта Visual Basic. Затем в контекстном меню выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="321f1-199">In the **Design** view for **ProjectInstaller**, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="321f1-200">Выберите для свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> значение <xref:System.ServiceProcess.ServiceAccount.LocalSystem> в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="321f1-200">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem> from the drop-down list.</span></span> 

     <span data-ttu-id="321f1-201">Это позволит установить и запускать службу от имени локальной системной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="321f1-201">This setting installs the service and runs it by using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="321f1-202">У учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalSystem> имеется множество разрешений, включая разрешение на запись в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="321f1-202">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="321f1-203">Эту учетную запись следует использовать с осторожностью, поскольку это может увеличить риск атак с помощью вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="321f1-203">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="321f1-204">Для других задач следует рассмотреть возможность использования учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalService> , которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя.</span><span class="sxs-lookup"><span data-stu-id="321f1-204">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="321f1-205">В этом примере произойдет ошибка, если вы попытаетесь использовать учетную запись <xref:System.ServiceProcess.ServiceAccount.LocalService> , так как для нее требуется разрешение на запись в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="321f1-205">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="321f1-206">Дополнительные сведения об установщиках см. в руководстве по [ добавлению установщиков в приложение-службу](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="321f1-206">For more information about installers, see [How to: Add installers to your service application](how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="321f1-207">Установка параметров запуска (необязательно)</span><span class="sxs-lookup"><span data-stu-id="321f1-207">(Optional) Set startup parameters</span></span>

> [!NOTE]
> <span data-ttu-id="321f1-208">Прежде чем добавлять параметры запуска, решите, является ли это наилучшим способом передачи информации в службу.</span><span class="sxs-lookup"><span data-stu-id="321f1-208">Before you decide to add startup parameters, consider whether it's the best way to pass information to your service.</span></span> <span data-ttu-id="321f1-209">Хотя параметры запуска просты для использования и синтаксического анализа и пользователи могут легко их переопределять, для пользователей их поиск и применение могут оказаться затрудненными (без документации).</span><span class="sxs-lookup"><span data-stu-id="321f1-209">Although they're easy to use and parse, and a user can easily override them, they might be harder for a user to discover and use without documentation.</span></span> <span data-ttu-id="321f1-210">Как правило, если вашей службе требуется всего несколько параметров запуска, то следует использовать реестр или файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="321f1-210">Generally, if your service requires more than just a few startup parameters, you should use the registry or a configuration file instead.</span></span> 

<span data-ttu-id="321f1-211">Служба Windows может принимать аргументы командной строки или параметры запуска.</span><span class="sxs-lookup"><span data-stu-id="321f1-211">A Windows service can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="321f1-212">При добавлении кода в параметры запуска процесса пользователь может запускать службу со своими собственными специальными параметрами из окна свойств службы.</span><span class="sxs-lookup"><span data-stu-id="321f1-212">When you add code to process startup parameters, a user can start your service with their own custom startup parameters in the service properties window.</span></span> <span data-ttu-id="321f1-213">Однако эти параметры запуска не сохраняются при следующем запуске службы.</span><span class="sxs-lookup"><span data-stu-id="321f1-213">However, these startup parameters aren't persisted the next time the service starts.</span></span> <span data-ttu-id="321f1-214">Задать постоянные параметры запуска можно в реестре.</span><span class="sxs-lookup"><span data-stu-id="321f1-214">To set startup parameters permanently, set them in the registry.</span></span>

<span data-ttu-id="321f1-215">Для каждой службы Windows создается запись в разделе реестра **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services**.</span><span class="sxs-lookup"><span data-stu-id="321f1-215">Each Windows service has a registry entry under the **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** subkey.</span></span> <span data-ttu-id="321f1-216">Для хранения информации, к которой может обращаться ваша служба, в разделе службы можно использовать подраздел **Parameters**.</span><span class="sxs-lookup"><span data-stu-id="321f1-216">Under each service's subkey, use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="321f1-217">Файлы конфигурации приложения для службы Windows можно использовать так же, как и для программ других типов.</span><span class="sxs-lookup"><span data-stu-id="321f1-217">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="321f1-218">Пример кода см. в разделе <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="321f1-218">For sample code, see <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span></span>

### <a name="to-add-startup-parameters"></a><span data-ttu-id="321f1-219">Добавление параметров запуска</span><span class="sxs-lookup"><span data-stu-id="321f1-219">To add startup parameters</span></span>

1. <span data-ttu-id="321f1-220">Выберите файл **Program.cs** или **MyNewService.Designer.vb**, а затем в контекстном меню выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="321f1-220">Select **Program.cs**, or **MyNewService.Designer.vb**, then choose **View Code** from the shortcut menu.</span></span> <span data-ttu-id="321f1-221">Измените код метода `Main`, добавив входной параметр, который будет передаваться в конструктор службы:</span><span class="sxs-lookup"><span data-stu-id="321f1-221">In the `Main` method, change the code to add an input parameter and pass it to the service constructor:</span></span>

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
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewService(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. <span data-ttu-id="321f1-222">В файле **MyNewService.cs** или **MyNewService.vb** измените конструктор `MyNewService` для обработки входного параметра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="321f1-222">In **MyNewService.cs**, or **MyNewService.vb**, change the `MyNewService` constructor to process the input parameter as follows:</span></span>

   ```csharp
   using System.Diagnostics;

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

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

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
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="321f1-223">Этот код задает имя источника события и журнала в соответствии с указанными пользователем параметрами запуска.</span><span class="sxs-lookup"><span data-stu-id="321f1-223">This code sets the event source and log name according to the startup parameters that the user supplies.</span></span> <span data-ttu-id="321f1-224">Если аргументы не заданы, используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="321f1-224">If no arguments are supplied, it uses default values.</span></span>

3. <span data-ttu-id="321f1-225">Чтобы задать аргументы командной строки, добавьте следующий код в класс `ProjectInstaller` в файле **ProjectInstaller.cs** или **ProjectInstaller.vb**:</span><span class="sxs-lookup"><span data-stu-id="321f1-225">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in **ProjectInstaller.cs**, or **ProjectInstaller.vb**:</span></span>

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

   <span data-ttu-id="321f1-226">Как правило, это значение представляет собой полный путь к исполняемому файлу службы Windows.</span><span class="sxs-lookup"><span data-stu-id="321f1-226">Typically, this value contains the full path to the executable for the Windows service.</span></span> <span data-ttu-id="321f1-227">Для правильного запуска службы пользователь должен заключить путь и каждый параметр в кавычки.</span><span class="sxs-lookup"><span data-stu-id="321f1-227">For the service to start up correctly, the user must supply quotation marks for the path and each individual parameter.</span></span> <span data-ttu-id="321f1-228">Чтобы изменить параметры запуска службы Windows, пользователь может настроить параметры в разделе реестра **ImagePath**.</span><span class="sxs-lookup"><span data-stu-id="321f1-228">A user can change the parameters in the **ImagePath** registry entry to change the startup parameters for the Windows service.</span></span> <span data-ttu-id="321f1-229">Однако лучше изменять их программными средствами и создать для пользователей удобный интерфейс для этой возможности, например в виде программы управления или настройки.</span><span class="sxs-lookup"><span data-stu-id="321f1-229">However, a better way is to change the value programmatically and expose the functionality in a user-friendly way, such as by using a management or configuration utility.</span></span>


## <a name="build-the-service"></a><span data-ttu-id="321f1-230">Сборка службы</span><span class="sxs-lookup"><span data-stu-id="321f1-230">Build the service</span></span>

1. <span data-ttu-id="321f1-231">В **обозревателе решений** выберите пункт **Свойства** в контекстном меню проекта **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="321f1-231">In **Solution Explorer**, choose **Properties** from the shortcut menu for the **MyNewService** project.</span></span>

   <span data-ttu-id="321f1-232">Отобразятся страницы свойств для проекта.</span><span class="sxs-lookup"><span data-stu-id="321f1-232">The property pages for your project appear.</span></span>

2. <span data-ttu-id="321f1-233">На вкладке **Приложение** в списке **Автоматически запускаемый объект** выберите **MyNewService.Program** (или **Sub Main** для проекта Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="321f1-233">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**, or **Sub Main** for Visual Basic projects.</span></span>

3. <span data-ttu-id="321f1-234">Чтобы выполнить сборку проекта, в **обозревателе решений** выберите в контекстном меню проекта пункт **Сборка** (или нажмите клавиши **CTRL**+**SHIFT**+**B**).</span><span class="sxs-lookup"><span data-stu-id="321f1-234">To build the project, in **Solution Explorer**, choose **Build** from the shortcut menu for your project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="321f1-235">Установка службы</span><span class="sxs-lookup"><span data-stu-id="321f1-235">Install the service</span></span>

<span data-ttu-id="321f1-236">После создания службы Windows ее можно установить.</span><span class="sxs-lookup"><span data-stu-id="321f1-236">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="321f1-237">Чтобы установить службу Windows, необходимо иметь разрешения администратора на том компьютере, где выполняется установка.</span><span class="sxs-lookup"><span data-stu-id="321f1-237">To install a Windows service, you must have administrator credentials on the computer where it's installed.</span></span>

1. <span data-ttu-id="321f1-238">Откройте [Командную строку разработчика Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="321f1-238">Open [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) with administrative credentials.</span></span> <span data-ttu-id="321f1-239">В меню **Пуск** Windows выберите в папке Visual Studio элемент **Командная строка разработчика для VS 2017**, а затем в контекстном меню последовательно выберите **Дополнительно** > **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="321f1-239">From the Windows **Start** menu, select **Developer Command Prompt for VS 2017** in the Visual Studio folder, then select **More** > **Run as Administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="321f1-240">В окне **Командная строка разработчика для Visual Studio** перейдите к папке, которая содержит выходные данные проекта (по умолчанию это подкаталог *\bin\Debug* проекта).</span><span class="sxs-lookup"><span data-stu-id="321f1-240">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output (by default, the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="321f1-241">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="321f1-241">Enter the following command:</span></span>

    ```shell
    installutil MyNewService.exe
    ```

    <span data-ttu-id="321f1-242">Если служба установлена успешно, команда сообщит об успешном выполнении.</span><span class="sxs-lookup"><span data-stu-id="321f1-242">If the service installs successfully, the command reports success.</span></span> 

    <span data-ttu-id="321f1-243">Если система не может найти файл *installutil.exe*, убедитесь в том, что он есть на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="321f1-243">If the system can't find *installutil.exe*, make sure that it exists on your computer.</span></span> <span data-ttu-id="321f1-244">Это средство устанавливается вместе с платформой .NET Framework в папке *%windir%\Microsoft.NET\Framework[64]\\&lt;версия платформы&gt;*.</span><span class="sxs-lookup"><span data-stu-id="321f1-244">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt;*.</span></span> <span data-ttu-id="321f1-245">Например, для 64-разрядной версии по умолчанию используется путь *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="321f1-245">For example, the default path for the 64-bit version is *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="321f1-246">Если процесс **installutil.exe** завершается сбоем, найдите причину в журнале установки.</span><span class="sxs-lookup"><span data-stu-id="321f1-246">If the **installutil.exe** process fails, check the install log to find out why.</span></span> <span data-ttu-id="321f1-247">По умолчанию журнал находится в той же папке, что и исполняемый файл службы.</span><span class="sxs-lookup"><span data-stu-id="321f1-247">By default, the log is in the same folder as the service executable.</span></span> <span data-ttu-id="321f1-248">Установка может завершиться сбоем по указанным ниже причинам.</span><span class="sxs-lookup"><span data-stu-id="321f1-248">The installation can fail if:</span></span> 
    - <span data-ttu-id="321f1-249">Класс <xref:System.ComponentModel.RunInstallerAttribute> отсутствует в классе `ProjectInstaller`.</span><span class="sxs-lookup"><span data-stu-id="321f1-249">The <xref:System.ComponentModel.RunInstallerAttribute> class isn't present on the `ProjectInstaller` class.</span></span>
    -  <span data-ttu-id="321f1-250">Значение атрибута отличается от `true`.</span><span class="sxs-lookup"><span data-stu-id="321f1-250">The attribute isn't set to `true`.</span></span> 
    - <span data-ttu-id="321f1-251">Класс `ProjectInstaller` не определен как `public`.</span><span class="sxs-lookup"><span data-stu-id="321f1-251">The `ProjectInstaller` class isn't defined as `public`.</span></span>

<span data-ttu-id="321f1-252">Дополнительные сведения см. в разделе [Как Установка и удаление служб](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="321f1-252">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="321f1-253">Запуск и выполнение службы</span><span class="sxs-lookup"><span data-stu-id="321f1-253">Start and run the service</span></span>

1. <span data-ttu-id="321f1-254">В Windows откройте классическое приложение **Службы**.</span><span class="sxs-lookup"><span data-stu-id="321f1-254">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="321f1-255">Нажмите клавиши **Windows**+**R**, чтобы открыть окно **Выполнить**, введите *services.msc* и нажмите клавишу **ВВОД** или кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="321f1-255">Press **Windows**+**R** to open the **Run** box, enter *services.msc*, and then press **Enter** or select **OK**.</span></span>

     <span data-ttu-id="321f1-256">Заданное вами отображаемое имя службы отобразится в списке **Службы**, представленном в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="321f1-256">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService в окне "Службы".](media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="321f1-258">Чтобы запустить службу, в ее контекстном меню выберите пункт **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="321f1-258">To start the service, choose **Start** from the service's shortcut menu.</span></span>

3. <span data-ttu-id="321f1-259">Чтобы остановить службу, в ее контекстном меню выберите пункт **Остановить**.</span><span class="sxs-lookup"><span data-stu-id="321f1-259">To stop the service, choose **Stop** from the service's shortcut menu.</span></span>

4. <span data-ttu-id="321f1-260">Для запуска и остановки службы в командной строке можно использовать команды **net start &lt;имя службы&gt;** и **net stop &lt;имя службы&gt;** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="321f1-260">(Optional) From the command line, use the commands **net start &lt;service name&gt;** and **net stop &lt;service name&gt;** to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="321f1-261">Проверка журнала событий для службы</span><span class="sxs-lookup"><span data-stu-id="321f1-261">Verify the event log output of your service</span></span>

1. <span data-ttu-id="321f1-262">В Windows откройте классическое приложение **Просмотр событий**.</span><span class="sxs-lookup"><span data-stu-id="321f1-262">In Windows, open the **Event Viewer** desktop app.</span></span> <span data-ttu-id="321f1-263">Введите строку *Просмотр событий* в поле поиска Windows и выберите **Просмотр событий** в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="321f1-263">Enter *Event Viewer* in the Windows search bar, and then select **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="321f1-264">В Visual Studio доступ к журналам событий можно получить, открыв **обозреватель сервера** в меню **Вид** (или нажав клавиши **CTRL**+**ALT**+**S**) и развернув узел **Журналы событий** для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="321f1-264">In Visual Studio, you can access event logs by opening **Server Explorer** from the **View** menu (or press **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="321f1-265">В **средстве просмотра событий** разверните узел **Журналы приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="321f1-265">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="321f1-266">Найдите в списке элемент **MyNewLog** (или **MyLogFile1**, если вы использовали процедуру добавления аргументов командной строки) и разверните его.</span><span class="sxs-lookup"><span data-stu-id="321f1-266">Locate the listing for **MyNewLog** (or **MyLogFile1** if you followed the procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="321f1-267">Вы увидите записи для двух действий (запуск и остановка), которые выполнила ваша служба.</span><span class="sxs-lookup"><span data-stu-id="321f1-267">You should see the entries for the two actions (start and stop) that your service performed.</span></span>

     ![Просмотр записей в журнале событий с помощью компонента "Просмотр событий"](media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a><span data-ttu-id="321f1-269">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="321f1-269">Clean up resources</span></span>

<span data-ttu-id="321f1-270">Если приложение службы Windows вам больше не нужно, его можно удалить.</span><span class="sxs-lookup"><span data-stu-id="321f1-270">If you no longer need the Windows service app, you can remove it.</span></span> 

1. <span data-ttu-id="321f1-271">Откройте **Командную строку разработчика Visual Studio** с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="321f1-271">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="321f1-272">В окне **Командная строка разработчика для Visual Studio** перейдите к папке, которая содержит выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="321f1-272">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="321f1-273">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="321f1-273">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="321f1-274">Если служба удалена успешно, команда сообщит об этом.</span><span class="sxs-lookup"><span data-stu-id="321f1-274">If the service uninstalls successfully, the command reports that your service was successfully removed.</span></span> <span data-ttu-id="321f1-275">Дополнительные сведения см. в разделе [Как Установка и удаление служб](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="321f1-275">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="321f1-276">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="321f1-276">Next steps</span></span>

<span data-ttu-id="321f1-277">Теперь, после создания службы, можно выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="321f1-277">Now that you've created the service, you can:</span></span>

- <span data-ttu-id="321f1-278">Создайте автономную программу установки, с помощью которой другие пользователи могут устанавливать вашу службу Windows.</span><span class="sxs-lookup"><span data-stu-id="321f1-278">Create a standalone setup program for others to use to install your Windows service.</span></span> <span data-ttu-id="321f1-279">Создать установщик для службы Windows можно с помощью [набора инструментов WiX](http://wixtoolset.org/).</span><span class="sxs-lookup"><span data-stu-id="321f1-279">Use the [WiX Toolset](http://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="321f1-280">Другие идеи можно почерпнуть в статье [о создании пакета установщика](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="321f1-280">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

- <span data-ttu-id="321f1-281">Изучите возможности компонента <xref:System.ServiceProcess.ServiceController>, который позволяет отправлять команды в установленную службу.</span><span class="sxs-lookup"><span data-stu-id="321f1-281">Explore the <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

- <span data-ttu-id="321f1-282">Для создания журнала событий при установке приложения, а не во время его запуска, можно воспользоваться установщиком.</span><span class="sxs-lookup"><span data-stu-id="321f1-282">Instead of creating the event log when the application runs, use an installer to create an event log when you install the application.</span></span> <span data-ttu-id="321f1-283">В этом случае журнал событий удаляется установщиком при удалении приложения.</span><span class="sxs-lookup"><span data-stu-id="321f1-283">The event log is deleted by the installer when you uninstall the application.</span></span> <span data-ttu-id="321f1-284">Для получения дополнительной информации см. <xref:System.Diagnostics.EventLogInstaller>.</span><span class="sxs-lookup"><span data-stu-id="321f1-284">For more information, see <xref:System.Diagnostics.EventLogInstaller>.</span></span>

## <a name="see-also"></a><span data-ttu-id="321f1-285">См. также</span><span class="sxs-lookup"><span data-stu-id="321f1-285">See also</span></span>

- [<span data-ttu-id="321f1-286">Приложения служб Windows</span><span class="sxs-lookup"><span data-stu-id="321f1-286">Windows service applications</span></span>](index.md)
- [<span data-ttu-id="321f1-287">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="321f1-287">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="321f1-288">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="321f1-288">How to: Debug Windows service applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="321f1-289">Службы (Windows)</span><span class="sxs-lookup"><span data-stu-id="321f1-289">Services (Windows)</span></span>](/windows/desktop/Services/services)
