---
title: Практическое руководство. Запуск рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 06ac34f5ba5d95bd9f000a35036cf288d3c8f7f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779162"
---
# <a name="how-to-run-a-workflow"></a>Практическое руководство. Запуск рабочего процесса
Этот раздел продолжает учебник Windows Workflow Foundation Приступая к работе и описывает, как создать узел рабочего процесса и запустить рабочий процесс, описанный в предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) раздела.

> [!NOTE]
>  Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов. Для изучения этого раздела, необходимо сначала выполнить [как: Создание действия](how-to-create-an-activity.md) и [как: Создание рабочего процесса](how-to-create-a-workflow.md).

> [!NOTE]
>  Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow-host-project"></a>Создание проекта узла рабочего процесса  
  
1. Откройте решение из предыдущего [как: Создание действия](how-to-create-an-activity.md) темам с помощью Visual Studio 2012.  
  
2. Щелкните правой кнопкой мыши решение **WF45GettingStartedTutorial** в окне **Обозреватель решений** и выберите **Добавить**, **Создать проект**.  
  
    > [!TIP]
    >  Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений** .

3. В узле **Установленные** выберите пункты **Visual C#** и **Рабочий процесс** (или **Visual Basic**и **Рабочий процесс**).

    > [!NOTE]
    >  В зависимости от того, какой язык программирования задан как основной в Visual Studio, узел **Visual C#** или **Visual Basic** может находиться в разделе **Другие языки** узла **Установленные** .

     Убедитесь, что в раскрывающемся списке версий .NET Framework выбран пункт **.NET Framework 4.5** . В списке **Рабочий процесс** выберите **Консольное приложение рабочего процесса** . Введите `NumberGuessWorkflowHost` в поле **Имя** и нажмите кнопку **ОК**. Будет создано начальное приложение рабочего процесса с базовой поддержкой размещения рабочего процесса. Этот базовый код размещения изменяется и используется для выполнения приложения рабочего процесса.

4. Щелкните правой кнопкой мыши созданный проект **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **Добавить ссылку**. Выберите **Решение** из списка **Добавление ссылки** , установите флажок рядом с **NumberGuessWorkflowActivities**и нажмите кнопку **ОК**.

5. Щелкните правой кнопкой мыши **Workflow1.xaml** в окне **Обозреватель решений** и выберите **Удалить**. Нажмите кнопку **ОК** для подтверждения.

### <a name="to-modify-the-workflow-hosting-code"></a>Изменение кода размещения рабочего процесса

