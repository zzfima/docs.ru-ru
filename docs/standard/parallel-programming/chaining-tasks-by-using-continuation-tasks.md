---
title: Создание цепочки задач с помощью задач продолжения
ms.date: 02/11/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, continuations
ms.assetid: 0b45e9a2-de28-46ce-8212-1817280ed42d
ms.openlocfilehash: 7de8c4e44e1866e3df36c666c9ecc210dc6a7d83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159368"
---
# <a name="chaining-tasks-by-using-continuation-tasks"></a>Создание цепочки задач с помощью задач продолжения
В асинхронном программировании при завершении одной асинхронной операции принято вызывать вторую операцию и передавать в нее данные. В большинстве случаев непрерывность достигается с помощью методов обратного вызова. В библиотеке параллельных задач эта функциональность обеспечивается *задачами продолжения*. Задача продолжения (также называемая просто продолжением) — это асинхронная задача, вызываемая другой задачей, которая называется *предшествующей*, при завершении этой предшествующей задачи.  
  
 Хотя продолжения относительно легко использовать, они представляют собой мощный и гибкий инструмент. Например, с их помощью можно выполнять следующее.  
  
- Передавать данные из предшествующей задачи в продолжение.  
  
- Указывать точные условия, при которых продолжение будет вызываться или не будет вызываться.  
  
- Отменять продолжение перед его запуском либо совместно с его выполнением.  
  
- Определять подсказки, как должно планироваться продолжение.  
  
- Вызывать несколько продолжений из одной и той же предшествующей задачи.  
  
- Вызывать одно продолжение по завершении всех или одной из нескольких предшествующих задач.  
  
- Прикреплять продолжения одно после другого до любой произвольной длины.  
  
- Использовать продолжение для обработки исключений, вызванных предшествующей задачей.  
  
## <a name="about-continuations"></a>О продолжениях  
 Продолжение — это задача, созданная в состоянии <xref:System.Threading.Tasks.TaskStatus.WaitingForActivation> . Она активируется автоматически при завершении предшествующей задачи или задач. Вызов <xref:System.Threading.Tasks.Task.Start%2A?displayProperty=nameWithType> в продолжении в пользовательском коде вызывает исключение <xref:System.InvalidOperationException?displayProperty=nameWithType> .  
  
 Продолжение по сути является <xref:System.Threading.Tasks.Task> и не блокирует поток, в котором она запущена. Вызовите метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> для блокирования до завершения задачи продолжения.  
  
## <a name="creating-a-continuation-for-a-single-antecedent"></a>Создание продолжения для одной предшествующей задачи  
 Продолжение, которое выполняется, когда завершается предшествующая задача, создается путем вызова метода <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> . В следующем примере показан базовый шаблон (для ясности в нем опущена обработка исключений). Он выполняет предшествующую задачу `taskA`, которая возвращает объект <xref:System.DayOfWeek> , указывающий название текущего дня недели. После завершения предшествующей задачи задача продолжения `continuation` передается предшествующей задаче и отображает строку, содержащую результат ее выполнения.

