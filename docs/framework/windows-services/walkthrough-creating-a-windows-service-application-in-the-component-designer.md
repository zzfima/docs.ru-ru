---
title: Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Service applications, walkthroughs
- Windows Service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: c33b8badcacd4e228d70f8e770d4bf27144c29eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-a-windows-service-application-in-the-component-designer"></a>Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов
В этой статье описывается процедура создания простого приложения службы Windows в Visual Studio, которое записывает сообщения в журнал событий. Ниже приведены основные шаги, которые необходимо выполнить для создания и использования службы.  
  
1.  [Создание службы](#BK_CreateProject) с помощью шаблона проекта **службы Windows** и выполните необходимую настройку. Этот шаблон создает класс, производный от класса <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>, и формирует основную часть кода службы, например код, необходимый для ее запуска.  
  
2.  [Добавление компонентов в службу](#BK_WriteCode) для процедур <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> и переопределите все прочие методы по мере необходимости.  
  
3.  [Установка состояния службы](#BK_SetStatus). По умолчанию службы, созданные с помощью метода <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>, реализуют только подмножество доступных флагов состояния. Если операции запуска, приостановки или остановки службы выполняются медленно, то можно реализовать значения состояния, например, "Ожидание запуска" или "Ожидание остановки", которые указывают, что служба выполняет операцию.  
  
4.  [Добавление установщиков в службу](#BK_AddInstallers) для приложения службы.  
  
5.  (Необязательно.) [Установка параметров запуска](#BK_StartupParameters), задайте аргументы запуска по умолчанию и разрешите пользователям переопределять параметры по умолчанию, когда они запускают вашу службу вручную.  
  
6.  [Создание службы](#BK_Build).  
  
7.  [Установка службы](#BK_Install) на локальном компьютере.  
  
8.  Откройте диспетчер управления службами Windows и [Запуск и выполнение службы](#BK_StartService).  
  
9. [Удаление службы Windows](#BK_Uninstall).  
  
> [!WARNING]
>  Шаблон проекта служб Windows, необходимый для этого пошагового руководства, недоступен в выпуске Visual Studio Express.  
  
 [!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]  
  
<a name="BK_CreateProject"></a>   
## <a name="creating-a-service"></a>Создание службы  
 Для начала необходимо создать проект и установить значения, необходимые для правильной работы службы.  
  
#### <a name="to-create-and-configure-your-service"></a>Чтобы создать и настроить службу, выполните следующие действия:  
  
1.  В Visual Studio в строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
2.  В списке шаблонов проектов Visual Basic или Visual C# выберите **Служба Windows**и присвойте проекту имя **MyNewService**. Нажмите кнопку **ОК**.  
  
     Шаблон проекта автоматически добавит класс компонента с именем `Service1`, наследуемый от <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.  
  
3.  В меню **Правка** выберите **Найти и заменить**, **Найти в файлах** (сочетание клавиш: Ctrl+Shift+F). Замените все вхождения службы `Service1` на `MyNewService`. Вы найдете экземпляры в Service1.cs, Program.cs и Service1.Designer.cs (или их эквивалентах .vb).  
  
4.  В окне **Свойства** для **Service1.cs [Design]** или **Service1.vb [Design]** установите для <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> и свойства **(Имя)** для `Service1` значение **MyNewService**, если это еще не сделано.  
  
5.  В обозревателе решений переименуйте **Service1.cs** в **MyNewService.cs**или **Service1.vb** в **MyNewService.vb**.  
  
<a name="BK_WriteCode"></a>   
## <a name="adding-features-to-the-service"></a>Добавление компонентов в службу  
 В этом разделе к службе Windows будет добавлен настраиваемый журнал событий. Журналы событий никак не связаны со службами Windows. Компонент <xref:System.Diagnostics.EventLog> используется здесь как пример типа компонента, который можно добавить в службу Windows.  
  
#### <a name="to-add-custom-event-log-functionality-to-your-service"></a>Чтобы добавить к службе функцию работы с настраиваемым журналом событий, выполните следующие действия:  
  
1.  В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Конструктор представлений**.  
  
2.  Из раздела **Компоненты** **панели элементов**перетащите в окно конструктора компонент <xref:System.Diagnostics.EventLog> .  
  
3.  В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Просмотр кода**.  
  
4.  Добавьте объявление для объекта **eventLog** в классе `MyNewService` сразу после строки, которая объявляет переменную `components` :  
  
     [!code-csharp[VbRadconService#16](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#16)]
     [!code-vb[VbRadconService#16](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#16)]  
  
5.  Добавьте или измените конструктор, чтобы определить настраиваемый журнал событий:  
  
     [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
     [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]  
  
#### <a name="to-define-what-occurs-when-the-service-starts"></a>Чтобы задать поведение службы при запуске, выполните следующие действия:  
  
-   В редакторе кода найдите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> , который был автоматически переопределен при создании проекта, и замените код следующим содержимым. При этом при запуске службы в журнал событий будет добавлена запись:  
  
     [!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
     [!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]  
  
     Приложение службы предполагает длительное время выполнения, поэтому оно обычно опрашивает или отслеживает что-либо в системе. Отслеживание настраивается в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> . Тем не менее, метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> не отвечает за фактическое отслеживание. После начала работы службы метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> должен возвращать управление операционной системе. Он не должен уходить в бесконечный цикл или блокироваться. Для простого механизма опроса можно использовать компонент <xref:System.Timers.Timer?displayProperty=nameWithType> следующим образом: в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> задайте параметры компонента, а затем установите для свойства <xref:System.Timers.Timer.Enabled%2A> значение `true`. Таймер периодическую генерирует события в вашем коде, при возникновении которых служба сможет выполнять отслеживание. Для этого можно использовать следующий код:  
  
    ```csharp  
    // Set up a timer to trigger every minute.  
    System.Timers.Timer timer = new System.Timers.Timer();  
    timer.Interval = 60000; // 60 seconds  
    timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);  
    timer.Start();  
    ```  
  
    ```vb  
    ' Set up a timer to trigger every minute.  
    Dim timer As System.Timers.Timer = New System.Timers.Timer()  
    timer.Interval = 60000 ' 60 seconds  
    AddHandler timer.Elapsed, AddressOf Me.OnTimer  
    timer.Start()  
    ```  
     Добавьте переменную-член в класс. Он будет содержать идентификатор следующего события для записи в журнал событий.

    ```csharp
    private int eventId = 1;
    ```

    ```vb
    Private eventId As Integer = 1
    ```

     Добавьте код для обработки события таймера:  
  
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
  
     Задачи можно выполнять с помощью фоновых рабочих потоков, а не выполнять всю работу в основном потоке. См. пример на справочной странице <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.  
  
#### <a name="to-define-what-occurs-when-the-service-is-stopped"></a>Чтобы задать поведение службы при остановке, выполните следующие действия:  
  
-   Замените код для метода <xref:System.ServiceProcess.ServiceBase.OnStop%2A> на следующее. При этом при остановке службы в журнал событий будет добавлена запись:  
  
     [!code-csharp[VbRadconService#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
     [!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]  
  
 В следующем разделе можно переопределить методы <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>и <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> для выбора дополнительной обработки для своего компонента.  
  
#### <a name="to-define-other-actions-for-the-service"></a>Чтобы задать поведение службы в прочих случаях, выполните следующие действия:  
  
-   Найдите метод, который требуется для работы, и переопределите его требуемым образом.  
  
     Следующий код показывает, как можно переопределить метод <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :  
  
     [!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
     [!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]  
  
 Когда служба Windows устанавливается классом <xref:System.Configuration.Install.Installer> , должны выполняться некоторые специализированные действия. С помощью Visual Studio для службы Windows можно специально создавать подобные установщики и добавлять их в проект.  
  
<a name="BK_SetStatus"></a>   
## <a name="setting-service-status"></a>Установка состояния службы  
 Службы сообщают о своем состоянии диспетчеру управления службами, чтобы пользователи могли определить, работает ли служба корректно. По умолчанию, службы, которые наследуют из <xref:System.ServiceProcess.ServiceBase> , сообщают ограниченный набор параметров состояния, включая "Остановлена", Приостановлена" и "Выполняется". Если служба сразу не запускается, то может быть полезно обеспечить индикацию состояния "Ожидание запуска". Параметры состояния ожидания запуска и ожидания остановки также можно реализовать путем добавления кода, вызывающего функцию Windows [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx).  
  
#### <a name="to-implement-service-pending-status"></a>Реализация состояния ожидания службы  
  
1.  Добавьте оператор `using` или объявление `Imports` в пространство имен <xref:System.Runtime.InteropServices?displayProperty=nameWithType> в файле MyNewService.cs или MyNewService.vb:  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    ```  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    ```  
  
2.  Добавьте следующий код в файл MyNewService.cs для объявления значений `ServiceState` и добавления структуры для состояния, которая будет использоваться при вызове неуправляемого кода:  
  
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
  
3.  Теперь в классе `MyNewService` объявите функцию [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) с помощью вызова неуправляемого кода.  
  
    ```csharp  
    [DllImport("advapi32.dll", SetLastError=true)]  
            private static extern bool SetServiceStatus(IntPtr handle, ref ServiceStatus serviceStatus);  
    ```  
  
    ```vb  
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean  
    ```  
  
4.  Для реализации состояния ожидания запуска добавьте следующий код в начало метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :  
  
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
  
5.  Для присвоения состоянию значения "Запуск" добавьте код в конце метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .  
  
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
  
6.  (Необязательно) Повторите данную процедуру для метода <xref:System.ServiceProcess.ServiceBase.OnStop%2A> .  
  
> [!CAUTION]
>  [Диспетчера управления службами](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) использует `dwWaitHint` и `dwCheckpoint` члены [структуры SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) для определения времени ожидания для службы Windows для запуска или завершения работы. Если ваши методы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> выполняются долго, ваша служба может запросить больше времени, повторно вызвав функцию [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) с увеличенным значением `dwCheckPoint` .  
  
<a name="BK_AddInstallers"></a>   
## <a name="adding-installers-to-the-service"></a>Добавление установщиков в службу  
 Перед запуском службы Windows ее необходимо установить (при этом служба будет зарегистрирована с помощью диспетчера управления службами. В проект можно добавить установщики, которые обрабатывают  сведения о регистрации.  
  
#### <a name="to-create-the-installers-for-your-service"></a>Чтобы создать установщики для службы, выполните следующие действия:  
  
1.  В окне **Обозреватель решений**откройте контекстное меню для элемента **MyNewService.cs** или **MyNewService.vb**и выберите **Конструктор представлений**.  
  
2.  Щелкните фон конструктора, чтобы выбрать саму службу, а не какой-либо из ее элементов.  
  
3.  Откройте контекстное меню в окне конструктора (в случае применения указательного устройства щелкните правой кнопкой мыши внутри окна) и нажмите **Добавить установщик**.  
  
     По умолчанию в проект добавляется класс компонента, содержащий два установщика. Компоненту присваивается имя **ProjectInstaller**, а содержащиеся в нем установщики предназначаются для установки службы и связанного со службой процесса.  
  
4.  В представлении **Конструктор** для **ProjectInstaller**выберите **serviceInstaller1** для проекта Visual C# или **ServiceInstaller1** для проекта Visual Basic.  
  
5.  Убедитесь, что в окне **Свойства** свойство <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> имеет значение **MyNewService**.  
  
6.  Введите для свойства **Описание** какой нибудь текст, например, "Пример службы". Этот текст отображается в окне «Службы» и помогает пользователю идентифицировать службу, а также и понять, для чего она используется.  
  
7.  Введите для свойства <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> текст, который будет отображаться в окне «Службы» в столбце **Имя** . Например, можно ввести «Отображаемое имя MyNewService». Это имя может отличаться от значения свойства <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , которое представляет собой имя, используемое в системе (например, если для запуска своей службы вы используете команду `net start` ).  
  
8.  Задайте для свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение <xref:System.ServiceProcess.ServiceStartMode.Automatic>.  
  
     ![Свойства установщика для службы Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")  
  
9. В конструкторе щелкните **serviceProcessInstaller1** для проекта Visual C# или **ServiceProcessInstaller1** для проекта Visual Basic. Задайте для свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> значение <xref:System.ServiceProcess.ServiceAccount.LocalSystem>. Это приведет к установке и выполнению службы с использованием локальной учетной записи служб.  
  
    > [!IMPORTANT]
    >  У учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalSystem> имеется множество разрешений, включая разрешение на запись в журнал событий. Эту учетную запись следует использовать с осторожностью, поскольку это может увеличить риск атак с помощью вредоносных программ. Для других задач следует рассмотреть возможность использования учетной записи <xref:System.ServiceProcess.ServiceAccount.LocalService>, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя. В этом примере произойдет ошибка, если вы попытаетесь использовать учетную запись <xref:System.ServiceProcess.ServiceAccount.LocalService>, так как для нее требуется разрешение на запись в журнал событий.  
  
     Дополнительные сведения об установщиках см. в разделе [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
<a name="BK_StartupParameters"></a>   
## <a name="set-startup-parameters"></a>Установка параметров запуска  
 Служба Windows, как и любой другой исполняемый файл, может принимать аргументы командной строки или параметры запуска. При добавлении кода в параметры запуска процесса пользователи могут запускать свою службу со своими собственными специальными параметрами с помощью окна "Службы" на панели управления Windows. Тем не менее, эти параметры запуска не сохраняются при следующем запуске службы. Чтобы окончательно задать параметры запуска, их можно указать в реестре, как показано в данной процедуре.  
  
> [!NOTE]
>  Прежде чем добавить параметры запуска, убедитесь, что это наилучший способ передачи информации в службу. Хотя параметры запуска просты при использовании и синтаксическом анализе, и пользователи могут легко их переопределять, для пользователей их поиск и применение может оказаться затрудненным (без документации). Как правило, если для вашей службы требуется всего несколько параметров запуска, то целесообразно использовать реестр или файл конфигурации. Каждая служба Windows имеет запись в реестре в разделе HKLM\System\CurrentControlSet\services. Для хранения информации, к которой может обращаться ваша служба, в разделе ключа службы можно использовать подраздел **Параметры** . Файлы конфигурации приложения для службы Windows можно использовать так же, как и для программ других типов. Пример кода см. в разделе <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.  
  
#### <a name="adding-startup-parameters"></a>Добавление параметров запуска  
  
1.  В методе `Main` метода в файле Program.cs или в MyNewService.Designer.vb добавьте аргумент для командной строки:  
  
```csharp  
static void Main(string[] args)
{
    ServiceBase[] ServicesToRun = new ServiceBase[] { new MyNewService(args) };
    ServiceBase.Run(ServicesToRun);
}
```  
  
```vb
Shared Sub Main(ByVal cmdArgs() As String)
    Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
    System.ServiceProcess.ServiceBase.Run(ServicesToRun)
End Sub
```  
  
2.  Измените конструктор `MyNewService` следующим образом:  
  
```csharp  
public MyNewService(string[] args)
{
    InitializeComponent();
    string eventSourceName = "MySource";
    string logName = "MyNewLog";
    if (args.Count() > 0) 
    {
        eventSourceName = args[0];
    }
    if (args.Count() > 1)
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
  
Этот код изменяет раздел реестра **ImagePath** , который обычно содержит полный путь к исполняемому файлу для службы Windows, путем добавления значений параметров по умолчанию. Для корректного запуска службы путь (а также каждый параметр) должен быть заключен в кавычки. Для изменения параметров запуска службы Windows пользователи могут изменять параметры, заданные в разделе реестра **ImagePath** , хотя, лучше всего изменять их программно и предоставлять функциональную возможность пользователям понятным способом (например, в программе управления или настройки).  
  
<a name="BK_Build"></a>   
## <a name="building-the-service"></a>Создание службы  
  
#### <a name="to-build-your-service-project"></a>Чтобы построить проект службы, выполните следующие действия:  
  
1.  В **Обозревателе решений**откройте контекстное меню для своего проекта и выберите **Свойства**. Появляются страницы свойств для проекта.  
  
2.  На вкладке "Приложение" в списке **Автоматически запускаемый объект** выберите **MyNewService.Program**.  
  
3.  В **Обозревателе решений**откройте контекстное меню проекта, а затем выберите **Построить** для построения проекта (сочетание клавиш: Ctrl+Shift+B).  
  
<a name="BK_Install"></a>   
## <a name="installing-the-service"></a>Установка службы  
 После создания службы Windows ее можно установить. Чтобы установить службу Windows, необходимо иметь разрешения администратора на то компьютере, на котором выполняется установка.  
  
#### <a name="to-install-a-windows-service"></a>Установка службы Windows  
  
1.  В Windows 7 и Windows Server откройте **Командная строка разработчика** в разделе **Инструменты Visual Studio** в меню **Пуск** . В Windows 8 или Windows 8.1 выберите **Инструменты Visual Studio** на экране **Пуск** , а затем запустите командную строку разработчика с правами администратора. (Если вы используете мышь, щелкните правой кнопкой мыши **Командная строка разработчика**и выберите **Запуск от имени администратора**.)  
  
2.  В окне "Командная строка" откройте папку, содержащую выходные данные проекта. Например, в папке "Мои документы" перейдите в папку "Visual Studio 2013\Projects\MyNewService\bin\Debug".  
  
3.  Введите следующую команду:  
  
    ```  
    installutil.exe MyNewService.exe  
    ```  
  
     Если служба установлена успешно, installutil.exe сообщит об успешном завершении работы. Если система не может найти файл InstallUtil.exe, убедитесь, что он существует на вашем компьютере. Этот инструмент устанавливается с помощью платформы .NET Framework в папку `%WINDIR%\Microsoft.NET\Framework[64]\`*framework_version*. Например, путь по умолчанию для 32-разрядной версии платформы .NET Framework 4, 4.5, 4.5.1 и 4.5.2 — `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.  
  
     Если процесс installutil.exe сообщает о сбое, проверьте журнал установки, чтобы выяснить причину. По умолчанию журнал находится в той же папке, что и исполняемый файл службы. Установка может завершиться ошибкой, если <xref:System.ComponentModel.RunInstallerAttribute> класса не установлен на `ProjectInstaller` класса, в противном случае атрибут не имеет значение `true`, или же `ProjectInstaller` класс не является `public`.  
  
     Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
<a name="BK_StartService"></a>   
## <a name="starting-and-running-the-service"></a>Запуск и выполнение службы  
  
#### <a name="to-start-and-stop-your-service"></a>Чтобы запустить или остановить службу, выполните следующие действия:  
  
1.  В Windows откройте **начальный** экран или меню **Пуск** и введите `services.msc`.  
  
     В окне **Службы** должна появиться служба **MyNewService** .  
  
     ![MyNewService в окне «службы». ] (../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")  
  
2.  В окне **Службы** откройте контекстное меню службы и нажмите **Пуск**.  
  
3.  Откройте контекстное меню службы и щелкните **Остановить**.  
  
4.  (Необязательно.) Для запуска и остановки службы в командной строке можно использовать команды `net start``ServiceName` и `net stop``ServiceName` .  
  
#### <a name="to-verify-the-event-log-output-of-your-service"></a>Чтобы проверить формирование журнала событий службы, выполните следующие действия:  
  
1.  В Visual Studio откройте **Обозреватель серверов** (сочетание клавиш: Ctrl+Alt+S) и найдите узел **Журналы событий** для локального компьютера.  
  
2.  Найдите список для **MyNewLog** (или **MyLogFile1**, если для добавления аргументов командной строки вы использовали необязательную процедуру) и разверните его. Вы должны увидеть записи для двух действий (запуск и остановка), которые выполнила ваша служба.  
  
     ![Используйте средство просмотра событий для просмотра записей в журнале событий. ] (../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")  
  
<a name="BK_Uninstall"></a>   
## <a name="uninstalling-a-windows-service"></a>Удаление службы Windows  
  
#### <a name="to-uninstall-your-service"></a>Чтобы удалить службу, выполните следующие действия:  
  
1.  Откройте командную строку разработчика с учетными данными администратора.  
  
2.  В окне "Командная строка" откройте папку, содержащую выходные данные проекта. Например, в папке "Мои документы" перейдите в папку "Visual Studio 2013\Projects\MyNewService\bin\Debug".  
  
3.  Введите следующую команду:  
  
    ```  
    installutil.exe /u MyNewService.exe  
    ```  
  
     Если служба удалена успешно, installutil.exe сообщит об этом. Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="next-steps"></a>Следующие шаги  
 Можно создать автономную программу установки, которую могут использовать другие пользователи для установки вашей службы Windows, но для этого потребуется выполнить дополнительные операции. ClickOnce не поддерживает службы Windows, поэтому вы не сможете использовать мастер публикации. Можно использовать полный выпуск InstallShield, который не предоставляется корпорацией Майкрософт. Дополнительные сведения об InstallShield см. в разделе [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition). Для создания установщика службы Windows можно также использовать [Windows Installer XML Toolset](http://go.microsoft.com/fwlink/?LinkId=249067) .  
  
 Кроме того, можно изучить возможности компонента <xref:System.ServiceProcess.ServiceController> , который позволяет отправлять команды в установленную службу.  
  
 Для создания журнала событий при установке приложения можно воспользоваться установщиком, а не создавать журнал после запуска приложения. Кроме того, в этом случае журнал событий будет удален установщиком при удалении приложения. Дополнительные сведения см. на странице <xref:System.Diagnostics.EventLogInstaller> .  
  
## <a name="see-also"></a>См. также  
 [Приложения служб Windows](../../../docs/framework/windows-services/index.md)  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Службы (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
