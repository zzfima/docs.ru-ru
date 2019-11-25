---
title: Отмена в управляемых потоках
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation in .NET, overview
ms.assetid: eea11fe5-d8b0-4314-bb5d-8a58166fb1c3
ms.openlocfilehash: d4bbf30923d65ad7aeced80efa626136ae27491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138139"
---
# <a name="cancellation-in-managed-threads"></a>Отмена в управляемых потоках
В .NET Framework 4 введена новая универсальная модель совместной отмены асинхронных или долго выполняющихся синхронных операций. Эта модель построена на простом объекте, называемом токеном отмены. Объект, который вызывает одну или несколько отменяемых операций, например, путем создания новых потоков или задач, передает этот токен в каждую операцию. Операция, в свою очередь, передает копии этого токена в другие операции. Некоторое время спустя объект, создавший токен, может использовать его для запроса остановки выполнения операции. Запрос на отмену может создавать только запрашивающий объект, и каждый прослушиватель должен обнаружить этот запрос, чтобы правильно и своевременно отреагировать на него.  
  
 Общая схема реализации модели совместной отмены выглядит следующим образом:  
  
- Создается экземпляр объекта <xref:System.Threading.CancellationTokenSource>, который управляет уведомлениями об отмене и передает их отдельным токенам отмены.  
  
- В каждую задачу или поток, ожидающий отмены, передается токен, возвращенный свойством <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType>.  
  
- Каждой задачи или каждому потоку предоставляется механизм реагирования на отмену.  
  
- Вызывается метод <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> для предоставления уведомления об отмене.  
  
> [!IMPORTANT]
> Класс <xref:System.Threading.CancellationTokenSource> реализует интерфейс <xref:System.IDisposable>. По завершении использования источника токена отмены обязательно вызовите метод <xref:System.Threading.CancellationTokenSource.Dispose%2A?displayProperty=nameWithType>, чтобы освободить все занятые неуправляемые ресурсы.  
  
 На рисунке ниже показана связь между источником токена и всеми копиями токена.  
  
 ![CancellationTokenSource и токены отмены](../../../docs/standard/threading/media/vs-cancellationtoken.png "VS_CancellationToken")  
  
 Новая модель отмены упрощает создание приложений и библиотек, поддерживающих отмену. Она также поддерживает перечисленные ниже возможности.  
  
- Отмена является совместной и не осуществляется принудительно на прослушивателе. Прослушиватель сам определяет порядок корректного завершения в ответ на запрос отмены.  
  
- Запрос осуществляется отдельно от прослушивания. Объект, который вызывает отменяемую операцию, может управлять временем создания запроса отмены (а также самим фактом создания подобного запроса).  
  
- Запрашивающий объект создает запрос на отмену для всех копий токена, используя только один вызов метода.  
  
- Прослушиватель может одновременно ожидать несколько маркеров, объединив их в один *связанный маркер*.  
  
- Пользовательский код может отслеживать запросы на отмену из кода библиотеки и реагировать на них, а код библиотеки, в свою очередь, может отслеживать запросы на отмену из пользовательского кода и реагировать на них.  
  
- Для уведомления прослушивателей о запросах на отмену может использоваться опрос, регистрация обратных вызовов или ожидание дескрипторов ожидания.  
  
## <a name="cancellation-types"></a>Типы отмены  
 Инфраструктура отмены реализована в виде набора связанных типов, приведенных в таблице ниже.  
  
|Имя типа|ОПИСАНИЕ|  
|---------------|-----------------|  
|<xref:System.Threading.CancellationTokenSource>|Объект, который создает токен отмены и запрос на отмену для всех копий этого токена.|  
|<xref:System.Threading.CancellationToken>|Простой тип значения, передаваемый одному или нескольким прослушивателям, обычно в виде параметра метода. Прослушиватели отслеживают значение свойства `IsCancellationRequested` токена посредством опроса, обратного вызова или дескриптора ожидания.|  
|<xref:System.OperationCanceledException>|Перегрузки конструктора этого исключения принимают <xref:System.Threading.CancellationToken> в качестве параметра. Прослушиватели могут также создавать это исключение для проверки источника отмены и уведомления остальных прослушивателей об ответе на запрос отмены.|  
  
 Новая модель отмены интегрирована в несколько типов .NET Framework. Наиболее важные из них — <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> и <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>. Мы рекомендуем использовать именно эту новую модель отмены в коде всех новых библиотек и приложений.  
  
## <a name="code-example"></a>Пример кода  
 В примере ниже запрашивающий объект создает объект <xref:System.Threading.CancellationTokenSource>, а затем передает его свойство <xref:System.Threading.CancellationTokenSource.Token%2A> в отменяемую операцию. Операция, получающая запрос, отслеживает значение свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> токена путем опроса. Когда свойство принимает значение `true`, прослушиватель может завершить операцию любым приемлемым способом. В этом примере просто выполняется выход из метода. Во многих случаях этого достаточно.  
  
