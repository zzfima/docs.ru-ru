---
title: Создание и запуск долго выполняющегося рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 10eb4e2947bed9cea89f1cda05272aa3fa0fadaa
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204881"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a>Создание и запуск долго выполняющегося рабочего процесса

Одной из основных функций Windows Workflow Foundation (WF) является способность среды выполнения сохранять и выгружать неактивные рабочие процессы в базу данных. Инструкции по [выполнению рабочего процесса](how-to-run-a-workflow.md) демонстрируют основы размещения рабочих процессов с помощью консольного приложения. Приведены примеры запуска рабочих процессов, обработчиков жизненного цикла рабочего процесса и возобновления закладок. Для эффективной демонстрации сохранения рабочего процесса требуется более сложный узел рабочих процессов, обеспечивающий запуск и возобновление нескольких экземпляров рабочего процесса. На этом шаге учебника показано, как создать ведущее приложение форм Windows Form, которое обеспечивает запуск и возобновление нескольких экземпляров рабочих процессов, сохранение рабочего процесса и основу для таких дополнительных возможностей, как отслеживание версий, которые показаны в последующих шагах учебника, и управление ими.

> [!NOTE]
> В этом шаге руководства и последующих шагах используются все три типа рабочих процессов из [руководства: создание рабочего процесса](how-to-create-a-workflow.md). Если вы не выполнили все три типа, вы можете скачать завершенную версию шагов из [Windows Workflow Foundation (WF45) — Начало работы учебнике](https://go.microsoft.com/fwlink/?LinkID=248976).

> [!NOTE]
> Чтобы скачать готовую версию или просмотреть видео пошаговое руководство, см. Руководство по [Windows Workflow Foundation (WF45) — Начало работы](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="to-create-the-persistence-database"></a>Создание базы данных сохраняемости

1. Откройте SQL Server Management Studio и подключитесь к локальному серверу, например **.\SQLEXPRESS**. Щелкните правой кнопкой мыши узел **базы данных** на локальном сервере и выберите пункт **создать базу данных**. Назовите новую базу данных **WF45GettingStartedTutorial**, примите все остальные значения и нажмите кнопку **ОК**.

    > [!NOTE]
    > Перед созданием базы данных убедитесь, что у вас есть разрешение на **Создание базы данных** на локальном сервере.

2. Выберите **Открыть**, **файл** в меню **файл** . Перейдите в следующую папку: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*

    Выберите два следующих файла и нажмите кнопку **Открыть**.

    - *Склворкфловинстанцесторелогик. SQL*

    - *Склворкфловинстанцесторесчема. SQL*

3. В меню **окно** выберите **склворкфловинстанцесторесчема. SQL** . Убедитесь, что в раскрывающемся списке **Доступные базы данных** выбрано **WF45GettingStartedTutorial** , и выберите команду **выполнить** в меню **запрос** .

4. В меню **окно** выберите **склворкфловинстанцесторелогик. SQL** . Убедитесь, что в раскрывающемся списке **Доступные базы данных** выбрано **WF45GettingStartedTutorial** , и выберите команду **выполнить** в меню **запрос** .

    > [!WARNING]
    > Важно выполнить предыдущие два шага в правильном порядке. Если выполнить запросы в неправильном порядке, произойдет ошибка и база данных сохраняемости не будет правильно настроена.

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a>Добавление ссылки в сборки DurableInstancing

1. Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **Обозреватель решений** и выберите команду **Добавить ссылку**.

2. Выберите **сборки** в списке **Добавить ссылку** и введите `DurableInstancing` в поле **Поиск сборок** . Сборки отфильтруются, и будет легче выбрать необходимые ссылки.

3. Установите флажок рядом с элементом **System. activitys. DurableInstancing** и **System. Runtime. DurableInstancing** в списке **результатов поиска** и нажмите кнопку **ОК**.

## <a name="to-create-the-workflow-host-form"></a>Создание ведущей формы рабочего процесса

> [!NOTE]
> В шагах этой процедуры показано, как добавить и настроить форму вручную. При необходимости можно загрузить файлы решений для учебника и добавить готовую форму в проект. Чтобы скачать файлы учебников, см. [руководство по Windows Workflow Foundation (WF45) — Начало работы](https://go.microsoft.com/fwlink/?LinkID=248976). После скачивания файлов щелкните правой кнопкой мыши **NumberGuessWorkflowHost** и выберите команду **Добавить ссылку**. Добавьте ссылку на **System. Windows. Forms** и **System. Drawing**. Эти ссылки добавляются автоматически при добавлении новой формы из меню **Добавить**, **создать элемент** , но их необходимо добавить вручную при импорте формы. После добавления ссылок щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **Обозреватель решений** и выберите **добавить**, **существующий элемент**. Перейдите в папку `Form` в файлах проекта, выберите **WorkflowHostForm.CS** (или **воркфловхостформ. vb**) и нажмите кнопку **добавить**. Если вы решили импортировать форму, можно перейти к следующему разделу, [чтобы добавить свойства и вспомогательные методы формы](#to-add-the-properties-and-helper-methods-of-the-form).

1. Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **Обозреватель решений** и выберите **добавить**, **новый элемент**.

2. В списке **установленные** шаблоны выберите **форма Windows**, введите `WorkflowHostForm` в поле **имя** и нажмите кнопку **Добавить**.

3. Задайте следующие свойства формы.

    |Свойство|Значение|
    |--------------|-----------|
    |FormBorderStyle|FixedSingle|
    |MaximizeBox|Ложь|
    |Размер|400, 420|

4. Добавьте в форму следующие элементы управления в указанном порядке и задайте значения свойств.

    |Управление|Свойство: значение|
    |-------------|---------------------|
    |**Button**|Имя: Невгаме<br /><br /> Расположение: 13, 13<br /><br /> Размер: 75, 23<br /><br /> Текст: Новая игра|
    |**Label**|Расположение: 94, 18<br /><br /> Текст: догадка числа от 1 до|
    |**ComboBox**|Имя: Нумберранже<br /><br /> DropDownStyle: DropDownList<br /><br /> Элементы: 10, 100, 1000<br /><br /> Расположение: 228, 12<br /><br /> Размер: 143, 21|
    |**Label**|Расположение: 13, 43<br /><br /> Текст: тип рабочего процесса|
    |**ComboBox**|Имя: Воркфловтипе<br /><br /> DropDownStyle: DropDownList<br /><br /> Элементы: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow<br /><br /> Расположение: 94, 40<br /><br /> Размер: 277, 21|
    |**Label**|Имя: Воркфловверсион<br /><br /> Расположение: 13, 362<br /><br /> Текст: версия рабочего процесса|
    |**GroupBox**|Расположение: 13, 67<br /><br /> Размер: 358, 287<br /><br /> Текст: игра|

    > [!NOTE]
    > При добавлении следующих элементов управления помещайте их в GroupBox.

    |Управление|Свойство: значение|
    |-------------|---------------------|
    |**Label**|Расположение: 7, 20<br /><br /> Текст: идентификатор экземпляра рабочего процесса|
    |**ComboBox**|Имя: InstanceId.<br /><br /> DropDownStyle: DropDownList<br /><br /> Расположение: 121, 17<br /><br /> Размер: 227, 21|
    |**Label**|Расположение: 7, 47<br /><br /> Текст: предположение|
    |**TextBox**|Имя: предположение<br /><br /> Расположение: 50, 44<br /><br /> Размер: 65, 20|
    |**Button**|Имя: Ентергуесс<br /><br /> Расположение: 121, 42<br /><br /> Размер: 75, 23<br /><br /> Текст: введите предположение|
    |**Button**|Имя: Куитгаме<br /><br /> Расположение: 274, 42<br /><br /> Размер: 75, 23<br /><br /> Текст: Quit|
    |**TextBox**|Имя: WorkflowStatus<br /><br /> Расположение: 10, 73<br /><br /> Многострочный: true<br /><br /> ReadOnly: true<br /><br /> Полосы прокрутки: по вертикали<br /><br /> Размер: 338, 208|

5. Задайте для свойства **AcceptButton** формы значение **ентергуесс**.

 В следующем примере показана заполненная форма.

 ![Снимок экрана формы узла рабочего процесса Windows Workflow Foundation.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a>Добавление свойств и вспомогательных методов формы

В этом разделе показано, как добавить в класс формы свойства и вспомогательные методы, которые настраивают пользовательский интерфейс формы для запуска и возобновления рабочих процессов угадывания числа.

1. Щелкните правой кнопкой мыши **воркфловхостформ** в **Обозреватель решений** и выберите **Просмотреть код**.

2. Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).

    ```vb
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    Imports System.Data.SqlClient
    Imports System.IO
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DurableInstancing;
    using System.Data.SqlClient;
    using System.IO;
    using System.Windows.Forms;
    ```

3. Добавьте следующие объявления членов в класс **воркфловхостформ** .

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim workflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool workflowStarting;
    ```

    > [!NOTE]
    > Если у вас другая строка подключения, обновите строку `connectionString` так, чтобы она указывала на вашу базу данных.

4. Добавьте свойство `WorkflowInstanceId` в класс `WorkflowFormHost`.

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    В поле со списком `InstanceId` отображается список сохраненных идентификаторов экземпляров рабочих процессов, а свойство `WorkflowInstanceId` возвращает текущий выбранный рабочий процесс.

5. Добавьте обработчик события `Load` формы. Чтобы добавить обработчик, переключитесь в **режим конструктора** для формы, щелкните значок **событий** в верхней части окна **Свойства** и дважды щелкните **Load (загрузить**).

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. Добавьте следующий код к `WorkflowHostForm_Load`.

    ```vb
    ' Initialize the store and configure it so that it can be used for
    ' multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    ' Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    Когда форма загружена, настраивается класс `SqlWorkflowInstanceStore`, для полей со списком диапазонов и типов рабочего процесса устанавливаются значения по умолчанию, а сохраненные экземпляры рабочих процессов добавляются в поле `InstanceId`.

7. Добавьте обработчик событий `SelectedIndexChanged` для `InstanceId`. Чтобы добавить обработчик, переключитесь в **режим конструктора** для формы, выберите поле со списком `InstanceId`, щелкните значок **событий** в верхней части окна " **Свойства** " и дважды щелкните **элемент ",".**

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. Добавьте следующий код к `InstanceId_SelectedIndexChanged`. Каждый раз, когда пользователь выбирает рабочий процесс с помощью поля со списком, этот обработчик обновляет окно состояния.

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    ' Clear the status window.
    WorkflowStatus.Clear()

    ' Get the workflow version and display it.
    ' If the workflow is just starting then this info will not
    ' be available in the persistence store so do not try and retrieve it.
    If Not workflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        ' Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!workflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. Добавьте следующий метод `ListPersistedWorkflows` в класс формы.

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    ' Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (var localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow.
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    `ListPersistedWorkflows` отправляет запрос в хранилище экземпляров для сохраняемых экземпляров рабочего процесса и добавляет идентификаторы экземпляров в поле со списком `cboInstanceId`.

10. Добавьте следующий метод `UpdateStatus` и соответствующий делегат в класс формы. Этот метод обновляет окно состояния в форме с данными о состоянии рабочего процесса, выполняемого в данный момент.

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        ' We may be on a different thread so we need to
        ' make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            ' Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. Добавьте следующий метод `GameOver` и соответствующий делегат в класс формы. После завершения рабочего процесса этот метод обновляет пользовательский интерфейс формы, удаляя идентификатор экземпляра завершенного рабочего процесса из поля со списком **InstanceId** .

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            ' Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a>Настройка хранилища экземпляров, обработчиков жизненного цикла рабочего процесса и расширений

1. Добавьте метод `ConfigureWorkflowApplication` в класс формы.

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    Этот метод задает `WorkflowApplication`, добавляет необходимые расширения и обработчики событий жизненного цикла рабочего процесса.

2. В `ConfigureWorkflowApplication` укажите `SqlWorkflowInstanceStore` для `WorkflowApplication`.

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. Затем создайте экземпляр класса `StringWriter` и добавьте его в коллекцию `Extensions` приложения `WorkflowApplication`. При добавлении `StringWriter` к расширениям он фиксирует все выходные данные действия `WriteLine`. Когда рабочий процесс становится неактивным, выходные данные `WriteLine` можно извлечь из `StringWriter` и показать на форме.

    ```vb
    ' Add a StringWriter to the extensions. This captures the output
    ' from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    var sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. Добавьте следующий обработчик события `Completed`. После успешного завершения рабочего процесса число ходов, которое потребовалось для угадывания числа, отображается в окне состояния. Если рабочий процесс завершается, выдаются сведения об исключении, которое явилось причиной. В конце обработчика вызывается метод `GameOver`, который удаляет завершенный рабочий процесс из списка рабочих процессов.

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
        }
        GameOver();
    };
    ```

5. Добавьте следующие обработчики `Aborted` и `OnUnhandledException`. Метод `GameOver` не вызывается из обработчика `Aborted`, поскольку в случае аварийного завершения выполнения экземпляра рабочего процесса работа экземпляра не прекращается окончательно, позже можно перезапустить экземпляр.

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. Добавьте следующий обработчик `PersistableIdle`. Этот обработчик получает расширение `StringWriter`, которое было добавлено, извлекает данные из действий `WriteLine` и отображает их в окне состояния.

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            ' Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    Для перечисления <xref:System.Activities.PersistableIdleAction> существует три значения: <xref:System.Activities.PersistableIdleAction.None>,<xref:System.Activities.PersistableIdleAction.Persist> и <xref:System.Activities.PersistableIdleAction.Unload>. <xref:System.Activities.PersistableIdleAction.Persist> приводит к сохранению рабочего процесса, но не приводит к его выгрузке. <xref:System.Activities.PersistableIdleAction.Unload> приводит к тому, что рабочий процесс сохраняется и выгружается.

    Ниже приведен полный пример метода `ConfigureWorkflowApplication`.

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        ' Configure the persistence store.
        wfApp.InstanceStore = store

        ' Add a StringWriter to the extensions. This captures the output
        ' from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                ' Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        var sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a>Разрешение запуска и возобновления нескольких типов рабочих процессов

Чтобы возобновить экземпляр рабочего процесса, ведущее приложение должно предоставить определение рабочего процесса. В этом учебнике описано 3 типа рабочих процессов и далее предоставлено несколько версий этих типов. `WorkflowIdentity` предоставляет ведущему приложению способ связать идентифицирующие сведения с сохраненным экземпляром рабочего процесса. В этом разделе показано, как создать служебный класс, который поможет сопоставить идентификационные данные из сохраненного экземпляра рабочего процесса с соответствующим определением рабочего процесса. Дополнительные сведения о `WorkflowIdentity` и управлении версиями см. [в разделе Использование WorkflowIdentity и управление версиями](using-workflowidentity-and-versioning.md).

1. Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **Обозреватель решений** и выберите **добавить**, **класс**. Введите `WorkflowVersionMap` в поле **имя** и нажмите кнопку **Добавить**.

2. Добавьте следующие инструкции `using` или `Imports` в начало файла с другими инструкциями `using` или `Imports`.

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. Замените объявление класса `WorkflowVersionMap` следующим объявлением.

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        ' Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            ' Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
       }
    }
    ```

    `WorkflowVersionMap` содержит три удостоверения рабочего процесса, которые сопоставляются с тремя определениями рабочих процессов из этого учебника и используются в следующих разделах при запуске и возобновлении рабочих процессов.

## <a name="to-start-a-new-workflow"></a>Запуск нового рабочего процесса

1. Добавьте обработчик событий `Click` для `NewGame`. Чтобы добавить обработчик, переключитесь в **режим конструктора** для формы и дважды щелкните `NewGame`. Добавляется обработчик `NewGame_Click`, и активируется представление кода формы. Когда пользователь нажимает эту кнопку, запускается новый рабочий процесс.

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. Добавьте следующий код в обработчик события щелчка. Этот код создает словарь входных аргументов для рабочего процесса, различаемых по имени аргумента. Этот словарь содержит одну запись с диапазоном случайного созданных чисел, полученных из поля со списком диапазонов.

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. Затем добавьте следующий код, который запускает рабочий процесс. `WorkflowIdentity` и определение рабочего процесса, соответствующие выбранному типу рабочего процесса, извлекаются с помощью вспомогательного класса `WorkflowVersionMap`. Затем создается новый экземпляр `WorkflowApplication` с помощью определения рабочего процесса, `WorkflowIdentity` и словаря входных аргументов.

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. Затем необходимо добавить следующий код, который добавляет рабочий процесс в список рабочих процессов и отображает сведения о версии рабочего процесса на форме.

    ```vb
    ' Add the workflow to the list and display the version information.
    workflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    workflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    workflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    workflowStarting = false;
    ```

5. Вызовите `ConfigureWorkflowApplication` для настройки хранилища экземпляров, расширений и обработчиков жизненного цикла рабочего процесса для экземпляра `WorkflowApplication`.

    ```vb
    ' Configure the instance store, extensions, and
    ' workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. Теперь вызовите `Run`.

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     Ниже приведен полный пример обработчика `NewGame_Click`.

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        ' Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        ' Add the workflow to the list and display the version information.
        workflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        workflowStarting = False

        ' Configure the instance store, extensions, and
        ' workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        ' Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
        switch (WorkflowType.SelectedItem.ToString())
        {
            case "SequentialNumberGuessWorkflow":
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
                break;

            case "StateMachineNumberGuessWorkflow":
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
                break;

            case "FlowchartNumberGuessWorkflow":
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
                break;
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        var wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        workflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        workflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

## <a name="to-resume-a-workflow"></a>Возобновление рабочего процесса

1. Добавьте обработчик событий `Click` для `EnterGuess`. Чтобы добавить обработчик, переключитесь в **режим конструктора** для формы и дважды щелкните `EnterGuess`. Когда пользователь нажимает эту кнопку, возобновляется рабочий процесс.

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. Добавьте следующий код, чтобы убедиться в том, что рабочий процесс выбран в списке рабочих процессов и догадка пользователя верна.

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. Затем извлеките `WorkflowApplicationInstance` сохраненного экземпляра рабочего процесса. `WorkflowApplicationInstance` представляет экземпляр сохраненного рабочего процесса, который еще не был связан с определением рабочего процесса. `DefinitionIdentity` экземпляра `WorkflowApplicationInstance` содержит `WorkflowIdentity` экземпляра сохраненного рабочего процесса. В этом учебнике служебный класс `WorkflowVersionMap` используется для сопоставления `WorkflowIdentity` с соответствующим определением рабочего процесса. Когда определение рабочего процесса получено, создается приложение `WorkflowApplication` на основе правильного определения.

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. После создания `WorkflowApplication` настройте хранилище экземпляров, обработчики жизненного цикла рабочего процесса и расширения, вызвав `ConfigureWorkflowApplication`. Эти шаги требуются каждый раз, когда создается новое приложение `WorkflowApplication`, и должны быть выполнены до того, как экземпляр рабочего процесса будет загружен в `WorkflowApplication`. После загрузки рабочего процесса он возобновляется с догадкой пользователя.

    ```vb
    ' Configure the extensions and lifecycle handlers.
    ' Do this before the instance is loaded. Once the instance is
    ' loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. И наконец, очистите текстовое поле с догадкой и подготовьте форму для ввода другой догадки.

    ```vb
    ' Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    Ниже приведен полный пример обработчика `EnterGuess_Click`.

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        ' Use the persisted WorkflowIdentity to retrieve the correct workflow
        ' definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        ' Associate the WorkflowApplication with the correct definition
        Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

        ' Configure the extensions and lifecycle handlers.
        ' Do this before the instance is loaded. Once the instance is
        ' loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        ' Load the workflow.
        wfApp.Load(instance)

        ' Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        ' Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

## <a name="to-terminate-a-workflow"></a>Завершение рабочего процесса

1. Добавьте обработчик событий `Click` для `QuitGame`. Чтобы добавить обработчик, переключитесь в **режим конструктора** для формы и дважды щелкните `QuitGame`. Когда пользователь нажимает эту кнопку, рабочий процесс, выбранный на данный момент, завершается.

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. Добавьте следующий код в обработчик `QuitGame_Click`: Code First проверяет, что рабочий процесс выбран в списке рабочих процессов. Затем он загружает сохраненный экземпляр в `WorkflowApplicationInstance`, использует `DefinitionIdentity` для получения правильного определения рабочего процесса и инициализирует `WorkflowApplication`. После этого настраиваются расширения и обработчики жизненного цикла рабочего процесса с помощью метода `ConfigureWorkflowApplication`. После настройки `WorkflowApplication` приложение загружается и вызывается метод `Terminate`.

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition.
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

    ' Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

## <a name="to-build-and-run-the-application"></a>Сборка и запуск приложения

1. Дважды щелкните **Program.CS** (или **Module1. vb**) в **Обозреватель решений** , чтобы отобразить код.

2. Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. Удалите или закомментируйте существующий код размещения рабочего процесса из [руководства: запуск рабочего процесса](how-to-run-a-workflow.md)и замените его следующим кодом.

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **Обозреватель решений** и выберите пункт **Свойства**. На вкладке **приложение** укажите **приложение Windows** для **типа выходных данных**. Этот шаг не обязателен, но, если его не выполнить, вместе с формой отображается окно консоли.

5. Нажмите клавиши Ctrl+Shift+B, чтобы создать приложение.

6. Убедитесь, что **NumberGuessWorkflowHost** установлен в качестве запускаемого приложения, и нажмите клавиши CTRL + F5, чтобы запустить приложение.

7. Выберите диапазон для игры подбора и тип рабочего процесса, который нужно запустить, и щелкните **Новая игра**. Введите предположение в поле **предположение** и нажмите кнопку **Перейти** , чтобы отправить свое предположение. Обратите внимание, что выходные данные действий `WriteLine` отображаются на форме.

8. Запустите несколько рабочих процессов, используя различные типы рабочих процессов и диапазоны номеров, введите некоторые предположения и переключайтесь между рабочими процессами, выбрав из списка **идентификатор экземпляра рабочего процесса** .

    Обратите внимание, что, если перейти к новому рабочему процессу, предыдущие догадки и ход выполнения рабочего процесса не отображаются в окне состояния. Состояние недоступно, так как оно не перехвачено и не сохранено. На следующем шаге руководства [: как создать настраиваемый участник отслеживания](how-to-create-a-custom-tracking-participant.md)создайте настраиваемый участник отслеживания, сохраняющий эту информацию.
