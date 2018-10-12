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
manager: douge
ms.openlocfilehash: 27acdac5d34b96dd04fec1bb763edec9077ff928
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46493611"
---
# <a name="walkthrough-create-a-windows-service-app"></a>Пошаговое руководство. Создание приложения службы Windows

Из этой статьи вы узнаете, как создать в Visual Studio простое приложение службы Windows, которое записывает сообщения в журнал событий.

## <a name="create-a-service"></a>Создание службы

Для начала создайте проект и настройте значения, необходимые для правильной работы службы.

1. В Visual Studio в строке меню последовательно выберите **Файл** > **Создать** > **Проект** (или нажмите сочетание клавиш **CTRL**+**SHIFT**+**N**), чтобы открыть диалоговое окно **Новый проект**.

2. Найдите и выберите шаблон проекта **Служба Windows**. Разверните элементы **Установленные** > [**Visual C#** или **Visual Basic**] > **Windows Desktop** или введите строку **Служба Windows** в поле поиска в правом верхнем углу.

   ![Шаблон приложения Windows в диалоговом окне нового проекта Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > Если вы не видите здесь шаблон **Служба Windows**, попробуйте установить рабочую нагрузку **Разработка классических приложений .NET**. В диалоговом окне **Новый проект** щелкните ссылку с текстом **Открыть Visual Studio Installer** в левом нижнем углу. В окне **Visual Studio Installer** выберите рабочую нагрузку **Разработка классических приложений .NET** и щелкните **Изменить**.

3. Присвойте проекту имя **MyNewService** и щелкните **ОК**.

   Этот шаблон проекта содержит класс компонента с именем `Service1`, наследуемый от <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. В нем собран основной служебный код, в том числе код для запуска службы.

## <a name="rename-the-service"></a>Переименование службы

Измените имя службы с **Service1** на **MyNewService**.

1. В представлении **Конструктор** для файла Service1.cs (или Service1.vb) щелкните ссылку **перехода к представлению кода**. Щелкните **Service1** правой кнопкой мыши и выберите в контекстном меню действие **Переименовать**. Введите **MyNewService** и нажмите клавишу **ВВОД** или щелкните **Применить**.

2. В окне **Свойства** для **Service1.cs [Проект]** или **Service1.vb [Проект]**, измените значение **ServiceName** на **MyNewService**.

3. В **обозревателе решений** переименуйте **Service1.cs** в **MyNewService.cs** (или **Service1.vb** в **MyNewService.vb**).

## <a name="add-features-to-the-service"></a>Добавление компонентов в службу

В этом разделе к службе Windows будет добавлен настраиваемый журнал событий. Журналы событий никак не связаны со службами Windows. Компонент <xref:System.Diagnostics.EventLog> используется здесь в качестве примера типа компонента, который можно добавить в службу Windows.

### <a name="add-custom-event-log-functionality"></a>Добавление возможности работы с настраиваемым журналом событий

1. В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Конструктор представлений**.

2. Из раздела **Компоненты** **панели элементов**перетащите в окно конструктора компонент <xref:System.Diagnostics.EventLog> .

3. В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Просмотр кода**.

4. Измените конструктор, чтобы определить настраиваемый журнал событий:

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

### <a name="define-what-occurs-when-the-service-starts"></a>Определение действий при запуске службы

В редакторе кода найдите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, который был автоматически переопределен при создании проекта. Добавьте строку кода, с помощью которой запись сохраняется в журнале событий при запуске службы:

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

Приложение службы предполагает длительное время выполнения, поэтому оно обычно опрашивает или отслеживает что-либо в системе. Отслеживание настраивается в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> . Тем не менее, метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> не отвечает за фактическое отслеживание. После начала работы службы метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> должен возвращать управление операционной системе. Он не должен уходить в бесконечный цикл или блокироваться. Для простого механизма опроса можно использовать компонент <xref:System.Timers.Timer?displayProperty=nameWithType> следующим образом: в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> задайте параметры компонента, а затем установите для свойства <xref:System.Timers.Timer.Enabled%2A> значение `true`. Таймер периодическую генерирует события в вашем коде, при возникновении которых служба сможет выполнять отслеживание. Для этого можно использовать следующий код:

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

Добавьте в класс переменную-член. Она содержит идентификатор следующего события, которое сохраняется в журнале событий.

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

Добавьте новый метод для обработки этого события таймера:

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

Задачи можно выполнять с помощью фоновых рабочих потоков, а не выполнять всю работу в основном потоке. Дополнительные сведения см. в разделе <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.

### <a name="define-what-occurs-when-the-service-is-stopped"></a>Определение действий при остановке службы

Добавьте в метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A> строку кода, с помощью которой запись сохраняется в журнале событий при остановке службы:

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>Определение других действий для службы

Вы можете переопределить методы <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> и <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>, добавив дополнительные процессы обработки. Следующий код показывает, как можно переопределить метод <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

Когда служба Windows устанавливается классом <xref:System.Configuration.Install.Installer> , должны выполняться некоторые специализированные действия. С помощью Visual Studio для службы Windows можно специально создавать подобные установщики и добавлять их в проект.

## <a name="set-service-status"></a>Установка состояния службы

Службы сообщают о своем состоянии диспетчеру управления службами, чтобы пользователи могли определить, работает ли служба корректно. По умолчанию, службы, которые наследуют из <xref:System.ServiceProcess.ServiceBase> , сообщают ограниченный набор параметров состояния, включая "Остановлена", Приостановлена" и "Выполняется". Если служба сразу не запускается, то может быть полезно обеспечить индикацию состояния "Ожидание запуска". Параметры состояния ожидания запуска и ожидания остановки также можно реализовать путем добавления кода, вызывающего функцию Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).

Чтобы реализовать состояние ожидания службы, сделайте следующее:

1. Добавьте оператор `using` или объявление `Imports` в пространство имен <xref:System.Runtime.InteropServices?displayProperty=nameWithType> в файле MyNewService.cs или MyNewService.vb.

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. Добавьте следующий код в файл MyNewService.cs для объявления значений `ServiceState` и добавления структуры для состояния, которая будет использоваться при вызове неуправляемого кода:

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

3. Теперь в классе `MyNewService` объявите [функцию SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) с помощью вызова [неуправляемого кода](../interop/consuming-unmanaged-dll-functions.md):

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. Для реализации состояния ожидания запуска добавьте следующий код в начало метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :

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

5. Для присвоения состоянию значения "Запуск" добавьте код в конце метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .

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

6. (Необязательно) Повторите данную процедуру для метода <xref:System.ServiceProcess.ServiceBase.OnStop%2A> .

> [!NOTE]
> [Диспетчер служб](/windows/desktop/Services/service-control-manager) использует члены `dwWaitHint` и `dwCheckpoint` [структуры SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status), чтобы определить время, в течение которого нужно ожидать запуск или завершение работы службы Windows. Если ваши методы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> выполняются долго, ваша служба может запросить больше времени, повторно вызвав функцию [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) с увеличенным значением `dwCheckPoint`.

## <a name="add-installers-to-the-service"></a>Добавление установщиков в службу

Чтобы получить возможность запустить службу Windows, выполните установку, при которой служба будет зарегистрирована в диспетчере служб. В проект можно добавить установщики, которые обрабатывают  сведения о регистрации.

1. В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Конструктор представлений**.

2. Щелкните фон конструктора, чтобы выбрать саму службу, а не какой-либо из ее элементов.

3. Откройте контекстное меню в окне конструктора (в случае применения указательного устройства щелкните правой кнопкой мыши внутри окна) и нажмите **Добавить установщик**.

   По умолчанию в проект добавляется класс компонента, содержащий два установщика. Компоненту присваивается имя **ProjectInstaller**, а содержащиеся в нем установщики предназначаются для установки службы и связанного со службой процесса.

4. В представлении **Конструктор** для **ProjectInstaller**выберите **serviceInstaller1** для проекта Visual C# или **ServiceInstaller1** для проекта Visual Basic.

5. Убедитесь, что в окне **Свойства** свойство <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> имеет значение **MyNewService**.

6. Введите для свойства **Описание** какой нибудь текст, например, "Пример службы". Этот текст отображается в окне «Службы» и помогает пользователю идентифицировать службу, а также и понять, для чего она используется.

7. Введите для свойства <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> текст, который будет отображаться в окне «Службы» в столбце **Имя** . Например, можно ввести «Отображаемое имя MyNewService». Это имя может отличаться от значения свойства <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , которое представляет собой имя, используемое в системе (например, если для запуска своей службы вы используете команду `net start` ).

8. Задайте для свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение <xref:System.ServiceProcess.ServiceStartMode.Automatic>.

     ![Свойства установщика для службы Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")

9. В конструкторе щелкните **serviceProcessInstaller1** для проекта Visual C# или **ServiceProcessInstaller1** для проекта Visual Basic. Задайте для свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> значение <xref:System.ServiceProcess.ServiceAccount.LocalSystem>. Это позволит установить и запускать службу от имени локальной системной учетной записи.

    > [!IMPORTANT]
    > У учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalSystem> имеется множество разрешений, включая разрешение на запись в журнал событий. Эту учетную запись следует использовать с осторожностью, поскольку это может увеличить риск атак с помощью вредоносных программ. Для других задач следует рассмотреть возможность использования учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalService>, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя. В этом примере произойдет ошибка, если вы попытаетесь использовать учетную запись <xref:System.ServiceProcess.ServiceAccount.LocalService>, так как для нее требуется разрешение на запись в журнал событий.

Дополнительные сведения об установщиках см. в статье [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).

## <a name="optional-set-startup-parameters"></a>Установка параметров запуска (необязательно)

Служба Windows, как и любой другой исполняемый файл, может принимать аргументы командной строки или параметры запуска. При добавлении кода в параметры запуска процесса пользователи могут запускать свою службу со своими собственными специальными параметрами с помощью окна "Службы" на панели управления Windows. Тем не менее, эти параметры запуска не сохраняются при следующем запуске службы. Чтобы окончательно задать параметры запуска, их можно указать в реестре, как показано в данной процедуре.

> [!NOTE]
> Прежде чем добавить параметры запуска, убедитесь, что это наилучший способ передачи информации в службу. Хотя параметры запуска просты при использовании и синтаксическом анализе, и пользователи могут легко их переопределять, для пользователей их поиск и применение может оказаться затрудненным (без документации). Как правило, если для вашей службы требуется всего несколько параметров запуска, то целесообразно использовать реестр или файл конфигурации. Для каждой службы Windows создается запись в разделе реестра **HKLM\System\CurrentControlSet\services**. Для хранения информации, к которой может обращаться ваша служба, в разделе ключа службы можно использовать подраздел **Параметры** . Файлы конфигурации приложения для службы Windows можно использовать так же, как и для программ других типов. Пример кода см. в разделе <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.

Чтобы добавить параметры запуска, сделайте следующее:

1. Добавьте в метод `Main` файла Program.cs или MyNewService.Designer.vb входной параметр, который будет передавать конструктор службы.

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

2. Измените конструктор `MyNewService` следующим образом:

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

   Этот код задает имя источника события и журнала в соответствии с заданными параметрами запуска или использует значения по умолчанию, если никакие аргументы не заданы.

3. Чтобы задать аргументы командной строки, добавьте следующий код в класс `ProjectInstaller` в файле ProjectInstaller.cs или ProjectInstaller.vb:

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

   С помощью этого кода изменяется раздел реестра **ImagePath**, который обычно содержит полный путь к исполняемому файлу для службы Windows, путем добавления значений параметров по умолчанию. Для корректного запуска службы путь (а также каждый параметр) должен быть заключен в кавычки. Чтобы изменить параметры запуска службы Windows, пользователи могут изменять параметры в разделе реестра **ImagePath**. Но лучше изменять их программными средствами и создать для пользователей удобный интерфейс для этой возможности (например, в программе управления или настройки).

## <a name="build-the-service"></a>Сборка службы

1. В **Обозревателе решений**откройте контекстное меню для своего проекта и выберите **Свойства**.

   Отобразятся страницы свойств для проекта.

2. На вкладке **Приложение** в списке **Автоматически запускаемый объект** выберите **MyNewService.Program**.

3. В **обозревателе решений** откройте контекстное меню проекта и щелкните **Сборка**, чтобы выполнить компиляцию проекта (или нажмите сочетание клавиш **CTRL**+**SHIFT**+**B**).

## <a name="install-the-service"></a>Установка службы

После создания службы Windows ее можно установить. Чтобы установить службу Windows, необходимо иметь разрешения администратора на том компьютере, где выполняется установка.

1. Откройте **Командную строку разработчика Visual Studio** с учетными данными администратора. Если вы используете мышь, щелкните правой кнопкой элемент **Developer Command Prompt for VS 2017** (Командная строка разработчика для VS 2017) в меню "Пуск" Windows и последовательно выберите **Дополнительно** > **Запуск от имени администратора**.

2. В окне **Командной строки разработчика** перейдите к папке, которая содержит выходные данные проекта (по умолчанию это подкаталог *\bin\Debug* в проекте).

3. Введите следующую команду:

    ```shell
    installutil.exe MyNewService.exe
    ```

    Если служба установлена успешно, **installutil.exe** сообщит об успешном выполнении. Если система не может найти файл **InstallUtil.exe**, убедитесь, что он есть на вашем компьютере. Этот инструмент устанавливается вместе с платформой .NET Framework в папку *%windir%\Microsoft.NET\Framework[64]\\[версия платформы]*. Например, для 32-разрядной версии по умолчанию используется путь *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.

    Если процесс **installutil.exe** сообщает о сбое, найдите причину в журнале установки. По умолчанию журнал находится в той же папке, что и исполняемый файл службы. Установка может завершиться сбоем, если класс <xref:System.ComponentModel.RunInstallerAttribute> отсутствует в классе `ProjectInstaller`, значение атрибута отличается от **true** или класс `ProjectInstaller` не имеет атрибута **public**.

Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="start-and-run-the-service"></a>Запуск и выполнение службы

1. В Windows откройте классическое приложение **Службы**. Нажмите сочетание клавиш **Windows**+**R**, чтобы открыть окно **Запуск**, введите имя файла **services.msc** и нажмите клавишу **ВВОД** или щелкните **ОК**.

     Заданное вами отображаемое имя службы отобразится в списке **Службы**, представленном в алфавитном порядке.

     ![MyNewService в окне "Службы".](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. В окне **Службы** откройте контекстное меню службы и нажмите **Пуск**.

3. Чтобы остановить работу службы, снова откройте контекстное меню службы и нажмите **Стоп**.

4. Для запуска и остановки службы из командной строки можно использовать команды `net start ServiceName` и `net stop ServiceName` (необязательно).

### <a name="verify-the-event-log-output-of-your-service"></a>Проверка журнала событий для службы

1. Чтобы открыть компонент **Просмотр событий**, начните вводить строку **Просмотр событий** в поле поиска на панели задач Windows и выберите **Просмотр событий** в результатах поиска.

   > [!TIP]
   > В Visual Studio доступ к журналам событий можно получить, открыв **обозреватель сервера** (сочетание клавиш **CTRL**+**ALT**+**S**) и развернув узел **Журналы событий** для локального компьютера.

2. В **средстве просмотра событий** разверните узел **Журналы приложений и служб**.

3. Найдите в списке элемент **MyNewLog** (или **MyLogFile1**, если вы использовали необязательную процедуру с аргументами командной строки) и разверните его. Вы увидите записи для двух действий (запуск и остановка), которые выполнила ваша служба.

     ![Просмотр записей в журнале событий с помощью компонента "Просмотр событий"](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a>Удаление службы

1. Откройте **Командную строку разработчика Visual Studio** с учетными данными администратора.

2. В окне командной строки перейдите к папке, которая содержит выходные данные проекта.

3. Введите следующую команду:

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   Если служба удалена успешно, **installutil.exe** сообщит об этом. Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="next-steps"></a>Следующие шаги

Завершив создание службы, вы можете создать автономную программу установки, с помощью которой другие пользователи будут устанавливать вашу службу Windows. ClickOnce не поддерживает службы Windows, но вы можете создать установщик службы Windows с помощью [набора средств WiX](http://wixtoolset.org/). Другие идеи можно почерпнуть в статье [о создании пакета установщика](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

Также изучите возможности компонента <xref:System.ServiceProcess.ServiceController>, который позволяет отправлять команды в установленную службу.

Для создания журнала событий при установке приложения можно воспользоваться установщиком, а не создавать журнал после запуска приложения. Кроме того, в этом случае журнал событий будет удален установщиком при удалении приложения. Дополнительные сведения см. на странице <xref:System.Diagnostics.EventLogInstaller> .

## <a name="see-also"></a>См. также

- [Приложения служб Windows](../../../docs/framework/windows-services/index.md)
- [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Практическое руководство. Отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [Службы (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
