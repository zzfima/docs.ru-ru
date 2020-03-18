---
title: Обработка исключений (библиотека параллельных задач)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
ms.openlocfilehash: 12777a5f34b8aadcc80977b8796fc2cd53c626a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73134253"
---
# <a name="exception-handling-task-parallel-library"></a>Обработка исключений (библиотека параллельных задач)

Необработанные исключения, создаваемые пользовательским кодом, который выполняется в задаче, распространяются обратно в вызывающий поток, за исключением отдельных сценариев, описанных далее в этом разделе. Исключения распространяются, если вы вызываете один из статических или методов экземпляра <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> и заключаете этот вызов в инструкцию `try`/`catch`. Если задача является родительской для присоединенных дочерних задач или если вы ожидаете несколько задач, может быть создано несколько исключений.

Чтобы распространить все исключения обратно в вызывающий поток, инфраструктура задач заключает их в экземпляр <xref:System.AggregateException> . Исключение <xref:System.AggregateException> имеет свойство <xref:System.AggregateException.InnerExceptions%2A> , которое может быть перечислимым для проверки всех созданных исходных исключений и обработки (или отказа от обработки) каждого исключения по отдельности. Вы также можете обрабатывать исходные исключения с помощью метода <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> .

Даже если возникает только одно исключение, оно по-прежнему заключается в исключение <xref:System.AggregateException> , как показано в следующем примере.

