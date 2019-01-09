---
title: Как выполнить Создание пользовательского участника отслеживания
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: 4afa3f46532e365760c0dd5a9e1880a82e5ae82b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150639"
---
# <a name="how-to-create-a-custom-tracking-participant"></a>Как выполнить Создание пользовательского участника отслеживания
Отслеживание рабочих процессов обеспечивает видимость состояния выполнения рабочего процесса. Среда выполнения рабочего процесса отправляет записи отслеживания, описывающие события жизненного цикла рабочего процесса, события жизненного цикла действия, возобновления закладок и сбои. Эти записи отслеживания используются участниками отслеживания. Windows Workflow Foundation (WF) включает стандартного участника отслеживания, записывает записи отслеживания в виде трассировки событий для Windows (ETW). Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания. На этом шаге учебника описывается, как создать настраиваемого участника отслеживания и профиль отслеживания, которые захватывают выходные данные действий `WriteLine`, чтобы их можно было показать пользователю.  
  
> [!NOTE]
>  Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов. Для изучения этого раздела необходимо сначала пройти предыдущие шаги. Чтобы скачать полную версию или просмотреть пошаговое видео учебника, см. в разделе [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
## <a name="to-create-the-custom-tracking-participant"></a>Создание пользовательского участника отслеживания  
  
1.  Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **добавить**, **класс**. Тип `StatusTrackingParticipant` в **имя** и нажмите кнопку **добавить**.  
  
2.  Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3.  Измените класс `StatusTrackingParticipant` таким образом, чтобы он наследовался от класса `TrackingParticipant`.  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4.  Добавьте следующее переопределение метода `Track`. Существует несколько различных записей отслеживания. Нас интересуют только выходные данные действий `WriteLine`, которые содержатся в записях отслеживания действий. Если `TrackingRecord` является `ActivityTrackingRecord` для действия `WriteLine`, `Text` действия `WriteLine` добавляется в файл после `InstanceId` рабочего процесса. В этом руководстве файл сохраняется в текущей папке ведущего приложения.  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     Если профиль отслеживания не указан, используется профиль по умолчанию. Если используется профиль отслеживания по умолчанию, записи отслеживания создаются для всех `ActivityStates`. Поскольку нам нужно получить текст только один раз в течение жизненного цикла действия `WriteLine`, мы извлекаем текст только из состояния `ActivityStates.Executing`. В [для создания профиля отслеживания и регистрация участника отслеживания](#to-create-the-tracking-profile-and-register-the-tracking-participant), создается профиль отслеживания, указывающее, что только `WriteLine` `ActivityStates.Executing` создаются записи отслеживания.  
  
## <a name="to-create-the-tracking-profile-and-register-the-tracking-participant"></a>Создание профиля отслеживания и регистрация участника отслеживания  
  
1.  Щелкните правой кнопкой мыши **WorkflowHostForm** в **обозревателе решений** и выберите **Просмотр кода**.  
  
2.  Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3.  Добавьте следующий код в `ConfigureWorkflowApplication` сразу после кода, добавляющего `StringWriter` к расширениям рабочего процесса, и перед обработчиками жизненного цикла рабочего процесса.  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =   
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     Этот профиль отслеживания указывает, что только записи состояния действий `WriteLine` в состоянии `Executing` отправляются пользовательскому участнику отслеживания.  
  
     После добавления кода запуск `ConfigureWorkflowApplication` будет выглядеть так, как показано в следующем примере.  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =   
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
## <a name="to-display-the-tracking-information"></a>Отображение сведений об отслеживании  
  
1.  Щелкните правой кнопкой мыши **WorkflowHostForm** в **обозревателе решений** и выберите **Просмотр кода**.  
  
2.  В обработчике `InstanceId_SelectedIndexChanged` добавьте следующий код сразу после кода очистки окна состояния.  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     Если новый рабочий процесс выбран в списке рабочих процессов, записи отслеживания для этого рабочего процесса загружаются и отображаются в окне состояния. Ниже приведен полный пример обработчика `InstanceId_SelectedIndexChanged`.  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
    ```  
  
## <a name="to-build-and-run-the-application"></a>Сборка и запуск приложения  
  
1.  Нажмите клавиши Ctrl+Shift+B, чтобы создать приложение.  
  
2.  Нажмите клавиши Ctrl+F5, чтобы запустить приложение.  
  
3.  Выберите диапазон для игры на угадывание и тип рабочего процесса для запуска и нажмите кнопку **новая игра**. Введите догадку в **предположение** поле и нажмите кнопку **Go** Чтобы отправить догадку. Обратите внимание, что состояние рабочего процесса отображается в окне состояния. Этот результат получен из действий `WriteLine`. Переключиться на другой рабочий процесс, выбрав один из **идентификатор экземпляра рабочего процесса** поле со списком и обратите внимание, что состояние текущего рабочего процесса удален. Переключитесь на предыдущий рабочий процесс и отметьте, что состояние восстановлено, как в следующем примере.  
  
    > [!NOTE]
    > Если перейти к рабочему процессу, который был запущен до включения отслеживания, состояние не отображается. Но если вы вводите дополнительные предположения, их состояние сохраняется, поскольку теперь отслеживание включено.  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```
    
    > [!NOTE]
    > Эти сведения полезны для определения диапазона случайного числа, но они не содержат никаких данных о предыдущих предположениях. Эта информация находится в следующем шаге [как: Размещение нескольких версий рабочего процесса Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).

    Запишите идентификатор экземпляра рабочего процесса и доведите игру до конца.
  
4.  Откройте проводник Windows и перейдите к **NumberGuessWorkflowHost\bin\debug** папку (или **bin\release** в зависимости от параметров проекта). Обратите внимание, что в дополнение к исполняемым файлам проекта существуют файлы с именами с идентификатором GUID. Определите файл, который соответствует идентификатору экземпляра рабочего процесса, завершенного на предыдущем шаге, и откройте его в Блокноте. Данные отслеживания содержат информацию, подобную следующим данным.  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    В дополнение к отсутствию догадок пользователя эти данные отслеживания не содержат сведения о последнем предположении рабочего процесса. Это происходит потому, что данные отслеживания состоят только из выходных данных `WriteLine` рабочего процесса, а последнее отображаемое сообщение выдается из обработчика `Completed` после завершения рабочего процесса. В следующем шаге этого руководства [как: Размещение нескольких версий рабочего процесса Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md), существующий `WriteLine` изменены действий для отображения догадок пользователя, а также само `WriteLine` добавляется действие, отображающий окончательные результаты. После интеграции этих изменений, [как: Размещение нескольких версий рабочего процесса Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md) показано, как разместить несколько версий рабочего процесса, в то же время.