1. В **Solution Explorer** дважды щелкните **Program.cs** или **Module1.vb** для вывода кода.

    > [!TIP]
    >  Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений** .

     Поскольку этот проект был создан с помощью шаблона **Консольное приложение рабочего процесса** , **Program.cs** или **Module1.vb** содержит следующий базовый код размещения рабочего процесса.

    ```vb
    ' Create and cache the workflow definition
    Activity workflow1 = new Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     Этот код размещения использует <xref:System.Activities.WorkflowInvoker>. <xref:System.Activities.WorkflowInvoker> предоставляет простой способ вызова рабочего процесса аналогично вызову метода и может использоваться только для рабочих процессов, не использующих сохраняемость. <xref:System.Activities.WorkflowApplication> предоставляет улучшенную модель выполнения рабочих процессов, которая включает уведомления о событиях жизненного цикла, управление выполнением, возобновление закладок и сохраняемость. В этом примере используются закладки, а для размещения рабочего процесса используется <xref:System.Activities.WorkflowApplication> . Добавьте инструкцию `using` или **Imports** в начало файла **Program.cs** или **Module1.vb** после существующих инструкций **using** или **Imports** .

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     Замените строки кода, использующие <xref:System.Activities.WorkflowInvoker> , следующим базовым кодом размещения <xref:System.Activities.WorkflowApplication> . Этот образец кода размещения показывает основные шаги по размещению и вызову рабочего процесса, но пока не обладает достаточной функциональностью для успешного выполнения рабочего процесса, описанного в данном разделе. В ходе следующих шагов этот базовый код модифицируется и добавляются дополнительные функции, пока приложение не будет полностью готово.

    > [!NOTE]
    >  Замените `Workflow1` в этих примерах на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, или `StateMachineNumberGuessWorkflow`, в зависимости от рабочего процесса, который вы выполнили на предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) шаг. Если не заменить `Workflow1` , то при попытке создать или запустить рабочий процесс будут выданы ошибки сборки.

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     Этот код создает объект <xref:System.Activities.WorkflowApplication>, подписывается на три события из жизненного цикла рабочего процесса, начинает рабочий процесс вызовом <xref:System.Activities.WorkflowApplication.Run%2A>, а затем ждет завершения рабочего процесса. После завершения рабочего процесса устанавливается <xref:System.Threading.AutoResetEvent> и ведущее приложение завершает работу.

### <a name="to-set-input-arguments-of-a-workflow"></a>Настройка входных аргументов рабочего процесса

1. Добавьте следующую инструкцию в начало файла **Program.cs** или **Module1.vb** после существующих инструкций `using` или `Imports` .

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. Замените строку кода, создающую новое <xref:System.Activities.WorkflowApplication> , следующим кодом, который создает и передает словарь параметров рабочему процессу, когда процесс создается.

    > [!NOTE]
    >  Замените `Workflow1` в этих примерах на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, или `StateMachineNumberGuessWorkflow`, в зависимости от рабочего процесса, который вы выполнили на предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) шаг. Если не заменить `Workflow1` , то при попытке создать или запустить рабочий процесс будут выданы ошибки сборки.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     В этом словаре содержится один элемент с ключом `MaxNumber`. Ключи в словаре входных данных соответствуют входным аргументам в корневом действии рабочего процесса. `MaxNumber` используется рабочим процессом для определения верхней границы случайного числа.

### <a name="to-retrieve-output-arguments-of-a-workflow"></a>Извлечение выходных аргументов рабочего процесса

1. Модифицируйте обработчик <xref:System.Activities.WorkflowApplication.Completed%2A> , чтобы извлечь и отобразить число ходов, использованных рабочим процессом.

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a>Возобновление закладки

1. Добавьте следующий код в начало метода `Main` сразу после существующего объявления <xref:System.Threading.AutoResetEvent> .

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. Добавьте следующий обработчик <xref:System.Activities.WorkflowApplication.Idle%2A> сразу после трех существующих обработчиков жизненного цикла процесса в `Main`.

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     Каждый раз, когда рабочий процесс переходит в неактивный режим в ожидании следующего предположения, вызывается этот обработчик и устанавливается `idleAction` <xref:System.Threading.AutoResetEvent> . Код на следующем этапе использует `idleEvent` и `syncEvent` , чтобы определить, ждет рабочий процесс следующего предположения или он завершился.

    > [!NOTE]
    >  В этом примере ведущее приложение использует события автоматического сброса в обработчиках <xref:System.Activities.WorkflowApplication.Completed%2A> и <xref:System.Activities.WorkflowApplication.Idle%2A> , чтобы синхронизировать ведущее приложение с ходом выполнения рабочего процесса. Устанавливать блокировку и ждать неактивности рабочего процесса перед возобновлением закладки не обязательно, но в этом примере требуются события синхронизации, чтобы узел знал, завершен ли рабочий процесс, или он ждет дальнейшего ввода данных от пользователя с помощью <xref:System.Activities.Bookmark>. Дополнительные сведения см. в разделе [закладки](bookmarks.md).

3. Удалите вызов `WaitOne`, замените его кодом для сборки входных данных от пользователя и возобновите <xref:System.Activities.Bookmark>.

     Удалите следующую строку кода.

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     Замените ее следующим примером.

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="BKMK_ToRunTheApplication"></a> Сборка и запуск приложения

1. Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в окне **Обозреватель решений** и выберите команду **Установить как запускаемый проект**.

2. Нажмите клавиши CTRL+F5 для сборки и запуска приложения. Попробуйте угадать число с наименьшим числом попыток.

     Чтобы протестировать приложение с другим стилем рабочего процесса, замените `Workflow1` в коде, который создает <xref:System.Activities.WorkflowApplication> , на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`или `StateMachineNumberGuessWorkflow`в зависимости от того, какой стиль рабочего процесса нужен.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Инструкции по добавлению сохраняемости к приложению рабочего процесса см. в следующем разделе [как: Создание и запуск длительно выполняющимся процессом](how-to-create-and-run-a-long-running-workflow.md).

## <a name="example"></a>Пример
 Ниже приведен полный код для метода `Main` .

> [!NOTE]
>  Замените `Workflow1` в этих примерах на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, или `StateMachineNumberGuessWorkflow`, в зависимости от рабочего процесса, который вы выполнили на предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) шаг. Если не заменить `Workflow1` , то при попытке создать или запустить рабочий процесс будут выданы ошибки сборки.

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a>См. также

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [Программирование в Windows Workflow Foundation](programming.md)
- [Руководство по началу работы](getting-started-tutorial.md)
- [Практическое руководство. Создание рабочего процесса](how-to-create-a-workflow.md)
- [Практическое руководство. Создание и запуск длительно выполнении рабочего процесса](how-to-create-and-run-a-long-running-workflow.md)
- [Ожидание входных данных в рабочем процессе](waiting-for-input-in-a-workflow.md)
- [Размещение рабочих процессов](hosting-workflows.md)