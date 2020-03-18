---
title: Реализация асинхронной модели, основанной на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: 9865fa169e0776765f9a97ec0a7b4555bf253886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67663709"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a>Реализация асинхронной модели, основанной на событиях

Если вы создаете класс и некоторые операции этого класса могут привести к значительным задержкам, подумайте о том, чтобы реализовать асинхронные функции для этого класса с помощью [асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).

Асинхронная модель на основе событий предоставляет стандартизированный способ упаковки класса, в котором есть асинхронные функции. Если вы реализуете класс с помощью вспомогательных классов, таких как <xref:System.ComponentModel.AsyncOperationManager>, то ваш класс будет работать правильно в любой модели приложения, включая ASP.NET, консольные приложения и приложения Windows Forms.

Пример реализации асинхронной модели на основе событий см. в разделе [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).

Для простых асинхронных операций компонент <xref:System.ComponentModel.BackgroundWorker> может оказаться подходящим вариантом. Дополнительные сведения о <xref:System.ComponentModel.BackgroundWorker> см. в статье [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).

Ниже перечислены функции асинхронной модели на основе событий, описанные в этом разделе.

- Возможности для реализации асинхронной модели на основе событий

- Именование асинхронных методов

- Возможная поддержка отмены

- Возможная поддержка свойства IsBusy

- Возможная поддержка отчетов о ходе выполнения

- Возможная поддержка возврата добавочных результатов

- Обработка выходных и ссылочных параметров в методах

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Возможности для реализации асинхронной модели на основе событий

Подумайте о реализации асинхронной модели на основе событий при следующих условиях.

- Клиентам вашего класса не нужна доступность объектов <xref:System.Threading.WaitHandle> и <xref:System.IAsyncResult> для асинхронных операций. Это значит, что механизм опросов и <xref:System.Threading.WaitHandle.WaitAll%2A> (или <xref:System.Threading.WaitHandle.WaitAny%2A>) нужно создать на стороне клиента.

- Асинхронными операциями должен управлять клиент с использованием известной модели событий или делегатов.

Любую операцию можно реализовать асинхронно, но следует выбирать те операции, которые будут включать большие задержки. Особенно подходят те операции, при которых клиенты вызывают метод и получают оповещение о его выполнении и никакого другого вмешательства в работу метода не требуется. Также подходят операции, которые работают постоянно и периодически уведомляют клиентов о ходе выполнения, об изменении состояния или отправляют им промежуточные результаты.

Дополнительные сведения о выборе асинхронной модели на основе событий см. в разделе [Выбор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).

## <a name="naming-asynchronous-methods"></a>Именование асинхронных методов

Для каждого синхронного метода *имя_метода*, для которого необходимо предоставить асинхронный эквивалент, выполните следующие действия.

Определите метод _MethodName_**Async**, который отвечает за выполнение следующих действий:

- Возвращает `void`.

- принимает те же параметры, что и метод *имя_метода*;

- поддерживает несколько вызовов.

Вы также можете определить перегрузку _MethodName_**Async**, которая идентична методу _MethodName_**Async**, но принимает дополнительный параметр `userState`, зависящий от объекта. Реализуйте эту перегрузку, если необходимо управлять несколькими параллельными вызовами метода. В этом случае значение `userState` будет отправляться обратно во все обработчики событий, чтобы различать вызовы метода. Такую перегрузку также можно использовать для хранения и последующего извлечения состояния пользователя.

Для каждой отдельной сигнатуры метода _MethodName_**Async** выполните следующие действия.

1. Определите следующее событие в том же классе, в котором находится метод.

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. Определите следующий делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs>. Обычно они определяются за пределами класса, но в том же пространстве имен.

    ```vb
    Public Delegate Sub MethodNameCompletedEventHandler( _
        ByVal sender As Object, _
        ByVal e As MethodNameCompletedEventArgs)

    Public Class MethodNameCompletedEventArgs
        Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As MyReturnType
    End Property
    ```

    ```csharp
    public delegate void MethodNameCompletedEventHandler(object sender,
        MethodNameCompletedEventArgs e);

    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
    {
        public MyReturnType Result { get; }
    }
    ```

    - Убедитесь, что класс _MethodName_**CompletedEventArgs** предоставляет свои члены в виде свойств только для чтения, а не в виде полей, которые не поддерживают привязку данных.

    - Не определяйте производные от <xref:System.ComponentModel.AsyncCompletedEventArgs> классы для методов, которые не возвращают результатов. Используйте в этой ситуации непосредственно экземпляр <xref:System.ComponentModel.AsyncCompletedEventArgs>.

      > [!NOTE]
      > Также полностью допустимо использовать делегат и типы <xref:System.ComponentModel.AsyncCompletedEventArgs> повторно во всех случаях, когда это возможно и уместно. В этом случае имя делегата не будет согласовано с именем метода, так как делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs> не привязаны к одному методу.

