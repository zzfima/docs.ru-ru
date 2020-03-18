---
title: Асинхронный шаблон, основанный на задачах (TAP)
ms.date: 02/26/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 8cef1fcf-6f9f-417c-b21f-3fd8bac75007
ms.openlocfilehash: 89c486618729c334bf74f0a1f4f9dd1b3cee8b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78158172"
---
# <a name="task-based-asynchronous-pattern-tap"></a>Асинхронный шаблон, основанный на задачах (TAP)
Асинхронная модель на основе задач (TAP) основана на типах <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> пространства имен <xref:System.Threading.Tasks?displayProperty=nameWithType>, которые используются для представления произвольных асинхронных операций. TAP — это рекомендуемый асинхронный шаблон для разработки новых компонентов.  
  
## <a name="naming-parameters-and-return-types"></a>Именование, параметры и возвращаемые типы

TAP использует один метод для представления инициализации и завершения асинхронной операции. Это отличается от шаблона модели асинхронного программирования (APM или `IAsyncResult`) и асинхронного шаблона, основанного на событиях (EAP). Для APM требуется метод `Begin` и `End`. Для EAP требуется метод с суффиксом `Async`, а также одно или несколько событий, типов делегата обработчика событий и производные от `EventArg` типы. В асинхронных методах TAP после имени операции используется суффикс `Async` — для методов, возвращающих типы с поддержкой ожидания, например <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> и <xref:System.Threading.Tasks.ValueTask%601>. Синхронные операции `Get`, возвращающие `Task<String>`, могут называться `GetAsync`. Если вы добавляете к классу, который уже содержит имя метода EAP с суффиксом `Async`, метод TAP, используйте вместо него суффикс `TaskAsync`. Например, класс уже содержит метод `GetAsync`, используйте имя `GetTaskAsync`. Если метод запускает асинхронную операцию, но не возвращает ожидаемый тип, его имя должно начинаться с `Begin`, `Start` или другого глагола, который указывает на то, что этот метод не возвращает или не выдает результат операции.  
  
 Метод TAP возвращает <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> в зависимости от того, возвращает ли соответствующий синхронный метод значение void или тип `TResult`.  
  
 Параметры метода TAP должны соответствовать параметрам его синхронного аналога и предоставляться в том же порядке.  Однако параметры `out` и `ref` исключены из этого правила, их следует избегать полностью. Все данные, которые были бы возвращены параметром `out` или `ref`, должны вместо этого возвращаться как часть результата `TResult`, возвращаемого <xref:System.Threading.Tasks.Task%601>, и должны использовать кортеж или пользовательскую структуру данных, чтобы вместить несколько значений. Попробуйте добавить параметр <xref:System.Threading.CancellationToken>, даже если в аналогичном синхронном методе TAP этот параметр не применяется.

 К методам, которые предназначены исключительно для создания, обработки или сочетания задач (где асинхронная природа метода очевидна из имени метода или имени типа, к которому относится метод), эта схема именования не применяется. Такие методы часто называются *методами объединения*. К таким методам относятся <xref:System.Threading.Tasks.Task.WhenAll%2A> и <xref:System.Threading.Tasks.Task.WhenAny%2A>, которые рассматриваются в разделе [Использование внутренних блоков объединения задач](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md#combinators) статьи [Использование асинхронного шаблона, основанного на задачах](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).  
  
 Примеры отличий синтаксиса TAP от синтаксиса, используемого в устаревших асинхронных моделях, таких как асинхронная модель программирования (APM) и асинхронная модель на основе событий (EAP), вы найдете в статье [Шаблоны асинхронного программирования](../../../docs/standard/asynchronous-programming-patterns/index.md).  
  
## <a name="initiating-an-asynchronous-operation"></a>Инициализация асинхронной операции  
 Асинхронный метод, основанный на TAP, может выполнить небольшой объем работы синхронно, например проверить аргументы и инициировать асинхронную операцию, прежде чем вернуть результирующую задачу. Синхронная работа должна быть сведена к минимуму, чтобы асинхронный метод мог быстро вернуть значение. Причины быстрого возвращения указаны ниже.  
  
- Асинхронные методы могут вызываться из потоков пользовательского интерфейса, и любые продолжительные синхронные задачи могут негативно сказаться на скорости реагирования приложения.  
  
- Одновременно можно запускать несколько асинхронных методов. Таким образом, любые длительные синхронные фрагменты асинхронного метода могут отложить запуск других асинхронных операций, тем самым сводя к минимуму преимущества параллельности.  
  
 В некоторых случаях объем работы, необходимый для выполнения операции, меньше объема работы, необходимого для асинхронного запуска операции. Примером такой ситуации является чтение из потока, в котором операция чтения может быть выполнена с использованием данных, которые уже сохранены в памяти. В таких случаях операция может выполняться синхронно и может возвращать задачу, которая уже была завершена.  
  
## <a name="exceptions"></a>Исключения  
 Асинхронный метод должен вызывать исключение, которое должно создаваться вызовом асинхронного метода только в ответ на ошибку использования. Ошибки использования никогда не должны происходить в рабочем коде. Например, если передача пустой ссылки (`Nothing` в Visual Basic) в виде одного из аргументов метода вызывает ошибочное состояние (как правило, представляется исключением <xref:System.ArgumentNullException> ), можно изменить вызывающий код, чтобы убедиться, что пустая ссылка никогда не передается. Для всех остальных ошибок исключения, возникающие во время исполнения асинхронного метода, должны относиться к возвращаемой задаче, даже если асинхронный метод выполняется синхронно перед возвращением задачи. Как правило, задача содержит не более одного исключения. Однако если задача представляет множественные операции (например, <xref:System.Threading.Tasks.Task.WhenAll%2A>), с одной задачей может быть связано несколько исключений.  
  
## <a name="target-environment"></a>Целевая среда  
 При реализации метода TAP можно определить, где происходит асинхронное выполнение. Можно выполнить рабочую нагрузку в пуле потоков, реализовать ее с помощью асинхронного ввода-вывода (без привязки к потоку в большей части выполнения операции), выполнить ее в определенном потоке (например, в потоке пользовательского интерфейса) или использовать любое количество потенциальных контекстов. Возможно, у метода TAP не будет задач для выполнения, тогда он просто возвратит <xref:System.Threading.Tasks.Task>, представляющий вхождение условия в другом месте системы (например, задачу с представлением данных, поступающих в структуру данных на основе очереди).

 Вызывающий метода TAP может приостановить работу, ожидая завершения метода TAP путем синхронного ожидания результирующей задачи, или выполнять дополнительный код, продолжающий работу после завершения асинхронной операции. Автор кода продолжения имеет контроль над местом исполнения кода. Можно создать код продолжения явным образом с помощью методов в классе <xref:System.Threading.Tasks.Task> (например, <xref:System.Threading.Tasks.Task.ContinueWith%2A>) или неявно путем поддержки языка на основе продолжений (например, `await` в C#, `Await` в Visual Basic, `AwaitValue` в F#).  
  
## <a name="task-status"></a>Состояние задачи  
 Класс <xref:System.Threading.Tasks.Task> обеспечивает жизненный цикл для асинхронных операций, и этот цикл представлен перечислением <xref:System.Threading.Tasks.TaskStatus>. Для поддержки угловых случаев типов, производных от <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>, и чтобы обеспечить разделение построения и планирования, класс <xref:System.Threading.Tasks.Task> предоставляет метод <xref:System.Threading.Tasks.Task.Start%2A>. Задачи, созданные открытыми конструкторами <xref:System.Threading.Tasks.Task>, называются *холодными задачами*, так как они начинают свой жизненный цикл в незапланированном состоянии <xref:System.Threading.Tasks.TaskStatus.Created>, а их планирование осуществляется только тогда, когда в этих экземплярах вызывается метод <xref:System.Threading.Tasks.Task.Start%2A>.

 Все другие задачи начинают свой жизненный цикл в активном состоянии, то есть асинхронные операции, которые они представляют, уже были инициированы и их статус задачи — это значение перечисления, отличное от <xref:System.Threading.Tasks.TaskStatus.Created?displayProperty=nameWithType>. Необходимо активировать все задачи, возвращаемые методами TAP. **Если внутри метода TAP используется конструктор задачи, создающий экземпляр возвращаемой задачи, метод TAP перед ее возвращением должен вызвать метод <xref:System.Threading.Tasks.Task.Start%2A> для объекта <xref:System.Threading.Tasks.Task>.** Объекты-получатели метода TAP могут с уверенностью допускать, что возвращаемая задача активна, и не пытаться вызвать метод <xref:System.Threading.Tasks.Task.Start%2A> для любого объекта <xref:System.Threading.Tasks.Task>, который возвращается из метода TAP. Вызов метода <xref:System.Threading.Tasks.Task.Start%2A> в активной задаче приводит к исключению <xref:System.InvalidOperationException>.  
  
## <a name="cancellation-optional"></a>Отмена (необязательно)  
 В TAP отмена является необязательной как для асинхронной реализации метода, так и для асинхронных объектов-получателей метода. Если операция позволяет выполнить отмену, она предоставляет перезагрузку асинхронного метода, принимающую токен отмены (экземпляр <xref:System.Threading.CancellationToken>). По правилам этот параметр называется `cancellationToken`.  
  
 [!code-csharp[Conceptual.TAP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#1)]
 [!code-vb[Conceptual.TAP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#1)]  
  
 Асинхронная операция отслеживает этот токен на наличие запросов на отмену. Если операция получает запрос на отмену, системой может быть принято решение об удовлетворении запроса и отмене операции. Если запрос на отмену приводит к преждевременному завершению работы, метод TAP возвращает задачу, которая завершается в состоянии <xref:System.Threading.Tasks.TaskStatus.Canceled>; в этом случае отсутствует результат и исключение не создается.  Состояние <xref:System.Threading.Tasks.TaskStatus.Canceled> считается конечным состоянием для задачи, наравне с состояниями <xref:System.Threading.Tasks.TaskStatus.Faulted> и <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Таким образом, если задача находится в состоянии <xref:System.Threading.Tasks.TaskStatus.Canceled>, ее свойство <xref:System.Threading.Tasks.Task.IsCompleted%2A> возвращает значение `true`. Если задача завершается в состоянии <xref:System.Threading.Tasks.TaskStatus.Canceled>, любые продолжения, зарегистрированные для задачи, планируются или исполняются, если только не был выбран параметр отказа от продолжения, такой как <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled>. Любой код, который асинхронно ожидает отмененной задачи с использованием языковых возможностей, продолжает выполняться, но получает исключение <xref:System.OperationCanceledException> или производное от него исключение. Код, который блокируется во время синхронного ожидания задачи с использованием методов <xref:System.Threading.Tasks.Task.Wait%2A> и <xref:System.Threading.Tasks.Task.WaitAll%2A> также продолжает выполняться с исключением.  
  
 Если токен отмены запросил отмену до вызова метода TAP, принявшего этот токен, метод TAP должен вернуть задачу <xref:System.Threading.Tasks.TaskStatus.Canceled>.  Однако если отмена запрошена во время выполнения асинхронной операции, последней не обязательно принимать запрос на отмену.  Возвращаемая задача должна завершиться в состоянии <xref:System.Threading.Tasks.TaskStatus.Canceled>, только если операция завершается в результате запроса отмены. Если отмена запрошена, но результат или исключение по-прежнему создаются, задача должна завершиться в состоянии <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> или <xref:System.Threading.Tasks.TaskStatus.Faulted>.

 В асинхронных методах, для которых возможность выполнить отмену является обязательным условием, не обязательно предоставлять перегрузку, не принимающую маркер отмены. Для методов, которые не могут быть отменены, не нужно предоставлять перегрузки, принимающие токен отмены; это позволяет указать вызывающему объекту, можно ли в действительности отменить целевой метод.  Код объекта-получателя, в котором отмена является нежелательной, может вызвать метод, который принимает <xref:System.Threading.CancellationToken> и предоставляет <xref:System.Threading.CancellationToken.None%2A> в качестве значения аргумента. <xref:System.Threading.CancellationToken.None%2A> функционально эквивалентен значению по умолчанию <xref:System.Threading.CancellationToken>.  
  
## <a name="progress-reporting-optional"></a>Отчет о ходе выполнения (необязательно)  
 Для некоторых асинхронных операций имеет смысл предоставлять уведомления о ходе выполнения; обычно уведомления используются для обновления информации о выполнении асинхронной операции в пользовательском интерфейсе.

 В TAP ход выполнения контролируется в интерфейсе <xref:System.IProgress%601>, который передается в асинхронный метод в качестве параметра, который обычно называется `progress`.  Предоставление интерфейса для контроля за ходом выполнения при вызове асинхронного метода позволяет избежать состояний гонки, возникающих в результате неправильного использования (т. е. когда обработчики событий, неправильно зарегистрированные после начала операции, пропускают обновления).  Еще более важно то, что интерфейс выполнения поддерживает различные реализации хода выполнения в соответствии с определением в коде-потребителе.  Например, код-потребитель может запрашивать только последнее обновление хода выполнения, пытаться выполнить буферизацию всех обновлений, вызвать действие для каждого обновления или контролировать маршалирование вызова в определенный поток. Все эти варианты могут быть реализованы с использованием иной реализации интерфейса, настроенной в соответствии с требованиями потребителя.  Как и в случае с отменой, реализации TAP должны предоставлять параметр <xref:System.IProgress%601>, только если API поддерживает уведомления о ходе выполнения.

 Например, если метод `ReadAsync`, обсуждаемый ранее в этой статье, может информировать о ходе выполнения в виде считанного количества байтов, обратный вызов хода выполнения может быть представлен интерфейсом <xref:System.IProgress%601>:  
  
 [!code-csharp[Conceptual.TAP#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#2)]
 [!code-vb[Conceptual.TAP#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#2)]  
  
 Если метод `FindFilesAsync` возвращает список всех файлов, соответствующих указанному шаблону поиска, обратный вызов хода выполнения может предоставить оценку процента выполненной работы, а также текущий частичный результат.  Для этого может использоваться кортеж:  
  
 [!code-csharp[Conceptual.TAP#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#3)]
 [!code-vb[Conceptual.TAP#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#3)]  
  
 или тип данных, соответствующий данному API.  
  
 [!code-csharp[Conceptual.TAP#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#4)]
 [!code-vb[Conceptual.TAP#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#4)]  
  
 В последнем случае к специальному типу данных добавляется суффикс `ProgressInfo`.  
  
 Если реализации TAP предоставляют перегрузки, принимающие параметр `progress`, они должны разрешать значение `null` для аргумента. В этом случае о ходе выполнения не сообщается. В реализации TAP необходимо синхронно сообщать информацию о ходе выполнения объекту <xref:System.Progress%601>, что позволит асинхронному методу быстро предоставлять сведения о ходе выполнения, а объекту-получателю этой информации определять, как и где лучше обрабатывать эти данные. Например, экземпляр хода выполнения может маршалировать обратные вызовы и инициировать события для захваченного контекста синхронизации.  
  
## <a name="iprogresst-implementations"></a>Реализации IProgress\<T>  
 .NET Framework 4.5 предоставляет одну реализацию <xref:System.IProgress%601>: <xref:System.Progress%601>. Класс <xref:System.Progress%601>объявляется следующим образом:  
  
```csharp  
public class Progress<T> : IProgress<T>  
{  
    public Progress();  
    public Progress(Action<T> handler);  
    protected virtual void OnReport(T value);  
    public event EventHandler<T> ProgressChanged;  
}  
```  
  
```vb  
Public Class Progress(Of T) : Inherits IProgress(Of T)  
    Public Sub New()  
    Public Sub New(handler As Action(Of T))  
    Protected Overridable Sub OnReport(value As T)  
    Public Event ProgressChanged As EventHandler(Of T>  
End Class  
```  
  
 Экземпляр <xref:System.Progress%601> предоставляет событие <xref:System.Progress%601.ProgressChanged>, которое вызывается каждый раз, когда асинхронная операция сообщает об обновлении хода выполнения. Событие <xref:System.Progress%601.ProgressChanged> вызывается для объекта <xref:System.Threading.SynchronizationContext>, который был захвачен при создании экземпляра <xref:System.Progress%601>. Если контекст синхронизации не был доступен, то используется контекст по умолчанию, предназначенный для пула потоков. Обработчики могут быть зарегистрированы при помощи этого события. Один обработчик также может предоставляться конструктору <xref:System.Progress%601> для удобства. Он работает точно так же, как обработчик события <xref:System.Progress%601.ProgressChanged>. Обновления хода выполнения вызываются асинхронно, чтобы избежать задержки асинхронной операции при выполнении обработчиков событий. В другой реализации <xref:System.IProgress%601> может применяться другая семантика.  
  
## <a name="choosing-the-overloads-to-provide"></a>Выбор перегрузок для предоставления  
 Если реализация TAP использует необязательные параметры <xref:System.Threading.Tasks.TaskFactory.CancellationToken%2A> и <xref:System.IProgress%601>, потенциально может потребоваться до четырех перегрузок:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
public Task MethodNameAsync(…, IProgress<T> progress);
public Task MethodNameAsync(…,
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken cancellationToken) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task
Public MethodNameAsync(…, cancellationToken As CancellationToken,
                       progress As IProgress(Of T)) As Task  
```  
  
 Однако многие реализации TAP не поддерживают ни отмену, ни просмотр информации о ходе выполнения, поэтому им требуется единственный метод:  
  
```csharp  
public Task MethodNameAsync(…);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
```  
  
 Если реализация TAP поддерживает либо отмену, либо просмотр хода выполнения, но не одновременно, то она может предоставлять две перегрузки:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
  
// … or …  
  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken) As Task  
  
' … or …  
  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task  
```  
  
 Если реализация TAP поддерживает отмену и просмотр хода выполнения, то она может предоставить все четыре перегруженные версии. С другой стороны, она может предоставить только следующие две:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…,
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken,
                       progress As IProgress(Of T)) As Task  
```  
  
 Чтобы возместить два отсутствующих промежуточных сочетания, разработчик может передать значение <xref:System.Threading.CancellationToken.None%2A> или значение по умолчанию <xref:System.Threading.CancellationToken> для параметра `cancellationToken` и `null` для параметра `progress`.  
  
 Если ожидается, что каждое использование метода TAP поддерживает отмену или отслеживание хода выполнения, то можно опустить перегрузки, которые не принимают соответствующих параметров.  
  
 Если необходимо предоставить несколько перегрузок, чтобы сделать необязательной отмену или отслеживание хода выполнения, то перегруженные варианты, которые не поддерживают отмену или отслеживание хода выполнения, должны работать так, будто они передали <xref:System.Threading.CancellationToken.None%2A> для отмены или `null` для отслеживания хода выполнения в перегрузку, которая их поддерживает.  
  
## <a name="related-topics"></a>Связанные разделы  
  
|Название|Описание:|  
|-----------|-----------------|  
|[Модели асинхронного программирования](../../../docs/standard/asynchronous-programming-patterns/index.md)|Представляет три шаблона для выполнения асинхронных операций: асинхронную модель на основе задач (TAP), асинхронную модель программирования (APM) и асинхронную модель на основе событий (EAP).|  
|[Реализация асинхронной модели на основе задач](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)|Описывает три способа реализации асинхронной модели на основе задач (TAP): с помощью компиляторов C# и Visual Basic в Visual Studio, вручную или путем сочетания этих методов.|  
|[Использование асинхронной модели на основе задач](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)|Описывает, как можно использовать задачи и обратные вызовы для реализации неблокирующего ожидания.|  
|[Взаимодействие с другими асинхронными шаблонами и типами](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)|Описывает, как использовать асинхронную модель на основе задач (TAP) для реализации асинхронной модели программирования (APM) и асинхронной модели на основе событий (EAP).|
