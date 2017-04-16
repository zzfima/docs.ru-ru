---
title: "Обработка исключений (библиотека параллельных задач) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "задачи, исключения"
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Обработка исключений (библиотека параллельных задач)
Необработанные исключения, создаваемые пользовательским кодом, который выполняется в задаче, распространяются обратно в вызывающий поток, за исключением отдельных сценариев, описанных далее в этом разделе. Исключения распространяются при использовании одного из статических методов или методов экземпляра <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> или <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=fullName>, и вы обрабатываете их путем заключения вызова в инструкцию `try`\/`catch`. Если задача является родительской для присоединенных дочерних задач или если вы ожидаете несколько задач, может быть создано несколько исключений.  
  
 Чтобы распространить все исключения обратно в вызывающий поток, инфраструктура задач заключает их в экземпляр <xref:System.AggregateException>. Исключение <xref:System.AggregateException> имеет свойство <xref:System.AggregateException.InnerExceptions%2A>, которое может быть перечислимым для проверки всех созданных исходных исключений и обработки \(или отказа от обработки\) каждого исключения по отдельности. Вы также можете обрабатывать исходные исключения с помощью метода <xref:System.AggregateException.Handle%2A?displayProperty=fullName>.  
  
 Даже если возникает только одно исключение, оно по\-прежнему заключается в исключение <xref:System.AggregateException>, как показано в следующем примере.  
  
 [!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
 [!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]  
  
 Чтобы избежать необработанного исключения, достаточно перехватить <xref:System.AggregateException> и не просматривать какие\-либо внутренние исключения. Однако рекомендуется этого не делать, так как это аналог перехвату базового типа <xref:System.Exception> в непараллельных сценариях. Чтобы перехватить исключение без выполнения определенных действий для восстановления из него можно оставить программу в неопределенном состоянии.  
  
 Если вы не хотите вызывать метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> или <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=fullName> для ожидания завершения задачи, можно также извлечь исключение <xref:System.AggregateException> из свойства <xref:System.Threading.Tasks.Task.Exception%2A> задачи, как показано в следующем примере. Дополнительные сведения см. в разделе [Выявление исключения с помощью свойства Task.Exception](#ExceptionProp) в этой статье.  
  
 [!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
 [!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]  
  
 Если вы не ожидаете задачу, распространяющую исключение, или доступа к его свойству <xref:System.Threading.Tasks.Task.Exception%2A>, исключение распространяется согласно политике исключений .NET после удаления задачи сборкой мусора.  
  
 Если исключения могут всплывать обратно в присоединяемый поток, задача может продолжить обработку некоторых элементов после создания исключения.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5 для продолжения и увидеть поведение обработки исключения, которое демонстрируется в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок **Включить только мой код** в меню **Сервис, Параметры, Отладка, Общие**.  
  
## Присоединенные дочерние задачи и вложенные исключения AggregateException  
 Если задача имеет присоединенную дочернюю задачу, которая создает исключение, это исключение заключается в <xref:System.AggregateException> перед распространением в родительскую задачу, которая заключает его в собственное исключение <xref:System.AggregateException> перед распространением обратно в вызывающий поток. В таких случаях свойство <xref:System.AggregateException.InnerExceptions%2A> исключения <xref:System.AggregateException>, перехватываемого в методе <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.WaitAny%2A> или <xref:System.Threading.Tasks.Task.WaitAll%2A>, содержит один или несколько экземпляров <xref:System.AggregateException>, а не исходные исключения, которые вызвали сбой. Чтобы избежать необходимости выполнения итерации по вложенным исключениям <xref:System.AggregateException>, можно использовать метод <xref:System.AggregateException.Flatten%2A> для удаления всех вложенных исключений <xref:System.AggregateException>, чтобы свойство <xref:System.AggregateException.InnerExceptions%2A?displayProperty=fullName> содержало исходные исключения. В следующем примере вложенные экземпляры <xref:System.AggregateException> сглаживаются и обрабатываются всего в одном цикле.  
  
 [!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
 [!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]  
  
 Вы также можете использовать метод <xref:System.AggregateException.Flatten%2A?displayProperty=fullName>, чтобы повторно создать внутренние исключения из нескольких экземпляров <xref:System.AggregateException>, вызванные несколькими задачами в одном экземпляре <xref:System.AggregateException>, как показано в следующем примере.  
  
 [!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
 [!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]  
  
## Исключения из отсоединенных дочерних задач  
 По умолчанию дочерние задачи создаются отсоединенными. Исключения, создаваемые отсоединенными задачами, должны обрабатываться или повторно создаваться в непосредственной родительской задаче; они не распространяются обратно в вызывающий поток тем же способом, как распространяются обратно присоединенные дочерние задачи. Самая верхняя родительская задача может вручную повторно создавать исключение из отсоединенной дочерней задачи, чтобы вызвать его заключение в <xref:System.AggregateException> и распространение обратно в вызывающий поток.  
  
 [!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
 [!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]  
  
 Даже если для выявления исключения в дочерней задаче используется продолжение, исключение по\-прежнему должно выявляться родительской задачей.  
  
## Исключения, указывающие координированную отмену  
 Когда пользовательский код в задаче отвечает на запрос отмены, правильной процедурой будет создание исключения <xref:System.OperationCanceledException>, передаваемого в токен отмены, с помощью которого был передан запрос. Перед попыткой распространить исключение экземпляр задачи сравнивает токен в исключении с токеном, переданным в него при его создании. Если они совпадают, задача распространяет <xref:System.Threading.Tasks.TaskCanceledException>, заключенное в <xref:System.AggregateException>, и можно увидеть, когда проверяются внутренние исключения. Однако если вызывающий поток не ожидает задачу, это конкретное исключение не будет распространяться. Для получения дополнительной информации см. [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
 [!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
 [!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]  
  
## Использование метода дескриптора для фильтрации внутренних исключений  
 Вы можете использовать метод <xref:System.AggregateException.Handle%2A?displayProperty=fullName> для фильтрации исключений, которые можно рассматривать как обработанные без использования какой\-либо дальнейшей логики. В пользовательском делегате, предоставленном в метод <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=fullName>, можно проверить тип исключения, его свойство <xref:System.Exception.Message%2A> или другие сведения о нем, которые позволят определить, является ли оно безопасным. Любые исключения, для которых делегат возвращает значение `false`, повторно создаются в новом экземпляре <xref:System.AggregateException> сразу после возврата метода <xref:System.AggregateException.Handle%2A?displayProperty=fullName>.  
  
 Следующий пример является функциональным эквивалентом первого примера в этой статье, который проверяет каждое исключение в коллекции <xref:System.AggregateException.InnerExceptions%2A?displayProperty=fullName>.  Вместо этого данный обработчик исключений вызывает метод <xref:System.AggregateException.Handle%2A?displayProperty=fullName> для каждого исключения и только повторно создает исключения, не являющиеся экземплярами `CustomException`.  
  
 [!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
 [!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]  
  
 Ниже приведен более полный пример, в котором используется метод <xref:System.AggregateException.Handle%2A?displayProperty=fullName> для обеспечения специальной обработки исключения <xref:System.UnauthorizedAccessException> при перечислении файлов.  
  
 [!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
 [!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]  
  
<a name="ExceptionProp"></a>   
## Выявление исключений с помощью свойства Task.Exception  
 Если задача завершается в состоянии <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>, ее свойство <xref:System.Threading.Tasks.Task.Exception%2A> можно проанализировать, чтобы узнать, какое именно исключение вызвало сбой. Хороший способ исследования свойства <xref:System.Threading.Tasks.Task.Exception%2A> заключается в использовании продолжения, которое выполняется только в том случае, если происходит сбой предшествующей задачи, как показано в следующем примере.  
  
 [!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
 [!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]  
  
 В реальном приложении делегат продолжения может записать в журнал подробные сведения об исключении и возможно создать новые задачи для восстановления из исключения.  
  
## Событие UnobservedTaskException  
 В некоторых сценариях, например при размещении недоверенных подключаемых модулей, неопасные исключения могут быть общими, и может оказаться слишком сложно вручную выявить их все. В таких случаях можно обрабатывать событие <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>. Экземпляр <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=fullName>, который передается в обработчик, может использоваться для предотвращения распространения незамеченного исключения обратно в присоединяемый поток.  
  
## См. также  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)