## <a name="optionally-support-cancellation"></a>Возможная поддержка отмены

Если ваш класс будет поддерживать отмену асинхронных операций, возможность отмены должна быть предоставлена клиенту, как описано ниже. Перед тем как определить, будет ли реализована возможность отмены, необходимо ответить на два вопроса.

- Будет ли в вашем классе и во всех его будущих версиях всего одна асинхронная операция, которая поддерживает отмену?

- Может ли асинхронная операция с возможностью отмены поддерживать несколько ожидающих операций? То есть принимает ли метод _MethodName_**Async** параметр `userState` и позволяет ли он создать несколько вызовов перед ожиданием завершения любого из них?

С помощью ответов на эти вопросы и приведенной ниже таблицы определите сигнатуру метода отмены.

### <a name="visual-basic"></a>Visual Basic

||Поддерживается несколько одновременных операций|Только одна операция в один момент времени|
|------|------------------------------------------------|----------------------------------|
|Одна асинхронная операция во всем классе|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|Несколько асинхронных операций в классе|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a>C\#

||Поддерживается несколько одновременных операций|Только одна операция в один момент времени|
|------|------------------------------------------------|----------------------------------|
|Одна асинхронная операция во всем классе|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|Несколько асинхронных операций в классе|`void CancelAsync(object userState);`|`void CancelAsync();`|

При определении метода `CancelAsync(object userState)` следует быть внимательным при выборе значений состояния клиента. Эти значения должны различаться не только для всех вызовов одного асинхронного метода, но и для всех вызываемых асинхронных методов объекта.

Для версии метода с одной асинхронной операцией выбрано имя _MethodName_**AsyncCancel**, чтобы его было удобнее искать в среде разработки, например в IntelliSense для Visual Studio. При этом связанные элементы группируются и отделяются от других элементов, которые не связаны с асинхронными операциями. Если в дальнейшем могут быть добавлены новые асинхронные операции, рекомендуется определить `CancelAsync`.

Не определяйте несколько методов из приведенной выше таблицы в одном и том же классе. В этом не будет никакого смысла, к тому же интерфейс класса будет загроможден лишними методами.

Эти методы обычно возвращают управление немедленно, и на самом деле операция может не быть отменена. В обработчике события _MethodName_**Completed** объект _MethodName_**CompletedEventArgs** содержит поле `Cancelled`, которое позволяет клиентам определить, была ли отменена операция.

Придерживайтесь семантики отмены, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="optionally-support-the-isbusy-property"></a>Возможная поддержка свойства IsBusy

Если ваш класс поддерживает несколько одновременных вызовов, попробуйте предоставить свойство `IsBusy`. Это позволяет разработчикам определить, выполняется ли метод _MethodName_**Async**, не перехватывая исключение из метода _MethodName_**Async**.

Придерживайтесь семантики `IsBusy`, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="optionally-provide-support-for-progress-reporting"></a>Возможная поддержка отчетов о ходе выполнения

Часто желательно, чтобы асинхронная операция сообщала о ходе своего выполнения. При использовании асинхронной модели на основе событий это можно реализовать.

- При необходимости определите событие, которое будет выдаваться асинхронной операцией и вызываться в соответствующем потоке. Объект <xref:System.ComponentModel.ProgressChangedEventArgs> содержит целочисленный индикатор хода выполнения, который может принимать значения от 0 до 100.

- Укажите следующее имя для этого события:

  - `ProgressChanged`, если в классе есть несколько асинхронных операций (или ожидается в будущих версиях);

  - _MethodName_**ProgressChanged**, если в классе есть одна асинхронная операция.

  Выбор имени события соответствует выбору имени для метода отмены, как описано в разделе "Возможная поддержка отмены".

В этом событии следует использовать сигнатуру делегата <xref:System.ComponentModel.ProgressChangedEventHandler> и класс <xref:System.ComponentModel.ProgressChangedEventArgs>. Кроме того, если есть возможность создать индикатор хода выполнения с более точной привязкой к домену (например, основанный на количестве полученных байт и общем количестве байт при операции скачивания), следует определить класс, производный от <xref:System.ComponentModel.ProgressChangedEventArgs>.