> [!NOTE]
> В этом примере метод <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> используется для демонстрации совместимости новой инфраструктуры отмены с устаревшими интерфейсами API. Пример, в котором используется новый предпочтительный тип <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, см. в разделе [Руководство. Отмена задачи и ее дочерних элементов](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
 [!code-csharp[Cancellation#1](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex1.cs#1)]
 [!code-vb[Cancellation#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex1.vb#1)]  
  
## <a name="operation-cancellation-versus-object-cancellation"></a>Отмена операции и отмена объекта  
 В рамках новой инфраструктуры отмены осуществляется отмена операций, а не объектов. Запрос на отмену означает, что операция должна быть остановлена как можно скорее после выполнения всех необходимых очисток. Один токен отмены должен относиться к одной отменяемой операции, однако эта операция может быть реализована в программе. После того как свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> токена примет значение `true`, для него невозможно будет восстановить значение `false`. Поэтому токены отмены нельзя использовать повторно после отмены.  
  
 Если вам необходим механизм отмены объектов, его можно построить на основе механизма отмены операций путем вызова метода <xref:System.Threading.CancellationToken.Register%2A?displayProperty=nameWithType>, как показано в примере ниже.  
  
 [!code-csharp[Cancellation#2](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/objectcancellation1.cs#2)]
 [!code-vb[Cancellation#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/objectcancellation1.vb#2)]  
  
 Если объект поддерживает несколько параллельных отменяемых операций, в каждую отменяемую операцию следует передавать отдельный токен. Это позволяет отменить одну операцию, не затрагивая при этом остальные.  
  
## <a name="listening-and-responding-to-cancellation-requests"></a>Прослушивание запросов на отмену и ответ на них  
 Объект, реализующий отменяемую операцию, в пользовательском делегате определяет способ завершения операции в ответ на запрос отмены. Во многих случаях пользовательский делегат может выполнить необходимую очистку, а затем немедленный возврат.  
  
 Однако в более сложных случаях может потребоваться, чтобы пользовательский делегат уведомлял код библиотеки об отмене. В таких случаях, чтобы правильно завершить операцию, следует вызвать из делегата метод <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, который создает исключение <xref:System.OperationCanceledException>. Код библиотеки может перехватить это исключение в потоке пользовательского делегата и проверить токен исключения, чтобы определить, указывает ли исключение на совместную отмену или возникновение другой исключительной ситуации.  
  
 Класс <xref:System.Threading.Tasks.Task> обрабатывает <xref:System.OperationCanceledException> таким образом. Дополнительные сведения см. в разделе [Отмена задач](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
### <a name="listening-by-polling"></a>Прослушивание с помощью опросов  
 Для длительных циклических или рекурсивных вычислений можно прослушивать запрос на отмену путем периодического опроса значения свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A?displayProperty=nameWithType>. Если его значение равно `true`, метод должен максимально быстро выполнить очистку и завершение. Оптимальная частота опроса зависит от типа приложения. Разработчик должен определить оптимальную частоту опроса для конкретной программы. Сам по себе опрос не оказывает значительного влияния на производительность. В примере ниже показан один из возможных способов опроса.  
  
 [!code-csharp[Cancellation#3](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#3)]
 [!code-vb[Cancellation#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#3)]  
  
 Более полный пример см. в подразделе [Практическое руководство. Прослушивание запросов на отмену посредством опросов](../../../docs/standard/threading/how-to-listen-for-cancellation-requests-by-polling.md).  
  
### <a name="listening-by-registering-a-callback"></a>Прослушивание путем регистрации обратного вызова  
 Некоторые операции могут быть заблокированы таким образом, при котором невозможно своевременно проверить значение токена отмены. В этих случаях можно зарегистрировать метод обратного вызова, который разблокирует метод при получении запроса на отмену.  
  
 Метод <xref:System.Threading.CancellationToken.Register%2A> возвращает объект <xref:System.Threading.CancellationTokenRegistration>, который используется специально в этих целях. В примере ниже показано, как использовать метод <xref:System.Threading.CancellationToken.Register%2A> для отмены асинхронного веб-запроса.  
  
 [!code-csharp[Cancellation#4](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex4.cs#4)]
 [!code-vb[Cancellation#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex4.vb#4)]  
  
 Объект <xref:System.Threading.CancellationTokenRegistration> управляет синхронизацией потока и обеспечивает прекращение выполнения обратного вызова в определенный момент времени.  
  
 Чтобы обеспечить отклик системы и предотвратить взаимоблокировки, при регистрации обратных вызовов необходимо следовать приведенным ниже рекомендациям.  
  
- Метод обратного вызова должен быть быстрым, так как он вызывается синхронно и поэтому возврат вызова <xref:System.Threading.CancellationTokenSource.Cancel%2A> будет выполнен после возврата из функции обратного вызова.  
  
- Если вы вызываете <xref:System.Threading.CancellationTokenRegistration.Dispose%2A> во время выполнения обратного вызова и удерживаете блокировку, которую ожидает функция обратного вызова, в программе может произойти взаимоблокировка. После завершения работы метода `Dispose` можно освобождать любые ресурсы, которые необходимы для обратного вызова.  
  
- Обратные вызовы не должны обрабатывать какие-либо ручные потоки или использовать <xref:System.Threading.SynchronizationContext> в обратном вызове. Если обратный вызов должен выполняться в определенном потоке, используйте конструктор <xref:System.Threading.CancellationTokenRegistration?displayProperty=nameWithType>, который позволяет задать активный объект <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> в качестве целевого объекта syncContext. Выполнение ручного потока в обратном вызове может привести к взаимоблокировке.  
  
 Более полный пример см. в подразделе [Практическое руководство. Регистрация обратных вызовов для запросов на отмену](../../../docs/standard/threading/how-to-register-callbacks-for-cancellation-requests.md).  
  
### <a name="listening-by-using-a-wait-handle"></a>Прослушивание с помощью дескриптора ожидания  
 В случаях, когда отменяемая операция может блокироваться на время ожидания примитива синхронизации, такого как <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> или <xref:System.Threading.Semaphore?displayProperty=nameWithType>, можно с помощью свойства <xref:System.Threading.CancellationToken.WaitHandle%2A?displayProperty=nameWithType> включить ожидание операцией как этого события, так и запроса на отмену. Дескриптору ожидания токена отмены будет отправлен сигнал в ответ на запрос отмены, и метод сможет с помощью возвращаемого значения метода <xref:System.Threading.WaitHandle.WaitAny%2A> определить, был ли этот сигнал отправлен токеном отмены. Затем операция может выполнить выход или создать исключение <xref:System.OperationCanceledException> в зависимости от ситуации.  
  
 [!code-csharp[Cancellation#5](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#5)]
 [!code-vb[Cancellation#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#5)]  
  
 В новом коде, предназначенном для .NET Framework 4, классы <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> и <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> обеспечивают поддержку новой инфраструктуры отмены в методах `Wait`. Вы можете передать этому методу <xref:System.Threading.CancellationToken>, и тогда это событие активируется и создает исключение <xref:System.OperationCanceledException>, когда поступает запрос на отмену.  
  
 [!code-csharp[Cancellation#6](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#6)]
 [!code-vb[Cancellation#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#6)]  
  
 Более полный пример см. в подразделе [Практическое руководство. Прослушивание запросов на отмену, содержащих дескрипторы ожидания](../../../docs/standard/threading/how-to-listen-for-cancellation-requests-that-have-wait-handles.md).  
  
### <a name="listening-to-multiple-tokens-simultaneously"></a>Одновременное прослушивание нескольких токенов  
 В некоторых случаях прослушивателю может требоваться одновременного прослушивать несколько токенов отмены. Например, отменяемая операция может в дополнение к токену отмены, переданному извне в качестве аргумента в параметр метода, отслеживать также внутренний токен отмены. Для этого создайте источник связанных токенов, который может объединять два или более токенов в один, как показано в примере ниже.  
  
 [!code-csharp[Cancellation#7](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#7)]
 [!code-vb[Cancellation#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#7)]  
  
 Следует отметить, что после выполнения источником связанных токенов всех возложенных на него функций необходимо вызвать для него метод `Dispose`. Более полный пример см. в подразделе [Практическое руководство. Прослушивание нескольких запросов на отмену](../../../docs/standard/threading/how-to-listen-for-multiple-cancellation-requests.md).  
  
## <a name="cooperation-between-library-code-and-user-code"></a>Совместная работа кода библиотеки и пользовательского кода  
 Унифицированная инфраструктура отмены позволяет коду библиотеки отменять пользовательский код, а пользовательскому коду — отменять код библиотеки по принципу совместной работы. Успешная совместная работа зависит от соблюдения каждой стороной перечисленных ниже рекомендаций.  
  
- Если код библиотеки предоставляет отменяемые операции, он также должен предоставить общие методы, принимающие внешний токен отмены, чтобы пользовательский код мог запрашивать отмену.  
  
- Если код библиотеки вызывает пользовательский код, он должен уметь обрабатывать исключение OperationCanceledException(externalToken) как *совместную отмену*, а не только как исключение сбоя.  
  
- Пользовательские делегаты должны пытаться своевременно отвечать на запросы отмены от кода библиотеки.  
  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> и <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> — примеры классов, соответствующих этим рекомендациям. Дополнительные сведения см. в разделах [Отмена задач](../../../docs/standard/parallel-programming/task-cancellation.md) и [Практическое руководство. Отмена запроса PLINQ](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md).  
  
## <a name="see-also"></a>См. также

- [Основы управляемых потоков](../../../docs/standard/threading/managed-threading-basics.md)