[!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
[!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]

Чтобы избежать необработанного исключения, достаточно перехватить <xref:System.AggregateException> и не просматривать какие-либо внутренние исключения. Однако рекомендуется этого не делать, так как это аналог перехвату базового типа <xref:System.Exception> в непараллельных сценариях. Чтобы перехватить исключение без выполнения определенных действий для восстановления из него можно оставить программу в неопределенном состоянии.

Если вы не хотите вызывать метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> для ожидания завершения задачи, можно извлечь исключение <xref:System.AggregateException> из свойства <xref:System.Threading.Tasks.Task.Exception%2A> задачи, как показано в следующем примере. Дополнительные сведения см. в разделе [Выявление исключения с помощью свойства Task.Exception](#observing-exceptions-by-using-the-taskexception-property) в этой статье.

[!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
[!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]

Если вы не ожидаете задачу, распространяющую исключение, или доступа к его свойству <xref:System.Threading.Tasks.Task.Exception%2A> , исключение распространяется согласно политике исключений .NET после удаления задачи сборкой мусора.

Если исключения могут всплывать обратно в присоединяемый поток, задача может продолжить обработку некоторых элементов после создания исключения.

> [!NOTE]
> Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5 для продолжения и увидеть поведение обработки исключения, которое демонстрируется в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок **Включить только мой код** в меню **Сервис, Параметры, Отладка, Общие**.

## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a>Присоединенные дочерние задачи и вложенные исключения AggregateException

Если задача имеет присоединенную дочернюю задачу, которая создает исключение, это исключение заключается в <xref:System.AggregateException> перед распространением в родительскую задачу, которая заключает его в собственное исключение <xref:System.AggregateException> перед распространением обратно в вызывающий поток. В таких случаях свойство <xref:System.AggregateException.InnerExceptions%2A> исключения <xref:System.AggregateException>, перехватываемого в методе <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAny%2A> или <xref:System.Threading.Tasks.Task.WaitAll%2A>, содержит один или несколько экземпляров <xref:System.AggregateException>, а не исходные исключения, которые вызвали сбой. Чтобы избежать необходимости выполнения итерации по вложенным исключениям <xref:System.AggregateException> , можно использовать метод <xref:System.AggregateException.Flatten%2A> для удаления всех вложенных исключений <xref:System.AggregateException> , чтобы свойство <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> содержало исходные исключения. В следующем примере вложенные экземпляры <xref:System.AggregateException> сглаживаются и обрабатываются всего в одном цикле.

[!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
[!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]

Вы также можете использовать метод <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> , чтобы повторно создать внутренние исключения из нескольких экземпляров <xref:System.AggregateException> , вызванные несколькими задачами в одном экземпляре <xref:System.AggregateException> , как показано в следующем примере.

[!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
[!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]

## <a name="exceptions-from-detached-child-tasks"></a>Исключения из отсоединенных дочерних задач

По умолчанию дочерние задачи создаются отсоединенными. Исключения, создаваемые отсоединенными задачами, должны обрабатываться или повторно создаваться в непосредственной родительской задаче; они не распространяются обратно в вызывающий поток тем же способом, как распространяются обратно присоединенные дочерние задачи. Самая верхняя родительская задача может вручную повторно создавать исключение из отсоединенной дочерней задачи, чтобы вызвать его заключение в <xref:System.AggregateException> и распространение обратно в вызывающий поток.

[!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
[!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]

Даже если для выявления исключения в дочерней задаче используется продолжение, исключение по-прежнему должно выявляться родительской задачей.

## <a name="exceptions-that-indicate-cooperative-cancellation"></a>Исключения, указывающие координированную отмену

Когда пользовательский код в задаче отвечает на запрос отмены, правильной процедурой будет создание исключения <xref:System.OperationCanceledException> , передаваемого в токен отмены, с помощью которого был передан запрос. Перед попыткой распространить исключение экземпляр задачи сравнивает токен в исключении с токеном, переданным в него при его создании. Если они совпадают, задача распространяет <xref:System.Threading.Tasks.TaskCanceledException> , заключенное в <xref:System.AggregateException>, и можно увидеть, когда проверяются внутренние исключения. Однако если вызывающий поток не ожидает задачу, это конкретное исключение не будет распространяться. Дополнительные сведения см. в разделе [Отмена задач](../../../docs/standard/parallel-programming/task-cancellation.md).

[!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
[!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]

## <a name="using-the-handle-method-to-filter-inner-exceptions"></a>Использование метода дескриптора для фильтрации внутренних исключений

Вы можете использовать метод <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> для фильтрации исключений, которые можно рассматривать как обработанные без использования какой-либо дальнейшей логики. В пользовательском делегате, предоставленном в метод <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType>, можно проверить тип исключения, его свойство <xref:System.Exception.Message%2A> или другие сведения о нем, которые позволят проверить его безопасность. Любые исключения, для которых делегат возвращает значение `false`, повторно создаются в новом экземпляре <xref:System.AggregateException> сразу после завершения метода <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType>.

Следующий пример выполняет ту же функцию, что и первый пример в этой статье, то есть проверяет каждое исключение в коллекции <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType>.  Но этот обработчик исключений вызывает объект метода <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> для каждого исключения и создает повторно только те исключения, которые не являются экземплярами `CustomException`.

[!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
[!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]

Ниже приведен более полный пример, в котором используется метод <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> для обеспечения специальной обработки исключения <xref:System.UnauthorizedAccessException> при перечислении файлов.

[!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
[!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]

## <a name="observing-exceptions-by-using-the-taskexception-property"></a>Выявление исключения с помощью свойства Task.Exception

Если задача завершается в состоянии <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> , ее свойство <xref:System.Threading.Tasks.Task.Exception%2A> можно проанализировать, чтобы узнать, какое именно исключение вызвало сбой. Хороший способ исследования свойства <xref:System.Threading.Tasks.Task.Exception%2A> заключается в использовании продолжения, которое выполняется только в том случае, если происходит сбой предшествующей задачи, как показано в следующем примере.

[!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
[!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]

В реальном приложении делегат продолжения может записать в журнал подробные сведения об исключении и возможно создать новые задачи для восстановления из исключения.

## <a name="unobservedtaskexception-event"></a>Событие UnobservedTaskException

В некоторых сценариях, например при размещении недоверенных подключаемых модулей, неопасные исключения могут быть общими, и может оказаться слишком сложно вручную выявить их все. В таких случаях можно обрабатывать событие <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType> . Экземпляр <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType>, который передается в обработчик, не позволяет незамеченным исключениям бесконтрольно распространяться обратно в присоединяемый поток.

## <a name="see-also"></a>См. также раздел

- [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
