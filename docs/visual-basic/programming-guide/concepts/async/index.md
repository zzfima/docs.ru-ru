---
title: Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)
ms.date: 07/20/2015
ms.assetid: bd7e462b-583b-4395-9c36-45aa9e61072c
ms.openlocfilehash: 8593275371fcd97db2357211c3e221839b878527
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324725"
---
# <a name="asynchronous-programming-with-async-and-await-visual-basic"></a>Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)
Асинхронное программирование позволяет избежать появления узких мест производительности и увеличить общую скорость реагирования приложения. Однако традиционные методы создания асинхронных приложений могут оказаться сложными, как в плане написания кода, так и в плане отладки и обслуживания.  
  
 Visual Studio 2012 вводит упрощенный подход асинхронного программирования, который использует асинхронные возможности .NET Framework 4.5 (и более высоких версий) и среды выполнения Windows. Компилятор выполняет сложную работу, которую раньше делал разработчик, при этом логическая структура кода приложения похожа на синхронный код. То есть можно пользоваться всеми преимуществами асинхронного программирования с гораздо меньшими, чем обычно, трудозатратами.  
  
 В этом разделе рассматриваются области и методы использования асинхронного программирования, а также приводятся ссылки на вспомогательные разделы с дополнительными сведениями и примерами.  
  
## <a name="BKMK_WhentoUseAsynchrony"></a> Async повышает скорость реагирования  
 Асинхронность необходимо использовать при наличии потенциально блокирующих действий — например, когда приложение подключается к Интернету. Доступ к веб-ресурсу иногда осуществляется медленно или с задержкой. Если такое действие блокируется в пределах синхронного процесса, все приложение вынуждено ожидать. В асинхронном процессе приложение может перейти к следующей операции, не зависящей от веб-ресурса, до завершения блокирующей задачи.  
  
 В следующей таблице показаны стандартные области, в которых асинхронное программирование повышает скорость реагирования. Перечисленные интерфейсы API платформы .NET Framework 4.5 и среды выполнения Windows содержат методы, поддерживающие асинхронное программирование.  
  
|Область приложения|Поддерживающие интерфейсы API, которые содержат асинхронные методы|  
|----------------------|------------------------------------------------|  
|Веб-доступ|<xref:System.Net.Http.HttpClient>, <xref:Windows.Web.Syndication.SyndicationClient>|  
|Работа с файлами|<xref:Windows.Storage.StorageFile>, <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader>|  
|Работа с образами|<xref:Windows.Media.Capture.MediaCapture>значение <xref:Windows.Graphics.Imaging.BitmapEncoder>значение <xref:Windows.Graphics.Imaging.BitmapDecoder>|  
|Программирование с использованием WCF|[Синхронные и асинхронные операции](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)|  
|||  
  
 Асинхронность особенно полезна в приложениях, которые обращаются к потоку пользовательского интерфейса, поскольку все связанные с пользовательским интерфейсом действия обычно используют один поток. В синхронном приложении блокировка одного процесса приводит к блокировке всех процессов. Приложение перестает отвечать, и это выглядит как сбой, а не как ожидание.  
  
 При использовании асинхронных методов приложение продолжает реагировать на действия в пользовательском интерфейсе. Например, можно изменить размер окна или свернуть его, либо закрыть приложение, если не требуется ждать завершения работы.  
  
 Асинхронный подход добавляет эквивалент автоматической передачи в список параметров, выбранных при создании асинхронных операций. То есть разработчик может пользоваться всеми преимуществами традиционного асинхронного программирования, прикладывая гораздо меньше усилий.  
  
