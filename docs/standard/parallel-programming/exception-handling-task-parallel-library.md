---
title: "Обработка исключений (библиотека параллельных задач)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e62498376d321d8ff22a53315b9d5f18a8865056
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling-task-parallel-library"></a>Обработка исключений (библиотека параллельных задач)
Необработанные исключения, создаваемые пользовательским кодом, который выполняется в задаче, распространяются обратно в вызывающий поток, за исключением отдельных сценариев, описанных далее в этом разделе. Исключения распространяются при использовании одного из статических или экземпляр <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> или <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` методов и вы обрабатываете их путем заключения вызова в `try` / `catch` инструкции. Если задача является родительской для присоединенных дочерних задач или если вы ожидаете несколько задач, может быть создано несколько исключений.  
  
 Чтобы распространить все исключения обратно в вызывающий поток, инфраструктура задач заключает их в экземпляр <xref:System.AggregateException> . Исключение <xref:System.AggregateException> имеет свойство <xref:System.AggregateException.InnerExceptions%2A> , которое может быть перечислимым для проверки всех созданных исходных исключений и обработки (или отказа от обработки) каждого исключения по отдельности. Также можно обрабатывать исходные исключения с помощью <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> метод.  
  
 Даже если возникает только одно исключение, оно по-прежнему заключается в исключение <xref:System.AggregateException> , как показано в следующем примере.  
  
 [!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
 [!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]  
  
 Чтобы избежать необработанного исключения, достаточно перехватить <xref:System.AggregateException> и не просматривать какие-либо внутренние исключения. Однако рекомендуется этого не делать, так как это аналог перехвату базового типа <xref:System.Exception> в непараллельных сценариях. Чтобы перехватить исключение без выполнения определенных действий для восстановления из него можно оставить программу в неопределенном состоянии.  
  
 Если вы не хотите вызывать <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> или <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` метод для ожидания завершения задачи вы также можете получить <xref:System.AggregateException> исключение из задачи <xref:System.Threading.Tasks.Task.Exception%2A> свойства, как показано в следующем примере. Дополнительные сведения см. в разделе [Выявление исключения с помощью свойства Task.Exception](#ExceptionProp) в этой статье.  
  
 [!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
 [!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]  
  
 Если вы не ожидаете задачу, распространяющую исключение, или доступа к его свойству <xref:System.Threading.Tasks.Task.Exception%2A> , исключение распространяется согласно политике исключений .NET после удаления задачи сборкой мусора.  
  
 Если исключения могут всплывать обратно в присоединяемый поток, задача может продолжить обработку некоторых элементов после создания исключения.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5 для продолжения и увидеть поведение обработки исключения, которое демонстрируется в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок **Включить только мой код** в меню **Сервис, Параметры, Отладка, Общие**.  
  
## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a>Присоединенные дочерние задачи и вложенные исключения AggregateException  
 Если задача имеет присоединенную дочернюю задачу, которая создает исключение, это исключение заключается в <xref:System.AggregateException> перед распространением в родительскую задачу, которая заключает его в собственное исключение <xref:System.AggregateException> перед распространением обратно в вызывающий поток. В таких случаях <xref:System.AggregateException.InnerExceptions%2A> свойство <xref:System.AggregateException> исключение перехватывается в <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> или <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` или <xref:System.Threading.Tasks.Task.WaitAny%2A> или <xref:System.Threading.Tasks.Task.WaitAll%2A> метод содержит один или несколько <xref:System.AggregateException> экземпляров не исходные исключения, которые вызвали сбой. Чтобы избежать необходимости выполнения итерации по вложенным <xref:System.AggregateException> исключения, можно использовать <xref:System.AggregateException.Flatten%2A> метод для удаления всех вложенных <xref:System.AggregateException> исключения, чтобы <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> свойство содержало исходные исключения. В следующем примере вложенные экземпляры <xref:System.AggregateException> сглаживаются и обрабатываются всего в одном цикле.  
  
 [!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
 [!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]  
  
 Можно также использовать <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> метод, чтобы повторно создать внутренние исключения из нескольких <xref:System.AggregateException> экземпляров, вызванные несколькими задачами в одном <xref:System.AggregateException> экземпляра, как показано в следующем примере.  
  
 [!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
 [!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]  
  
## <a name="exceptions-from-detached-child-tasks"></a>Исключения из отсоединенных дочерних задач  
 По умолчанию дочерние задачи создаются отсоединенными. Исключения, создаваемые отсоединенными задачами, должны обрабатываться или повторно создаваться в непосредственной родительской задаче; они не распространяются обратно в вызывающий поток тем же способом, как распространяются обратно присоединенные дочерние задачи. Самая верхняя родительская задача может вручную повторно создавать исключение из отсоединенной дочерней задачи, чтобы вызвать его заключение в <xref:System.AggregateException> и распространение обратно в вызывающий поток.  
  
 [!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
 [!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]  
  
 Даже если для выявления исключения в дочерней задаче используется продолжение, исключение по-прежнему должно выявляться родительской задачей.  
  
## <a name="exceptions-that-indicate-cooperative-cancellation"></a>Исключения, указывающие координированную отмену  
 Когда пользовательский код в задаче отвечает на запрос отмены, правильной процедурой будет создание исключения <xref:System.OperationCanceledException> , передаваемого в токен отмены, с помощью которого был передан запрос. Перед попыткой распространить исключение экземпляр задачи сравнивает токен в исключении с токеном, переданным в него при его создании. Если они совпадают, задача распространяет <xref:System.Threading.Tasks.TaskCanceledException> , заключенное в <xref:System.AggregateException>, и можно увидеть, когда проверяются внутренние исключения. Однако если вызывающий поток не ожидает задачу, это конкретное исключение не будет распространяться. Для получения дополнительной информации см. [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
 [!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
 [!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]  
  
## <a name="using-the-handle-method-to-filter-inner-exceptions"></a>Использование метода дескриптора для фильтрации внутренних исключений  
 Можно использовать <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> метода для фильтрации исключений, которые можно рассматривать как «обработано» без использования любой дальнейшей логики. В пользовательском делегате, предоставленном <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> метод, можно проверить тип исключения, его <xref:System.Exception.Message%2A> свойства или другие сведения о нем, позволяющий определить, является ли информационный характер. Любые исключения, для которых делегат возвращает `false` , повторно создаются в новом <xref:System.AggregateException> экземпляр сразу же после <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> возвращает метод.  
  
 Следующий пример является функциональным эквивалентом первого примера в этой статье, который проверяет каждое исключение в <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> коллекции.  Вместо этого данный обработчик исключений вызывает <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> объект метода для каждого исключения и только повторно создает исключения, которые не являются `CustomException` экземпляров.  
  
 [!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
 [!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]  
  
 Ниже приведен более полный пример, использующий <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> метод, чтобы выполнить специальную обработку <xref:System.UnauthorizedAccessException> исключение при перечислении файлов.  
  
 [!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
 [!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]  
  
<a name="ExceptionProp"></a>   
## <a name="observing-exceptions-by-using-the-taskexception-property"></a>Выявление исключения с помощью свойства Task.Exception  
 Если задача завершается в <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> состояние, его <xref:System.Threading.Tasks.Task.Exception%2A> свойства можно проанализировать, чтобы узнать, какое именно исключение вызвало сбой. Хороший способ исследования свойства <xref:System.Threading.Tasks.Task.Exception%2A> заключается в использовании продолжения, которое выполняется только в том случае, если происходит сбой предшествующей задачи, как показано в следующем примере.  
  
 [!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
 [!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]  
  
 В реальном приложении делегат продолжения может записать в журнал подробные сведения об исключении и возможно создать новые задачи для восстановления из исключения.  
  
## <a name="unobservedtaskexception-event"></a>Событие UnobservedTaskException  
 В некоторых сценариях, например при размещении недоверенных подключаемых модулей, неопасные исключения могут быть общими, и может оказаться слишком сложно вручную выявить их все. В таких случаях можно обрабатывать <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType> событий. <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType> Экземпляр, который передается в обработчик может использоваться для предотвращения распространения незамеченного исключения распространяются обратно в присоединяемый поток.  
  
## <a name="see-also"></a>См. также  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