> [!NOTE]
> В примере C# в этой статье используется модификатор `async` в методе `Main`. Эта возможность доступна в C# 7.1 и более поздних версиях. В предыдущих версиях при компиляции примера кода создается [`CS5001`](../../csharp/misc/cs5001.md). Вам потребуется задать версию языка C# 7.1 или более поздней версии. Инструкции по настройке версии языка приводятся в [этой статье](../../csharp/language-reference/configure-language-version.md).
  
 [!code-csharp[TPL_Continuations#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/simple1.cs#1)]
 [!code-vb[TPL_Continuations#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/simple1.vb#1)]  
  
## <a name="creating-a-continuation-for-multiple-antecedents"></a>Создание продолжения для нескольких предшествующих задач  
 Можно также создать продолжение, которое будет выполняться после завершения всей группы задач или какой-либо из них. Чтобы выполнить продолжение после завершения всех предшествующих задач, вызовите статический (`Shared` в Visual Basic) метод <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> или экземпляр метода <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> . Чтобы выполнить продолжение после завершения какой-либо из предшествующих задач, вызовите статический (`Shared` в Visual Basic) метод <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> или экземпляр метода <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType> .  
  
 Обратите внимание, что вызовы в перегрузки <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> не блокируют вызывающий поток.  Тем не менее обычно вызываются все методы, кроме <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAll%28System.Threading.Tasks.Task%5B%5D%29?displayProperty=nameWithType> для извлечения возвращенного свойства <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>, которое не блокирует вызывающий поток.  
  
 В следующем примере вызывается метод <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> для создания задачи продолжения, которая отражает результаты десяти своих предшествующих задач. Каждой предшествующей задаче соответствует значение индекса в диапазоне от 1 до 10. Если предшествующие задачи завершаются успешно (их свойство <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> имеет значение <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>), то свойство <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> продолжения представляет собой массив значений <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> , возвращенных каждой предшествующей задачей. В этом примере они добавляются для вычисления суммы квадратов всех чисел от 1 до 10.  
  
 [!code-csharp[TPL_Continuations#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/whenall1.cs#5)]
 [!code-vb[TPL_Continuations#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/whenall1.vb#5)]  
  
## <a name="continuation-options"></a>Параметры продолжения  
 При создании продолжения одной задачи можно использовать перегрузку <xref:System.Threading.Tasks.Task.ContinueWith%2A> , принимающую значение перечисления <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> для указания условий, при которых запускается продолжение. Например, вы можете указать, что продолжение должно выполняться только в случае успешного завершения предшествующей задачи или только в случае, если предшествующая задача завершилась в состоянии ошибки. Если в момент, когда предшествующая задача готова вызвать продолжение, условие не выполняется, продолжение переходит непосредственно в состояние <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> и после этого не может быть запущено.  
  
 Ряд методов продолжения нескольких задач, таких как перегрузки метода <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> , также включает параметр <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . Однако допустимым является только подмножество всех членов перечисления <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . Вы можете указать значения <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> , которые имеют аналоги в перечислении <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=nameWithType> , такие как <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType>, <xref:System.Threading.Tasks.TaskContinuationOptions.LongRunning?displayProperty=nameWithType>и <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness?displayProperty=nameWithType>. Если указать один из параметров `NotOn` или `OnlyOn` с продолжением нескольких задач, во время выполнения будет вызвано исключение <xref:System.ArgumentOutOfRangeException> .  
  
 Дополнительные сведения о параметрах продолжения задач см. в разделе <xref:System.Threading.Tasks.TaskContinuationOptions> .  
  
## <a name="passing-data-to-a-continuation"></a>Передача данных в продолжение  
 Метод <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> передает ссылку на предшествующую задачу в пользовательский делегат продолжения в виде аргумента. Если предшествующая задача является объектом <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> и эта задача выполнялась до своего завершения, то продолжение может получить доступ к свойству <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> этой задачи.  
  
 Свойство <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> блокируется до завершения задачи. Однако если задача была отменена или произошел сбой, то попытка доступа к свойству <xref:System.Threading.Tasks.Task%601.Result%2A> вызовет исключение <xref:System.AggregateException> . Этой проблемы можно избежать, используя параметр <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnRanToCompletion> , как показано в следующем примере.  
  
 [!code-csharp[TPL_Continuations#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/result1.cs#2)]
 [!code-vb[TPL_Continuations#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result1.vb#2)]  
  
 Если вы хотите, чтобы продолжение выполнялось, даже если предшествующая задача не выполнилась до успешного завершения, необходимо защититься от этого исключения. Один из подходов заключается в проверке свойства <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> предшествующей задачи и выполнении попытки доступа к свойству <xref:System.Threading.Tasks.Task%601.Result%2A> только в том случае, если предшествующая задача не находится в состоянии <xref:System.Threading.Tasks.TaskStatus.Faulted> или <xref:System.Threading.Tasks.TaskStatus.Canceled>. Можно также проверять свойство <xref:System.Threading.Tasks.Task.Exception%2A> предшествующей задачи. Дополнительные сведения см. в разделе [Обработка исключений](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md). В следующем примере изменяется предыдущий пример, чтобы доступ к свойству <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> предшествующей задачи осуществлялся только в том случае, если она находится в состоянии <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Continuations#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/result2.cs#7)]
 [!code-vb[TPL_Continuations#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result2.vb#7)]  
  
## <a name="canceling-a-continuation"></a>Отмена продолжения  
 Свойство <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> продолжения устанавливается в значение <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> в следующих ситуациях.  
  
- В ответ на запрос отмены вызывается исключение <xref:System.OperationCanceledException> . Как и в любой другой задаче, если исключение содержит тот же токен, что и переданный в продолжение, то он рассматривается как подтверждение совместной отмены.  
  
- Продолжение передает объект <xref:System.Threading.CancellationToken?displayProperty=nameWithType> , свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> которого имеет значение `true`. В этом случае продолжение не запускается и переходит в состояние <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> .  
  
- Продолжение никогда не запускается, поскольку условие, заданное его аргументом <xref:System.Threading.Tasks.TaskContinuationOptions> , не выполнено. Например, если предшествующая задача переходит в состояние <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> , ее продолжение, которое передало параметр <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnFaulted?displayProperty=nameWithType> , не будет выполняться, но перейдет в состояние <xref:System.Threading.Tasks.TaskStatus.Canceled> .  
  
 Если задача и ее продолжение представляют две части одной логической операции, вы можете передать один и тот же токен отмены в обе задачи, как показано в следующем примере. В нем имеется предшествующая задача, создающая список целых чисел, кратных 33, который передается в продолжение. Продолжение, в свою очередь, отображает этот список. И предшествующая задача, и продолжение регулярно приостанавливаются на произвольные периоды времени. Кроме того, используется объект <xref:System.Threading.Timer?displayProperty=nameWithType> для выполнения метода `Elapsed` после пятисекундного времени ожидания. В этом примере вызывается метод <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>, который приводит к тому, что текущая выполняющаяся задача вызывает метод <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A?displayProperty=nameWithType>. В зависимости от длительности произвольно создаваемых пауз метод <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> вызывается при выполнении либо предшествующей задачи, либо ее продолжения. Если предшествующая задача отменена, продолжение не запустится. Если предшествующая задача не отменена, токен еще можно использовать для отмены продолжения.  
  
 [!code-csharp[TPL_Continuations#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/cancellation1.cs#3)]
 [!code-vb[TPL_Continuations#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation1.vb#3)]  
  
 Вы также можете запретить выполнение продолжения в случае отмены его предшествующей задачи без передачи в продолжение токена отмены, указав параметр <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled?displayProperty=nameWithType> при создании продолжения. Ниже приведен простой пример.  
  
 [!code-csharp[TPL_Continuations#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/cancellation2.cs#8)]
 [!code-vb[TPL_Continuations#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation2.vb#8)]  
  
 После перехода продолжения в состояние <xref:System.Threading.Tasks.TaskStatus.Canceled> это может повлиять на последующие продолжения, в зависимости от <xref:System.Threading.Tasks.TaskContinuationOptions> , указанных для этих продолжений.  
  
 Освобожденные продолжения не будут запускаться.  
  
## <a name="continuations-and-child-tasks"></a>Продолжения и дочерние задачи  
 Продолжение не выполняется до завершения предшествующей задачи и всех ее присоединенных дочерних задач. Продолжение не ожидает завершения отсоединенных дочерних задач. В следующих двух примерах показаны дочерние задачи, присоединенные к предшествующей задаче, создающей продолжение, и отсоединенные от нее. В следующем примере продолжение выполняется только после завершения всех дочерних задач, и многократное выполнение примера каждый раз приводит к одному и тому же результату. В этом примере предшествующая задача запускается путем вызова метода <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>, поскольку по умолчанию метод <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> создает родительскую задачу, которая имеет параметр создания задачи по умолчанию <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Continuations#9](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/attached1.cs#9)]
 [!code-vb[TPL_Continuations#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/attached1.vb#9)]  
  
 Если дочерние задачи отсоединены от предшествующей задачи, продолжение выполняется сразу после завершения предшествующей задачи независимо от состояния дочерних задач. В результате после нескольких запусков следующего примера могут создаваться разные выходные данные, в зависимости от того, как планировщик задач обработал каждую дочернюю задачу.  
  
 [!code-csharp[TPL_Continuations#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/detached1.cs#10)]
 [!code-vb[TPL_Continuations#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/detached1.vb#10)]  
  
 Конечное состояние предшествующей задачи зависит от конечного состояния всех присоединенных дочерних задач. Состояние отсоединенных дочерних задач не влияет на родительскую задачу. Дополнительные сведения см. в разделе [Присоединенные и отсоединенные дочерние задачи](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).  
  
## <a name="associating-state-with-continuations"></a>Связывание состояния с продолжениями  
 Вы можете связывать произвольное состояние с продолжением задачи. Метод <xref:System.Threading.Tasks.Task.ContinueWith%2A> предоставляет перегруженные версии, каждая из которых принимает значение <xref:System.Object> , представляющее состояние продолжения. Позднее можно получить доступ к этому объекту состояния с помощью свойства <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> . Если значение не предоставлено, то этот объект состояния имеет значение `null`.  
  
 Состояние продолжения полезно при преобразовании существующего кода, который использует библиотеку параллельных задач с помощью [асинхронной модели программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md). В APM объект состояния обычно предоставляется в метод **Begin**_Method_, а впоследствии доступ к этому состоянию получается с помощью свойства <xref:System.IAsyncResult.AsyncState%2A?displayProperty=nameWithType>. С помощью метода <xref:System.Threading.Tasks.Task.ContinueWith%2A> можно сохранить это состояние при преобразовании кода,  использующего библиотеку параллельных задач с помощью  APM.  
  
 Состояние продолжения также можно использовать при работе с объектами <xref:System.Threading.Tasks.Task> в отладчике Visual Studio. Например, в окне **Параллельные задачи** столбец **Задачи** отображает строковое представление объекта состояния для каждой задачи. Дополнительные сведения об окне **Параллельные задачи** см. в разделе [Использование окна задач](/visualstudio/debugger/using-the-tasks-window).  
  
 В следующем примере демонстрируется использование состояния продолжения. В нем создается цепочка задач продолжения. Каждая задача предоставляет текущее время в объекте <xref:System.DateTime> для параметра `state` метода <xref:System.Threading.Tasks.Task.ContinueWith%2A> . Каждый объект <xref:System.DateTime> представляет время, в которое создана задача продолжения. Каждая задача в результате создает второй объект <xref:System.DateTime> , представляющий время, в которое эта задача завершена. После завершения всех задач в этом примере отображается время создания и время завершения каждой задачи продолжения.  
  
 [!code-csharp[TPL_ContinuationState#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuationstate/cs/continuationstate.cs#1)]
 [!code-vb[TPL_ContinuationState#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuationstate/vb/continuationstate.vb#1)]  
  
## <a name="handling-exceptions-thrown-from-continuations"></a>Обработка исключений, вызванных из продолжений  
 Отношение предшествующей задачи и продолжения не является связью типа «родитель — потомок». Исключения, вызванные продолжениями, не распространяются в предшествующую задачу. Таким образом, следует обрабатывать вызванные продолжениями исключения так, как они обрабатываются в любой другой задаче, следующим образом.  
  
- Для ожидания продолжения можно использовать метод <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.WaitAll%2A>, или <xref:System.Threading.Tasks.Task.WaitAny%2A> , либо его универсальный эквивалент. Вы можете ожидать предшествующую задачу и ее продолжение в одном операторе `try` , как показано в следующем примере.  
  
     [!code-csharp[TPL_Continuations#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception1.cs#6)]
     [!code-vb[TPL_Continuations#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception1.vb#6)]  
  
- Для наблюдения за свойством <xref:System.Threading.Tasks.Task.Exception%2A> первого продолжения можно использовать второе продолжение. В следующем примере задача пытается выполнить чтение в несуществующем файле. Затем продолжение отображает сведения об исключении в предшествующей задаче.  
  
     [!code-csharp[TPL_Continuations#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception2.cs#4)]
     [!code-vb[TPL_Continuations#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#4)]  
  
     Так как она была запущена с параметром <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnFaulted?displayProperty=nameWithType> , продолжение выполняется только в том случае, если в предшествующей задаче возникает исключение, и поэтому можно предполагать, что свойство <xref:System.Threading.Tasks.Task.Exception%2A> предшествующей задачи не имеет значение `null`. Если продолжение выполняется независимо от того, вызывалось ли исключение в предшествующей задаче, то перед попыткой обработки исключения оно должно проверить, что свойство <xref:System.Threading.Tasks.Task.Exception%2A> не имеет значение `null` , как показано в следующем фрагменте кода.  
  
     [!code-csharp[TPL_Continuations#11](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception2.cs#11)]
     [!code-vb[TPL_Continuations#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#11)]  
  
     Дополнительные сведения см. в разделе [Обработка исключений](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
- Если продолжение является присоединенной дочерней задачей, созданной с использованием параметра <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType> , его исключения будут распространяться родительской задачей обратно в вызывающий поток, как и в случае любой другой присоединенной дочерней задачи. Дополнительные сведения см. в разделе [Присоединенные и отсоединенные дочерние задачи](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).  
  
## <a name="see-also"></a>См. также раздел

- [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