Обратите внимание, что для этого класса существует только одно событие `ProgressChanged` или _MethodName_**ProgressChanged**, независимо от количества поддерживаемых асинхронных методов. Чтобы различать изменения хода выполнения для нескольких одновременных операций, клиентам следует использовать объект `userState`, который передается в метод _MethodName_**Async**.

Возможны ситуации, при которых несколько операций поддерживают ход выполнения и каждая операция возвращает собственный индикатор хода выполнения. В этом случае одним событием `ProgressChanged` не обойтись и необходимо рассмотреть поддержку нескольких событий `ProgressChanged`. В этом случае используйте шаблон именования _MethodName_**ProgressChanged** для каждого метода _MethodName_**Async**.

Придерживайтесь семантики отчета о ходе выполнения, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="optionally-provide-support-for-returning-incremental-results"></a>Возможная поддержка возврата добавочных результатов

Иногда асинхронная операция может возвращать добавочные результаты до своего завершения. Поддержку этого сценария можно реализовать различными способами. Ниже приведены некоторые примеры.

### <a name="single-operation-class"></a>Класс с одной операцией

Если ваш класс поддерживает только одну асинхронную операцию и эта операция может возвращать добавочные результаты, выполните следующие действия.

- Расширьте тип <xref:System.ComponentModel.ProgressChangedEventArgs>, включив в него результаты с приращением, и определите событие _MethodName_**ProgressChanged** с использованием этих дополнительных данных.

- Создавайте это событие _MethodName_**ProgressChanged** при каждом появлении сведений о результатах.

Это решение применимо только к классам с одной асинхронной операцией, чтобы не возникало конфликтов с информированием о добавочных результатах "по всем операциям" в том же событии, как в случае с событием _имя_метода_**ProgressChanged**.

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Класс с несколькими операциями, предоставляющий однородные добавочные результаты

В данном случае класс поддерживает несколько асинхронных методов, каждый из которых может возвращать добавочные результаты, и эти добавочные результаты имеют одинаковый тип данных.

Используйте модель, описанную выше для классов с одной операцией, так как эта же структура <xref:System.EventArgs> подойдет для любых добавочных результатов. Определите событие `ProgressChanged` вместо события _MethodName_**ProgressChanged**, так как оно применяется к нескольким асинхронным методам.

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Класс с несколькими операциями, предоставляющий неоднородные добавочные результаты

Если ваш класс поддерживает несколько асинхронных методов, которые возвращают данные различных типов, необходимо сделать следующее.

- Разделите отправляемые отчеты о добавочных результатах и отчеты о ходе выполнения.

- Определите отдельное событие _MethodName_**ProgressChanged** с соответствующими аргументами <xref:System.EventArgs> для каждого асинхронного метода, чтобы обрабатывать добавочные сведения о результатах для этого метода.

Вызовите этот обработчик события в соответствующем потоке, как описано в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="handling-out-and-ref-parameters-in-methods"></a>Обработка выходных и ссылочных параметров в методах

Хотя на платформе .NET Framework в целом не рекомендуется использовать `out` или `ref`, это можно сделать при соблюдении некоторых правил.

Для данного синхронного метода *имя_метода*:

- параметры `out` метода *MethodName* не должны быть частью метода _MethodName_**Async**. Вместо этого они должны входить в метод _MethodName_**CompletedEventArgs** с тем же именем, что и аналогичные параметры для *MethodName* (если нет более подходящего имени).

- Параметры `ref`, передаваемые в метод *MethodName* должны входить в метод _MethodName_**Async** и _MethodName_**CompletedEventArgs** с тем же именем, что и аналогичные параметры для *MethodName* (если нет более подходящего имени).

Например, если учитывать, что:

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

Асинхронный метод и его класс <xref:System.ComponentModel.AsyncCompletedEventArgs> будут выглядеть следующим образом:

```vb
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)

Public Class MethodNameCompletedEventArgs
    Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As Integer
    End Property
    Public ReadOnly Property Arg2() As String
    End Property
    Public ReadOnly Property Arg3() As String
    End Property
End Class
```

```csharp
public void MethodNameAsync(string arg1, string arg2);

public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
{
    public int Result { get; };
    public string Arg2 { get; };
    public string Arg3 { get; };
}
```

## <a name="see-also"></a>См. также раздел

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)
- [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Определение, когда следует реализовать асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
