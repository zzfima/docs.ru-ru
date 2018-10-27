---
title: Как разместить параллельно несколько версий рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 04586f22076b6e2cf4175c7d9d985820ef7885c6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181623"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a>Как разместить параллельно несколько версий рабочего процесса
`WorkflowIdentity` предоставляет разработчикам приложений рабочих процессов способ связать имя и версию с определением рабочего процесса, а также связать эти сведения с сохраненным экземпляром рабочего процесса. Эти идентификационные данные могут быть использованы разработчиками приложений рабочего процесса для поддержки таких сценариев, как параллельное выполнение нескольких версий определения рабочего процесса, и являются ключевым элементом для других функциональных возможностей, таких как динамическое обновление. Этот шаг в учебнике показывает, как использовать `WorkflowIdentity` для размещения нескольких версий рабочих процессов одновременно.

> [!NOTE]
>  Чтобы скачать полную версию или просмотреть пошаговое видео учебника, см. в разделе [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
## <a name="in-this-topic"></a>Содержание раздела  
 На этом этапе учебника действия `WriteLine` в рабочем процессе изменены для предоставления дополнительных сведений и добавлено новое действие `WriteLine`. Копия исходной сборки рабочего процесса сохранена, а ведущее приложение обновлено для возможности одновременного выполнения исходных и обновленных рабочих процессов.  
  
-   [Для создания копии проекта NumberGuessWorkflowActivities](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [Обновление рабочих процессов](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [Обновление рабочего процесса конечного автомата](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [Обновление рабочего процесса блок-схема](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [Обновление последовательного рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [Обновление WorkflowVersionMap для включения предыдущих версий рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [Построение и запуск приложения](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  Перед выполнением действий, описанных в этом разделе, выполните приложение, запустите несколько рабочих процессов каждого типа и укажите одно или два предположения для каждого из них. Сохраненные рабочие процессы используются в этом шаге и приведенную ниже [как: обновить определение запущенного экземпляра рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).

> [!NOTE]
>  Каждый шаг в учебнике «Приступая к работе» построен на основе предыдущих шагов. Если вы не прошли предыдущих шагов можно загрузить завершенную версию учебника [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
###  <a name="BKMK_BackupCopy"></a> Для создания копии проекта NumberGuessWorkflowActivities  
  
1.  Откройте **WF45GettingStartedTutorial** решение в Visual Studio 2012, если оно еще не открыто.  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Закрыть **WF45GettingStartedTutorial** решения.  
  
4.  Откройте проводник Windows и перейдите в папку, где находятся файл решения и папки проекта.  
  
5.  Создайте новую папку с именем **PreviousVersions** в той же папке, что **NumberGuessWorkflowHost** и **NumberGuessWorkflowActivities**. Эта папка служит для хранения сборок, содержащих различные версии рабочих процессов, которые используются на последующих шагах учебника.  
  
6.  Перейдите к **NumberGuessWorkflowActivities\bin\debug** папку (или **bin\release** в зависимости от параметров проекта). Копировать **NumberGuessWorkflowActivities.dll** и вставьте его в **PreviousVersions** папки.  
  
7.  Переименуйте **NumberGuessWorkflowActivities.dll** в **PreviousVersions** папку **NumberGuessWorkflowActivities_v1.dll**.  
  
    > [!NOTE]
    >  Шаги в этом разделе демонстрируют один способ управления сборками, которые используются для хранения нескольких версий рабочих процессов. Также можно использовать другие методы, такие как строгое наименование сборок и их регистрация в глобальном кэше сборок (GAC).

8.  Создайте новую папку с именем **NumberGuessWorkflowActivities_du** в той же папке, что **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**и их вновь добавлен **PreviousVersions** папке и скопируйте все файлы и вложенные папки из **NumberGuessWorkflowActivities** в новую  **NumberGuessWorkflowActivities_du** папки. Эта резервная копия проекта для начальной версии действий используется в [как: обновить определение запущенного экземпляра рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).

9. Снова откройте **WF45GettingStartedTutorial** решение в Visual Studio 2012.

###  <a name="BKMK_UpdateWorkflows"></a> Обновление рабочих процессов
 В этом разделе обновлены определения рабочего процесса. Обновлены два действия `WriteLine`, которые получают отзывы на пробное значение пользователя, и добавлено новое действие `WriteLine`, которое предоставляет дополнительные сведения об игре, как только будет угадано число.

####  <a name="BKMK_UpdateStateMachine"></a> Обновление рабочего процесса конечного автомата

1.  В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **StateMachineNumberGuessWorkflow.xaml**.

2.  Дважды щелкните **неверное пробное значение** перехода в конечном автомате.

3.  Обновите `Text` крайнего левого `WriteLine` в действии `If`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4.  Обновите `Text` крайнего правого `WriteLine` в действии `If`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5.  Возврат к общему машины представление в конструкторе рабочих процессов состояния, нажав кнопку **StateMachine** на экране навигатора в верхней части конструктора рабочих процессов.

6.  Дважды щелкните **правильное пробное значение** перехода в конечном автомате.

7.  Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его на **Перетащите сюда действие Action** метку Переход.

8.  В поле свойств `Text` введите следующее выражение.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

####  <a name="BKMK_UpdateFlowchart"></a> Обновление рабочего процесса блок-схема

1.  В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **FlowchartNumberGuessWorkflow.xaml**.

2.  Обновите `Text` крайнего левого действия `WriteLine`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3.  Обновите `Text` крайнего правого действия `WriteLine`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4.  Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и разместите его в точку удаления действия `True` самого верхнего `FlowDecision` . Действие `WriteLine` добавляется к блок-схеме и связывается с действием `True``FlowDecision`.

5.  В поле свойств `Text` введите следующее выражение.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

####  <a name="BKMK_UpdateSequential"></a> Обновление последовательного рабочего процесса

1.  В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **SequentialNumberGuessWorkflow.xaml**.

2.  Обновите `Text` крайнего левого `WriteLine` в действии `If`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3.  Обновите `Text` крайнего правого действия `WriteLine` в действии `If`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4.  Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его после **DoWhile** действия, чтобы  **WriteLine** оказался последним действием в корневом каталоге `Sequence` действия.

5.  В поле свойств `Text` введите следующее выражение.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

###  <a name="BKMK_UpdateWorkflowVersionMap"></a> Обновление WorkflowVersionMap для включения предыдущих версий рабочего процесса

1.  Дважды щелкните **WorkflowVersionMap.cs** (или **WorkflowVersionMap.vb**) в разделе **NumberGuessWorkflowHost** проекта, чтобы открыть его.

2.  Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3.  Добавьте три новых идентификатора рабочих процессов непосредственно под тремя существующими объявлениями идентификаторов рабочих процессов. Эти новые идентификаторы рабочих процессов `v1` будут использоваться для получения правильных определений рабочих процессов перед выполнением обновлений.

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 Identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;
    ```

4.  В конструкторе `WorkflowVersionMap` обновите свойство `Version` трех текущих идентификаторов рабочих процессов до `2.0.0.0`.

    ```vb
    'Add the current workflow version identities.
    StateMachineNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    SequentialNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
    ```

    ```csharp
    // Add the current workflow version identities.
    StateMachineNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    SequentialNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
    ```

     Код, который добавляет текущие версии рабочих процессов в словарь, использует текущие версии, которые указаны в проекте, чтобы код, который инициализирует определения рабочего процесса, не нужно было обновлять.

5.  Добавьте следующий код в конструктор сразу после кода, добавляющего текущие версии в словарь.

    ```vb
    'Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }
    ```

    ```csharp
    // Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };
    ```

     Эти удостоверения рабочих процессов связаны с первоначальными версиями соответствующих определений рабочих процессов.

6.  Затем загрузите сборку, которая содержит первоначальную версию определений рабочих процессов, создайте соответствующие определения рабочих процессов и добавьте их в словарь.

    ```vb
    'Add the previous version workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v1 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Add the previous version workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v1 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     Ниже приведен полный список для обновленного класса `WorkflowVersionMap`.

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 Identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
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

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
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

###  <a name="BKMK_BuildAndRun"></a> Сборка и запуск приложения

1.  Нажмите сочетание клавиш CTRL+SHIFT+B, чтобы построить приложение, а затем сочетание клавиш CTRL+F5 для его запуска.

2.  Запустить новый рабочий процесс, нажав кнопку **новую игру**. Версия рабочего процесса отображается под окном состояния и отображает обновленную версию из связанного `WorkflowIdentity`. Запишите `InstanceId`, чтобы просмотреть файл отслеживания для рабочего процесса после его завершения, а затем вводите предположения, пока игра не завершится. Обратите внимание на то, что догадка пользователя отображается в окне состояния в зависимости от обновлений действий `WriteLine`.

 **Введите число от 1 до 10**  
**5-слишком много.**  
**Введите число от 1 до 10**  
**3-слишком много.**  
**Введите число от 1 до 10**  
**1-слишком мало.**  
**Введите число от 1 до 10**  
**Поздравляем, Вы угадали число за 4 попытки.**  

    > [!NOTE]
    >  Отображается обновленный текст из действий `WriteLine`, но выходные данные последнего действия `WriteLine`, которое было добавлено в этом разделе, отсутствуют. Это происходит потому, что окно состояния обновляется обработчиком `PersistableIdle`. Поскольку рабочий процесс завершается, а не переходит в состояние бездействия после окончательного действия, обработчик `PersistableIdle` не вызывается. Однако похожее сообщение отображается обработчиком `Completed` в окне состояния. Если необходимо, код можно добавить в обработчик `Completed`, чтобы извлечь текст из `StringWriter` и показать его в окне состояния.

3.  Откройте проводник Windows и перейдите к **NumberGuessWorkflowHost\bin\debug** папку (или **bin\release** в зависимости от параметров проекта) и откройте файл трассировки с помощью блокнота, соответствующий для завершенного рабочего процесса. Если вы не вносили запишите `InstanceId`, можно определить правильный файл отслеживания с помощью **Дата изменения** сведения в обозревателе Windows.

 **Введите число от 1 до 10**
**5-слишком много.** 
 **Введите число от 1 до 10**
**3 слишком велико.** 
 **Введите число от 1 до 10**
**1-слишком мало.** 
 **Введите число от 1 до 10**
**2-правильное число. Вы угадали число за 4 попытки.**      Обновленные выходные данные `WriteLine` содержатся в файле отслеживания, в том числе выходные данные трассировки действия `WriteLine`, добавленного в этом разделе.

4.  Перейдите к приложению отгадывания чисел и выберите один из рабочих процессов, который был запущен до выполнения обновлений. Вы можете указать версию выбранного в данный момент рабочего процесса, посмотрев сведения о версии, отображаемые под окном состояния. Введите несколько предположений и обратите внимание на то, что некоторые обновления состояния соответствуют выходным данным действия `WriteLine` из предыдущей версии, но не включают предположение пользователя. Это происходит потому, что такие рабочие процессы используют предыдущее определение рабочего процесса, в котором не выполнены обновления `WriteLine`.

     На следующем шаге [как: обновить определение запущенного экземпляра рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), выполнение `v1` экземпляров рабочего процесса обновляются, чтобы они содержали новые функции в виде `v2` экземпляров.
