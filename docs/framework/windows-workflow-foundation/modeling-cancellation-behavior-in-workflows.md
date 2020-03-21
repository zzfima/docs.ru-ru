---
title: Моделирование поведения отмены в рабочих процессах
ms.date: 03/30/2017
ms.assetid: d48f6cf3-cdde-4dd3-8265-a665acf32a03
ms.openlocfilehash: 8738afa838f1d0ca36b7fd6def00f0794bcf47ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143048"
---
# <a name="modeling-cancellation-behavior-in-workflows"></a>Моделирование поведения отмены в рабочих процессах
Действия можно отменять внутри рабочего процесса, например действием <xref:System.Activities.Statements.Parallel>, отменяющим неполные ветви, если вычисление его условия <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> возвращает значение `true`, или извне рабочего процесса, если узел вызывает метод <xref:System.Activities.WorkflowApplication.Cancel%2A>. Чтобы предусмотреть выполнение отмены, разработчики рабочего процесса могут использовать действие <xref:System.Activities.Statements.CancellationScope>, действие <xref:System.Activities.Statements.CompensableActivity> или создать пользовательские действия, которые предоставляют логику отмены. В этом разделе приведены общие сведения об отмене в рабочих процессах.  
  
## <a name="cancellation-compensation-and-transactions"></a>Отмена, компенсация и транзакции  
 Транзакции предоставляют приложению способность прерывать (производить откат) все изменения, выполняемые в пределах транзакции, если в ходе выполнения любой части транзакции возникают какие-либо ошибки. Однако не вся работа, которая может потребовать отмены, подходит для транзакций. К примерам такой работы относятся продолжительные задания или операции, в которых не задействуются ресурсы транзакций. Компенсация предоставляет модель для отмены выполненной ранее работы, которая не входит в состав транзакции, если в последующем эти действия вызвали ошибку в рабочем процессе. Отмена предоставляет разработчикам рабочих процессов и действий модель для обработки незавершенной работы, которая не входит в состав транзакции. Если какое-либо действие отменяется до завершения его выполнения, то будет вызвана логика его отмены при ее наличии.  
  
> [!NOTE]
> Для получения дополнительной информации о [Compensation](compensation.md)сделках и компенсации [см.](workflow-transactions.md)  
  
## <a name="using-cancellationscope"></a>Использование CancellationScope  
 Действие <xref:System.Activities.Statements.CancellationScope> имеет два раздела, которые могут содержать дочерние действия: <xref:System.Activities.Statements.CancellationScope.Body%2A> и <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>. В раздел <xref:System.Activities.Statements.CancellationScope.Body%2A> помещаются действия, составляющие логику действия, а в раздел <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> - действия, которые обеспечивают логику отмены действия. Отменено может быть только незавершенное действие. Если речь идет о действии <xref:System.Activities.Statements.CancellationScope>, то под завершением подразумевается завершение действий в <xref:System.Activities.Statements.CancellationScope.Body%2A>. Если запрос отмены запланирован и действия в <xref:System.Activities.Statements.CancellationScope.Body%2A> не завершились, то область <xref:System.Activities.Statements.CancellationScope> будет отмечена как <xref:System.Activities.ActivityInstanceState.Canceled>, после чего будут выполнены действия <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>.  
  
### <a name="canceling-a-workflow-from-the-host"></a>Отмена рабочего процесса с узла  
 Узел может отменить рабочий процесс путем вызова метода <xref:System.Activities.WorkflowApplication.Cancel%2A> экземпляра <xref:System.Activities.WorkflowApplication>, в котором размещен рабочий процесс. В следующем примере создается рабочий процесс, который имеет <xref:System.Activities.Statements.CancellationScope>. Происходит вызов рабочего процесса, а затем узел вызывает метод <xref:System.Activities.WorkflowApplication.Cancel%2A>. Основное выполнение рабочего процесса останавливается, вызывается обработчик <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> области <xref:System.Activities.Statements.CancellationScope>, после чего рабочий процесс завершается с указанием состояния <xref:System.Activities.ActivityInstanceState.Canceled>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#35](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#35)]  
  
 При вызове этого рабочего процесса на консоль выводятся следующие данные.  
  
 **Starting the workflow.**  
**CancellationHandler вызывается.** 
 **Рабочий процесс b30ebb30-df46-4d90-a211-e31c38d8db3c отменен.**