## <a name="BKMK_HowtoWriteanAsyncMethod"></a> Методы Async проще создавать  
 В Visual Basic основой асинхронного программирования являются ключевые слова [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [Await](../../../../visual-basic/language-reference/modifiers/async.md). Они позволяют использовать ресурсы платформы .NET Framework или среды выполнения Windows для создания асинхронных методов, и это почти так же просто, как создавать синхронные методы. Методы, которые определяются с помощью ключевых слов `Async` и `Await`, называются асинхронными методами.  
  
 Ниже приводится пример асинхронного метода. Почти все элементы кода должны быть вам знакомы. Комментарии указывают на возможности, добавляемые для создания асинхронности.  
  
 Полный файл примера Windows Presentation Foundation представлен в конце раздела. Также его можно скачать на странице [примера асинхронной работы из руководства по использованию ключевых слов Async и Await](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c).  
  
```vb  
' Three things to note in the signature:  
'  - The method has an Async modifier.   
'  - The return type is Task or Task(Of T). (See "Return Types" section.)  
'    Here, it is Task(Of Integer) because the return statement returns an integer.  
'  - The method name ends in "Async."  
Async Function AccessTheWebAsync() As Task(Of Integer)  
  
    ' You need to add a reference to System.Net.Http to declare client.  
    Dim client As HttpClient = New HttpClient()  
  
    ' GetStringAsync returns a Task(Of String). That means that when you await the  
    ' task you'll get a string (urlContents).  
    Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")  
  
    ' You can do work here that doesn't rely on the string from GetStringAsync.  
    DoIndependentWork()  
  
    ' The Await operator suspends AccessTheWebAsync.  
    '  - AccessTheWebAsync can't continue until getStringTask is complete.  
    '  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
    '  - Control resumes here when getStringTask is complete.   
    '  - The Await operator then retrieves the string result from getStringTask.  
    Dim urlContents As String = Await getStringTask  
  
    ' The return statement specifies an integer result.  
    ' Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
    Return urlContents.Length  
End Function  
```  
  
 Если метод `AccessTheWebAsync` не выполняет никакие операции между вызовом метода `GetStringAsync` и его завершением, можно упростить код, описав вызов и ожидание с помощью следующего простого оператора.  
  
```vb  
Dim urlContents As String = Await client.GetStringAsync()  
```  
  
 Далее поясняется, почему код предыдущего примера является асинхронным методом.  
  
-   Сигнатура метода включает модификатор `Async`.  
  
-   Имя асинхронного метода, как правило, оканчивается суффиксом Async.  
  
-   Возвращаемое значение имеет один из следующих типов:  
  
    -   <xref:System.Threading.Tasks.Task%601> Если метод имеет оператор return, в котором операнд имеет тип TResult.  
  
    -   <xref:System.Threading.Tasks.Task> Если метод не имеет оператора return или имеет оператор return без операнда.  
  
    -   [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md), если вы создаете асинхронный обработчик событий.  
  
     Дополнительные сведения см. ниже в подразделе "типы возвращаемого значения и параметры".  
  
-   Метод обычно содержит по крайней мере одно выражение await, отмечающее точку, в которой метод не может выполняться до завершения асинхронной операции. На это время метод приостанавливается и управление возвращается к вызывающему объекту метода. В следующем подразделе показано, что происходит в точке приостановки.  
  
 В асинхронных методах с помощью соответствующих ключевых слов и типов указывается, что требуется сделать, а компилятор выполняет остальные задачи, в том числе отслеживает обязательные действия, когда управление возвращается в точку await в приостановленном методе. Некоторые программные процессы, такие как циклы и обработка исключений, сложно добавлять в традиционный асинхронный код. В асинхронном методе эти элементы пишутся почти так же, как в синхронном решении, что очень удобно.  
  
 Дополнительные сведения об асинхронности в предыдущих версиях платформы .NET Framework, см. в статье [TPL and Traditional .NET Framework Asynchronous Programming](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md) (Библиотека параллельных задач и традиционное асинхронное программирование в .NET Framework).  
  
## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a>Что происходит в методе Async  
 В асинхронном программировании важнее всего понимать, как поток управления перемещается из метода в метод. Следующая схема описывает этот процесс.  
  
 ![Схема, показывающая трассировку асинхронной программы.](./media/index/navigation-trace-async-program.png)  
  
 Числа в схеме соответствуют следующим шагам.  
  
1. Обработчик событий вызывает асинхронный метод `AccessTheWebAsync` и ожидает его.  
  
2. `AccessTheWebAsync` Создает <xref:System.Net.Http.HttpClient> экземпляра и вызывает метод <xref:System.Net.Http.HttpClient.GetStringAsync%2A> асинхронный метод для загрузки содержимого веб-сайта в виде строки.  
  
3. В `GetStringAsync` происходит событие, которое приостанавливает ход выполнения. Например, методу необходимо подождать завершения загрузки или произошло другое блокирующее действие. Чтобы избежать блокировки ресурсов, `GetStringAsync` передает управление вызывающему объекту `AccessTheWebAsync`.  
  
     `GetStringAsync` Возвращает <xref:System.Threading.Tasks.Task%601> там, где TResult является строкой, и `AccessTheWebAsync` присваивает задачу `getStringTask` переменной. Задача представляет собой непрерывный процесс для вызова `GetStringAsync` с обязательством создать фактическое значение строки, когда работа будет завершена.  
  
4. Поскольку значение из процесса `getStringTask` еще не получено, метод `AccessTheWebAsync` может перейти к другим операциям, не зависящим от конечного результата`GetStringAsync`. Эти операции представлены вызовом синхронного метода `DoIndependentWork`.  
  
5. `DoIndependentWork` — Это синхронный метод, который выполняет свою работу и возвращает его вызывающему.  
  
6. `AccessTheWebAsync` хватает работы, его можно сделать без результатов из `getStringTask`. `AccessTheWebAsync` Далее хочет вычисления и возврата длину загруженной строки, но метод не может вычислить это значение до метода содержит строку.  
  
     Поэтому `AccessTheWebAsync` использует оператор await, чтобы приостановить свою работу и передать управление методу, вызвавшему `AccessTheWebAsync`. `AccessTheWebAsync` Возвращает `Task<int>` (`Task(Of Integer)` в Visual Basic) для вызывающего объекта. Задача представляет собой обещание создать целочисленный результат, являющийся длиной загруженной строки.  
  
    > [!NOTE]
    >  Если метод `GetStringAsync` (и, следовательно, процесс `getStringTask`) выполнен прежде, чем этого дождется `AccessTheWebAsync`, управление остается у метода `AccessTheWebAsync`. На приостановку метода `AccessTheWebAsync` и последующий возврат к нему были бы потрачены лишние ресурсы, если вызываемый асинхронный процесс (`getStringTask`) уже завершен и AccessTheWebSync не нужно ждать окончательного результата.  
  
     Внутри вызывающего объекта (в данном примере — обработчика событий) шаблон обработки повторяется. Вызывающий объект может выполнять другие операции, не зависящие от результата `AccessTheWebAsync`, во время ожидания этого результата, или сразу ожидать результата.   Обработчик событий ожидает `AccessTheWebAsync`, а `AccessTheWebAsync` ожидает `GetStringAsync`.  
  
7. `GetStringAsync` завершается и создает строковый результат. Вызов возвращает строковый результат в метод `GetStringAsync`, но не так, как, возможно, ожидалось. (Помните, что метод уже возвратил задачу в шаге 3.) Вместо этого строковый результат хранится в задаче `getStringTask`, которая представляет собой завершение метода. Оператор await извлекает результат из `getStringTask`. Оператор присваивания назначает извлеченный результат `urlContents`.  
  
8. Если `AccessTheWebAsync` содержит строковый результат, метод может вычислить длину строки. Затем работа `AccessTheWebAsync` также завершена, и ожидающий обработчик событий может возобновить работу. В полном примере в конце этого раздела видно, что обработчик событий извлекает значение длины и выводит результат.  
  
 Если вы недавно занимаетесь асинхронным программированием, рекомендуем обратить внимание на различия между синхронным и асинхронным поведением. Синхронный метод возвращает управление, когда его работа завершается (шаг 5), тогда как асинхронный метод возвращает значение задачи, когда его работа приостанавливается (шаги 3 и 6). Когда асинхронный метод в конечном счете завершает работу, задача помечается как завершенная и результат, при его наличии, сохраняется в задаче.  
  
 Дополнительные сведения о потоке управления см. в статье [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) (Поток управления в асинхронных программах на Visual Basic).  
  
## <a name="BKMK_APIAsyncMethods"></a> Методы Async API  
 Где же найти методы для асинхронного программирования (такие как `GetStringAsync`)? Платформа .NET Framework 4.5 или более поздней версии содержит большое количество элементов, совместимых с `Async` и `Await`. Они содержат суффикс Async в своем имени и возвращают тип <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Например, класс `System.IO.Stream` имеет такие методы, как <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> и <xref:System.IO.Stream.WriteAsync%2A>, наряду с синхронными методами <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> и <xref:System.IO.Stream.Write%2A>.  
  
 Среда выполнения Windows также содержит множество методов, которые можно использовать в сочетании с `Async` и `Await` в приложениях Windows. Дополнительные сведения и примеры методов см. в разделе [вызов асинхронных API в C# или Visual Basic](/windows/uwp/threading-async/call-asynchronous-apis-in-csharp-or-visual-basic), [асинхронное программирование (приложения среды выполнения Windows)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)), и [WhenAny: Создание моста между .NET Framework и среды выполнения Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120)).  
  
## <a name="BKMK_Threads"></a> Потоки  
 Асинхронные методы используются для неблокирующих операций. Выражение `Await` в асинхронном методе не блокирует текущий поток на время выполнения ожидаемой задачи. Вместо этого выражение регистрирует остальную часть метода как продолжение и возвращает управление вызывающему объекту асинхронного метода.  
  
 Ключевые слова `Async` и `Await` не вызывают создания дополнительных потоков. Асинхронные методы не требуют многопоточности, поскольку асинхронный метод не выполняется в собственном потоке. Метод выполняется в текущем контексте синхронизации и использует время в потоке, только когда метод активен. Метод <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> можно применять для перемещения операций, использующих ресурсы ЦП, в фоновый поток, однако фоновый поток не имеет смысла применять для процесса, который просто ждет результата.  
  
 Асинхронный подход к асинхронному программированию практически по всем параметрам имеет преимущество перед другими подходами. В частности, этот подход лучше, чем <xref:System.ComponentModel.BackgroundWorker> для операций ввода-вывода, так как код проще, и у вас нет доступа к предотвращать состояние гонки. В сочетании с <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> асинхронное программирование лучше <xref:System.ComponentModel.BackgroundWorker> для операций, использующих ресурсы ЦП, поскольку отделяет сведения координации о выполнении кода от действий, которые `Task.Run` перемещает в пул потоков.  
  
## <a name="BKMK_AsyncandAwait"></a> Async и Await  
 Если с помощью модификатора [Async](../../../../visual-basic/language-reference/modifiers/async.md) указать, что метод является асинхронным, появятся следующие две возможности.  
  
-   Асинхронный метод сможет использовать [Await](../../../../visual-basic/language-reference/operators/await-operator.md) для обозначения точек приостановки. Оператор await сообщает компилятору, что асинхронный метод не может выполняться после этой точки до завершения ожидаемого асинхронного процесса. На это время управление возвращается вызывающему объекту асинхронного метода.  
  
     Приостановка асинхронного метода на выражении `Await` не считается выходом из метода и блоки `Finally` не выполняются.  
  
-   Сам обозначенный асинхронный метод может ожидаться вызывающими его методами.  
  
 Асинхронный метод обычно содержит одно или несколько вхождений оператора `Await`, но отсутствие выражений `Await` не вызывает ошибок компилятора. Если асинхронный метод не использует оператор `Await` для обозначения точки приостановки, метод выполняется как синхронный, независимо от наличия модификатора `Async`. При компиляции таких методов выдается предупреждение.  
  
 `Async` и `Await` являются контекстными ключевыми словами. Дополнительные сведения и примеры см. в следующих разделах:  
  
-   [Async](../../../../visual-basic/language-reference/modifiers/async.md)  
  
-   [Оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md)  
  
## <a name="BKMK_ReturnTypesandParameters"></a> Типы возвращаемого значения и параметры  
 В программировании на платформе .NET Framework асинхронный метод обычно возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Внутри асинхронного метода оператор `Await` применяется к задаче, возвращаемой из вызова другого асинхронного метода.  
  
 В качестве возвращаемого типа указывается <xref:System.Threading.Tasks.Task%601>, если метод содержит оператор [Return](../../../../visual-basic/language-reference/statements/return-statement.md), который задает операнд типа `TResult`.  
  
 В качестве возвращаемого типа используется `Task`, если метод не содержит операторов return или содержит оператор return, который не возвращает операнд.  
  
 В следующем примере показано объявление и вызов метода, который возвращает <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>.  
  
```vb  
' Signature specifies Task(Of Integer)  
Async Function TaskOfTResult_MethodAsync() As Task(Of Integer)  
  
    Dim hours As Integer  
    ' . . .  
    ' Return statement specifies an integer result.  
    Return hours  
End Function  
  
' Calls to TaskOfTResult_MethodAsync  
Dim returnedTaskTResult As Task(Of Integer) = TaskOfTResult_MethodAsync()  
Dim intResult As Integer = Await returnedTaskTResult  
' or, in a single statement  
Dim intResult As Integer = Await TaskOfTResult_MethodAsync()  
  
' Signature specifies Task  
Async Function Task_MethodAsync() As Task  
  
    ' . . .  
    ' The method has no return statement.  
End Function  
  
' Calls to Task_MethodAsync  
Task returnedTask = Task_MethodAsync()  
Await returnedTask  
' or, in a single statement  
Await Task_MethodAsync()  
```  
  
 Каждая возвращенная задача представляет выполняющуюся работу. Задача инкапсулирует информацию о состоянии асинхронного процесса и, в итоге, либо конечный результат процесса, либо исключение, созданное процессом в случае его сбоя.  
  
 Асинхронный метод может также быть методом `Sub`. Тип возвращаемого значения в основном используется для определения обработчиков событий, где требуется возвращать тип. Асинхронные обработчики событий часто служат в качестве отправной точки для асинхронных программ.  
  
 Асинхронный метод, который является процедурой `Sub`, невозможно ожидать методом Await. Вызывающий объект не может перехватывать исключения, которые выдает такой метод.  
  
 Асинхронный метод не может объявлять параметры [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), но может вызывать методы, которые имеют такие параметры.  
  
 Дополнительные сведения и примеры см. в статье [о типах возвращаемых значений асинхронных операций](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md). Дополнительные сведения о перехвате исключений в асинхронных методах см. в статье [об операторе Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 При программировании в среде выполнения Windows асинхронные интерфейсы API имеют один из следующих возвращаемых типов, которые похожи на задачи:  
  
-   <xref:Windows.Foundation.IAsyncOperation%601>, который соответствует <xref:System.Threading.Tasks.Task%601>  
  
-   <xref:Windows.Foundation.IAsyncAction>, который соответствует <xref:System.Threading.Tasks.Task>  
  
-   <xref:Windows.Foundation.IAsyncActionWithProgress%601>  
  
-   <xref:Windows.Foundation.IAsyncOperationWithProgress%602>  
  
 Дополнительные сведения и пример см. в разделе [вызов асинхронных API в C# или Visual Basic](/windows/uwp/threading-async/call-asynchronous-apis-in-csharp-or-visual-basic).  
  
## <a name="BKMK_NamingConvention"></a> Соглашение об именовании  
 По соглашению к именам методов, которые имеют модификатор `Async`, добавляется суффикс Async.  
  
 Соглашение можно игнорировать в тех случаях, когда событие, базовый класс или контракт интерфейса предлагает другое имя. Например, не следует переименовывать общие обработчики событий, такие как `Button1_Click`.  
  
## <a name="BKMK_RelatedTopics"></a> Связанные разделы и примеры для Visual Studio  
  
|Заголовок|Описание|Пример|  
|-----------|-----------------|------------|  
|[Пошаговое руководство. Доступ к Интернету с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)|Иллюстрирует преобразование синхронного решения WPF в асинхронное. Приложение загружает ряд веб-сайтов.|[Пример асинхронности. Доступ к Пошаговое руководство](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)|  
|[Практическое руководство. Расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|Добавляет <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> к предыдущему пошаговому руководству. Использование `WhenAll` запускает все загрузки одновременно.||  
|[Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|Иллюстрирует, как запустить несколько задач одновременно.|[Пример асинхронности. Параллельное выполнение нескольких веб-запросов](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)|  
|[Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)|Иллюстрирует типы, которые могут возвращать асинхронные методы, и поясняет, когда следует использовать каждый из этих типов.||  
|[Поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)|Выполняет подробную трассировку потока управления через последовательность выражений ожидания в асинхронной программе.|[Пример асинхронности. Поток управления в асинхронных программах](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)|  
|[Настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)|Иллюстрирует добавление следующих функциональных возможностей в асинхронное решение:<br /><br /> -   [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) (Отмена асинхронной задачи или списка задач в Visual Basic)<br />-   [Cancel Async Tasks after a Period of Time (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md) (Отмена асинхронных задач после определенного периода времени в Visual Basic)<br />-   [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) (Отмена оставшихся асинхронных задач после завершения одной из них в Visual Basic)<br />-   [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md) (Запуск нескольких асинхронных задач и их обработка по мере завершения в Visual Basic)|[Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)|  
|[Обработка повторного входа в асинхронных приложениях (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)|Иллюстрирует обработку случаев, в которых активная асинхронная операция перезапускается при выполнении.||  
|[WhenAny. Связывание .NET Framework и среды выполнения Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|Иллюстрирует, как создать мост между типами задач на платформе .NET Framework и IAsyncOperations в [!INCLUDE[wrt](~/includes/wrt-md.md)], чтобы можно было использовать <xref:System.Threading.Tasks.Task.WhenAny%2A> с методом [!INCLUDE[wrt](~/includes/wrt-md.md)].|[Пример асинхронности. Создание моста между .NET и среды выполнения Windows (AsTask и WhenAny)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|  
|Отмена Async. Связывание .NET Framework и среды выполнения Windows|Иллюстрирует, как создать мост между типами задач на платформе .NET Framework и IAsyncOperations в [!INCLUDE[wrt](~/includes/wrt-md.md)], чтобы можно было использовать <xref:System.Threading.CancellationTokenSource> с методом [!INCLUDE[wrt](~/includes/wrt-md.md)].|[Пример асинхронности. Создание моста между .NET и среды выполнения Windows (AsTask и Отмена)](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3)|  
|[Использование метода Async для доступа к файлам (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/using-async-for-file-access.md)|Иллюстрирует преимущества использования асинхронности и ожидания для доступа к файлам.||  
|[Асинхронный шаблон, основанный на задачах (TAP)](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Описывает новый шаблон для асинхронности в платформе .NET Framework. Шаблон основан на типах <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>.||  
|[Видеоролики об Async на Channel 9](https://channel9.msdn.com/search?term=async+&type=All)|Предоставляет ссылки на различные видеоролики об асинхронном программировании.||  
  
## <a name="BKMK_CompleteExample"></a> Полный пример  
 Ниже представлен код файла MainWindow.xaml.vb из приложения Windows Presentation Foundation (WPF), которое обсуждается в этой статье. Вы можете скачать [пример использования Async из руководства по использованию ключевых слов Async и Await](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c).  
  
```vb  
' Add an Imports statement and a reference for System.Net.Http  
Imports System.Net.Http  
  
Class MainWindow  
  
    ' Mark the event handler with async so you can use Await in it.  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Call and await separately.  
        'Task<int> getLengthTask = AccessTheWebAsync();  
        '' You can do independent work here.  
        'int contentLength = await getLengthTask;  
  
        Dim contentLength As Integer = Await AccessTheWebAsync()  
  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
    End Sub  
  
    ' Three things to note in the signature:  
    '  - The method has an Async modifier.   
    '  - The return type is Task or Task(Of T). (See "Return Types" section.)  
    '    Here, it is Task(Of Integer) because the return statement returns an integer.  
    '  - The method name ends in "Async."  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' You need to add a reference to System.Net.Http to declare client.  
        Dim client As HttpClient = New HttpClient()  
  
        ' GetStringAsync returns a Task(Of String). That means that when you await the  
        ' task you'll get a string (urlContents).  
        Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")  
  
        ' You can do work here that doesn't rely on the string from GetStringAsync.  
        DoIndependentWork()  
  
        ' The Await operator suspends AccessTheWebAsync.  
        '  - AccessTheWebAsync can't continue until getStringTask is complete.  
        '  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
        '  - Control resumes here when getStringTask is complete.   
        '  - The Await operator then retrieves the string result from getStringTask.  
        Dim urlContents As String = Await getStringTask  
  
        ' The return statement specifies an integer result.  
        ' Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
        Return urlContents.Length  
    End Function  
  
    Sub DoIndependentWork()  
        ResultsTextBox.Text &= "Working . . . . . . ." & vbCrLf  
    End Sub  
End Class  
  
' Sample Output:  
  
' Working . . . . . . .  
  
' Length of the downloaded string: 41763.  
```  
  
## <a name="see-also"></a>См. также

- [Оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