> [!NOTE]
> Если отменяется действие <xref:System.Activities.Statements.CancellationScope> и вызывается обработчик <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>, то на разработчика рабочего процесса возлагается ответственность за определение того, какая часть отмененного действия была выполнена до его отмены в целях предоставления соответствующей логики отмены. Обработчик <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> не предоставляет никаких сведений о ходе выполнения отмененного действия.  
  
 Рабочий процесс также может быть отменен с узла, если за корнем рабочего процесса «всплывает» необработанное исключение и обработчик <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> возвращает <xref:System.Activities.UnhandledExceptionAction.Cancel>. В этом примере запускается рабочий процесс, а затем формируется исключение <xref:System.ApplicationException>. Рабочий процесс не обрабатывает это исключение, поэтому вызывается обработчик <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. Обработчик выдает среде выполнения команду отмены рабочего процесса, а затем вызывается обработчик <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> выполняемого в настоящее время действия <xref:System.Activities.Statements.CancellationScope>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#36](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#36)]  
  
 При вызове этого рабочего процесса на консоль выводятся следующие данные.  
  
 **Starting the workflow.**  
**OnUnhandledException в Workflow 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9**
**ApplicationException был брошен.** 
 **CancellationHandler вызывается.** 
 **Рабочий процесс 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9 отменен.**
### <a name="canceling-an-activity-from-inside-a-workflow"></a>Отмена действия из рабочего процесса  
 Действие также может быть отменено его родительским действием. Например, если действие <xref:System.Activities.Statements.Parallel> имеет несколько выполняющихся ветвей и его условие <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> принимает значение `true`, то его незавершенные ветви будут отменены. В этом примере создается действие <xref:System.Activities.Statements.Parallel>, которое имеет две ветви. Его условию <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> задается значение `true`, поэтому действие <xref:System.Activities.Statements.Parallel> завершается сразу после завершения любой из его ветвей. В этом примере завершается ветвь 2, поэтому ветвь 1 отменяется.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#37](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#37)]  
  
 При вызове этого рабочего процесса на консоль выводятся следующие данные.  
  
 **Начало ветки 1.**  
**Филиал 2 завершен.** 
 **Филиал 1 отменен.** 
 **Рабочий процесс e0685e24-18ef-4a47-acf3-5c638732f3be Завершено.**  Действия также отменяются, если исключение «всплывает» вслед за прохождением корня действия, но обрабатывается на более высоком уровне в рабочем процессе. В этом примере основная логика рабочего процесса состоит из действия <xref:System.Activities.Statements.Sequence>. Последовательность <xref:System.Activities.Statements.Sequence> задается как тело <xref:System.Activities.Statements.CancellationScope.Body%2A> действия <xref:System.Activities.Statements.CancellationScope>, которое содержится в действии <xref:System.Activities.Statements.TryCatch>. Из текста последовательности <xref:System.Activities.Statements.Sequence> формируется исключение, обрабатывается родительским действием <xref:System.Activities.Statements.TryCatch>, после чего последовательность <xref:System.Activities.Statements.Sequence> отменяется.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#39](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#39)]  
  
 При вызове этого рабочего процесса на консоль выводятся следующие данные.  
  
 **Начало последовательности.**  
**Последовательность отменена.** 
 **Исключение поймали.** 
 **Рабочий процесс e3c18939-121e-4c43-af1c-ba1ce977ce55 Завершено.**
### <a name="throwing-exceptions-from-a-cancellationhandler"></a>Формирование исключений из CancellationHandler  
 Для рабочего процесса любые исключения, сформированные из обработчика <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> области <xref:System.Activities.Statements.CancellationScope>, являются неустранимыми. Если есть возможность экранирования исключений из <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>, то используйте конструкцию <xref:System.Activities.Statements.TryCatch> в обработчике <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> для перехвата и обработки этих исключений.  
  
### <a name="cancellation-using-compensableactivity"></a>Отмена с помощью CompensableActivity  
 Как и действие <xref:System.Activities.Statements.CancellationScope>, действие <xref:System.Activities.Statements.CompensableActivity> имеет обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>. Если действие <xref:System.Activities.Statements.CompensableActivity> отменяется, то вызываются любые действия из обработчика <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>. Это может применяться для отмены частично завершенной работы, которую можно компенсировать. Для получения информации <xref:System.Activities.Statements.CompensableActivity> о том, как использовать для компенсации и отмены, см. [Compensation](compensation.md)  
  
## <a name="cancellation-using-custom-activities"></a>Отмена с помощью пользовательских действий  
 Разработчики пользовательских действий могут реализовать логику отмены в своих пользовательских действиях несколькими разными способами. Пользовательские действия, которые являются производными от <xref:System.Activities.Activity>, могут реализовывать логику отмены путем размещения действия <xref:System.Activities.Statements.CancellationScope> или другого пользовательского действия, содержащего логику отмены, в тексте этого действия. Действия, производные от <xref:System.Activities.AsyncCodeActivity> и <xref:System.Activities.NativeActivity>, могут переопределить соответствующий метод <xref:System.Activities.NativeActivity.Cancel%2A> и обеспечить логику отмены действий. Действия, производные от <xref:System.Activities.CodeActivity>, не обеспечивают отмену, поскольку вся их работа осуществляется в единственном всплеске выполнения, когда среда выполнения вызывает метод <xref:System.Activities.CodeActivity.Execute%2A>. Если метод выполнения еще не был вызван и действие, основанное на действии <xref:System.Activities.CodeActivity>, отменяется, действие закрывается с состоянием <xref:System.Activities.ActivityInstanceState.Canceled>, а метод <xref:System.Activities.CodeActivity.Execute%2A> не вызывается.  
  
### <a name="cancellation-using-nativeactivity"></a>Отмена с помощью NativeActivity  
 Действия, производные от действия <xref:System.Activities.NativeActivity>, могут переопределять метод <xref:System.Activities.NativeActivity.Cancel%2A> для предоставления пользовательской логики отмены. Если этот метод не переопределен, то применяется предусмотренная по умолчанию логика отмены рабочего процесса. Отмена по умолчанию — <xref:System.Activities.NativeActivity> это процесс, <xref:System.Activities.NativeActivity.Cancel%2A> который происходит <xref:System.Activities.NativeActivity.Cancel%2A> для того, кто не перекрывает метод или метод которого вызывает базовый <xref:System.Activities.NativeActivity> <xref:System.Activities.NativeActivity.Cancel%2A> метод. При отмене действия среда выполнения отмечает действие как подлежащее отмене и автоматически производит определенную очистку. Если действие имеет только закладки, ожидающие обработки, то закладки удаляются и действие отмечается как <xref:System.Activities.ActivityInstanceState.Canceled>. Любые ожидающие обработки дочерние действия отмененного действия, в свою очередь, будут отменены. Любая попытка запланировать дополнительные дочерние действия будет проигнорирована, и действие будет отмечено как <xref:System.Activities.ActivityInstanceState.Canceled>. Если любое ожидающее обработки дочернее действие завершится в состоянии <xref:System.Activities.ActivityInstanceState.Canceled> или <xref:System.Activities.ActivityInstanceState.Faulted>, то действие будет отмечено как <xref:System.Activities.ActivityInstanceState.Canceled>. Следует отметить, что запрос отмены может быть проигнорирован. Если действие не имеет ожидающих обработки закладок или выполняющихся дочерних действий, а также не планирует никаких дополнительных элементов работы после того, как оно было отмечено для отмены, то оно завершится успешно. Эта предусмотренная по умолчанию логика отмены является приемлемой для многих сценариев, но если потребуется дополнительная логика отмены, то могут использоваться встроенные действия отмены или пользовательские действия.  
  
 В следующем примере метод <xref:System.Activities.NativeActivity.Cancel%2A> переопределяет пользовательское действие <xref:System.Activities.NativeActivity>, основанное на действии `ParallelForEach`. Если действие отменяется, это переопределение отрабатывает логику отмены для действия. Этот пример является частью образца [ParallelForEach.](./samples/non-generic-parallelforeach.md)  
  
```csharp  
protected override void Cancel(NativeActivityContext context)  
{  
    // If we do not have a completion condition then we can just  
    // use default logic.  
    if (this.CompletionCondition == null)  
    {  
        base.Cancel(context);  
    }  
    else  
    {  
        context.CancelChildren();  
    }  
}  
```  
  
 Производные действия <xref:System.Activities.NativeActivity> могут определять, запрошена ли отмена, проверяя значение свойства <xref:System.Activities.NativeActivityContext.IsCancellationRequested%2A>, и помечать себя как отмененные действия, вызывая метод <xref:System.Activities.NativeActivityContext.MarkCanceled%2A>. Вызов метода <xref:System.Activities.NativeActivityContext.MarkCanceled%2A> не приводит к немедленному завершению действия. Как обычно, среда выполнения завершит действие, когда у него не останется больше ожидающей выполнения работы, но если вызывается метод <xref:System.Activities.NativeActivityContext.MarkCanceled%2A>, то конечным состоянием будет <xref:System.Activities.ActivityInstanceState.Canceled>, а не <xref:System.Activities.ActivityInstanceState.Closed>.  
  
### <a name="cancellation-using-asynccodeactivity"></a>Отмена с помощью AsyncCodeActivity  
 Действия, основанные на действии <xref:System.Activities.AsyncCodeActivity>, также могут предоставлять пользовательскую логику отмены путем переопределения метода <xref:System.Activities.AsyncCodeActivity.Cancel%2A>. Если этот метод не переопределен, то при отмене действия не выполняется никакая обработка отмены. В следующем примере определяется переопределение пользовательского действия <xref:System.Activities.AsyncCodeActivity.Cancel%2A>, основанного на действии <xref:System.Activities.AsyncCodeActivity> методом `ExecutePowerShell`. Если действие отменяется, оно реализует желаемое поведение отмены.
  
 [!code-csharp[CFX_WorkflowApplicationExample#1020](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1020)]  
  
 Производные действия <xref:System.Activities.AsyncCodeActivity> могут определять, запрошена ли отмена, проверяя значение свойства <xref:System.Activities.AsyncCodeActivityContext.IsCancellationRequested%2A>, и помечать себя как отмененные действия, вызывая метод <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>.
