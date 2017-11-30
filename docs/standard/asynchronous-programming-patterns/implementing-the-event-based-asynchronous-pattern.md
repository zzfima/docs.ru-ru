---
title: "Реализация асинхронной модели, основанной на событиях"
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b4df5e4df914d932c7413e9330e8663753456c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a>Реализация асинхронной модели, основанной на событиях
Если вы создаете класс и некоторые операции этого класса могут привести к значительным задержкам, подумайте о том, чтобы реализовать асинхронные функции для этого класса с помощью [асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Асинхронная модель на основе событий предоставляет стандартизированный способ упаковки класса, в котором есть асинхронные функции. Если реализуется с помощью вспомогательных классов, например <xref:System.ComponentModel.AsyncOperationManager>, класс будет правильно работать в любой модели приложения, включая [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], приложения Windows Forms и консольных приложений.  
  
 Пример реализации асинхронной модели на основе событий см. в разделе [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Для простых асинхронных операций, возможно, вам <xref:System.ComponentModel.BackgroundWorker> подходящий компонент. Дополнительные сведения о <xref:System.ComponentModel.BackgroundWorker>, в разделе [как: выполнение операции в фоновом режиме](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
 Ниже перечислены функции асинхронной модели на основе событий, описанные в этом разделе.  
  
-   Возможности для реализации асинхронной модели на основе событий  
  
-   Именование асинхронных методов  
  
-   Возможная поддержка отмены  
  
-   Возможная поддержка свойства IsBusy  
  
-   Возможная поддержка отчетов о ходе выполнения  
  
-   Возможная поддержка возврата добавочных результатов  
  
-   Обработка выходных и ссылочных параметров в методах  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Возможности для реализации асинхронной модели на основе событий  
 Подумайте о реализации асинхронной модели на основе событий при следующих условиях.  
  
-   Клиенты вашего класса не обязательно <xref:System.Threading.WaitHandle> и <xref:System.IAsyncResult> объектов, доступных для асинхронных операций, это означает, что опроса и <xref:System.Threading.WaitHandle.WaitAll%2A> или <xref:System.Threading.WaitHandle.WaitAny%2A> будет необходимо создавать с помощью клиента.  
  
-   Асинхронными операциями должен управлять клиент с использованием известной модели событий или делегатов.  
  
 Любую операцию можно реализовать асинхронно, но следует выбирать те операции, которые будут включать большие задержки. Особенно подходят те операции, при которых клиенты вызывают метод и получают оповещение о его выполнении и никакого другого вмешательства в работу метода не требуется. Также подходят операции, которые работают постоянно и периодически уведомляют клиентов о ходе выполнения, об изменении состояния или отправляют им промежуточные результаты.  
  
 Дополнительные сведения о выборе асинхронной модели на основе событий см. в разделе [Выбор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).  
  
## <a name="naming-asynchronous-methods"></a>Именование асинхронных методов  
 Для каждого синхронного метода *имя_метода*, для которого необходимо предоставить асинхронный эквивалент, выполните следующие действия.  
  
 Определите метод *имя_метода*`Async`, который:  
  
-   Возвращает `void`.  
  
-   принимает те же параметры, что и метод *имя_метода*;  
  
-   поддерживает несколько вызовов.  
  
 Также можно определить перегрузку *имя_метода*`Async`. Эта перегрузка идентична *имя_метода*`Async`, но включает дополнительный параметр `userState`, в качестве которого передается объект. Реализуйте эту перегрузку, если необходимо управлять несколькими параллельными вызовами метода. В этом случае значение `userState` будет отправляться обратно во все обработчики событий, чтобы различать вызовы метода. Такую перегрузку также можно использовать для хранения и последующего извлечения состояния пользователя.  
  
 Для каждой отдельной сигнатуры метода *имя_метода*`Async` выполните следующие действия.  
  
1.  Определите следующее событие в том же классе, в котором находится метод.  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  Определить следующий делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs>. Обычно они определяются за пределами класса, но в том же пространстве имен.  
  
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
  
    -   Убедитесь, что члены класса *имя_метода*`CompletedEventArgs` предоставляются в качестве свойств, доступных только для чтения, а не полей, так как к полям нельзя выполнить привязку данных.  
  
    -   Не определяйте любые <xref:System.ComponentModel.AsyncCompletedEventArgs>-производные классы для методов, которые не дают результатов. Просто используйте экземпляр <xref:System.ComponentModel.AsyncCompletedEventArgs> сам.  
  
        > [!NOTE]
        >  Это полностью допустимо, когда это возможно и уместно, чтобы повторно использовать делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs> типов. В этом случае именование не будет согласовываться с именем метода, так как заданный делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs> не будут привязаны к одному методу.  
  
## <a name="optionally-support-cancellation"></a>Возможная поддержка отмены  
 Если ваш класс будет поддерживать отмену асинхронных операций, возможность отмены должна быть предоставлена клиенту, как описано ниже. Перед тем как определить, будет ли реализована возможность отмены, необходимо ответить на два вопроса.  
  
-   Будет ли в вашем классе и во всех его будущих версиях всего одна асинхронная операция, которая поддерживает отмену?  
  
-   Может ли асинхронная операция с возможностью отмены поддерживать несколько ожидающих операций? То есть принимает ли метод *имя_метода*`Async` параметр `userState` и поддерживает ли он несколько вызовов, чтобы затем ожидать завершения любого из них?  
  
 С помощью ответов на эти вопросы и приведенной ниже таблицы определите сигнатуру метода отмены.  
  
### <a name="visual-basic"></a>Visual Basic  
  
||Поддерживается несколько одновременных операций|Только одна операция в один момент времени|  
|------|------------------------------------------------|----------------------------------|  
|Одна асинхронная операция во всем классе|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|Несколько асинхронных операций в классе|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>C#  
  
||Поддерживается несколько одновременных операций|Только одна операция в один момент времени|  
|------|------------------------------------------------|----------------------------------|  
|Одна асинхронная операция во всем классе|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|Несколько асинхронных операций в классе|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 При определении метода `CancelAsync(object userState)` следует быть внимательным при выборе значений состояния клиента. Эти значения должны различаться не только для всех вызовов одного асинхронного метода, но и для всех вызываемых асинхронных методов объекта.  
  
 При выборе имени для метода с одной асинхронной операцией *имя_метода*`AsyncCancel` учитывалось удобство поиска этого метода по имени в среде разработки, например в IntelliSense в Visual Studio. При этом связанные элементы группируются и отделяются от других элементов, которые не связаны с асинхронными операциями. Если в дальнейшем могут быть добавлены новые асинхронные операции, рекомендуется определить `CancelAsync`.  
  
 Не определяйте несколько методов из приведенной выше таблицы в одном и том же классе. В этом не будет никакого смысла, к тому же интерфейс класса будет загроможден лишними методами.  
  
 Эти методы обычно возвращают управление немедленно, и на самом деле операция может не быть отменена. В обработчике события *имя_метода*`Completed` объект *имя_метода*`CompletedEventArgs` содержит поле `Cancelled`, с помощью которого клиенты могут определить, была ли отменена операция.  
  
 Придерживайтесь семантики отмены, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-support-the-isbusy-property"></a>Возможная поддержка свойства IsBusy  
 Если ваш класс поддерживает несколько одновременных вызовов, попробуйте предоставить свойство `IsBusy`. Это позволяет разработчикам определить, выполняется ли метод *имя_метода*`Async`, не перехватывая исключение из метода *имя_метода*`Async`.  
  
 Придерживайтесь семантики `IsBusy`, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>Возможная поддержка отчетов о ходе выполнения  
 Часто желательно, чтобы асинхронная операция сообщала о ходе своего выполнения. При использовании асинхронной модели на основе событий это можно реализовать.  
  
-   При необходимости определите событие, которое будет выдаваться асинхронной операцией и вызываться в соответствующем потоке. <xref:System.ComponentModel.ProgressChangedEventArgs> Объект передает индикатор хода выполнения на целочисленный, которая должна быть в диапазоне от 0 до 100.  
  
-   Укажите следующее имя для этого события:  
  
    -   `ProgressChanged`, если в классе есть несколько асинхронных операций (или ожидается в будущих версиях);  
  
    -   *имя_метода* `ProgressChanged`, если в классе есть одна асинхронная операция.  
  
     Выбор имени события соответствует выбору имени для метода отмены, как описано в разделе "Возможная поддержка отмены".  
  
 Это событие следует использовать <xref:System.ComponentModel.ProgressChangedEventHandler> сигнатура делегата и <xref:System.ComponentModel.ProgressChangedEventArgs> класса. Кроме того, если индикатор выполнения более специфические для домена могут быть предоставлены (для экземпляра, количество прочитанных байтов и общее количество байтов в операции загрузки), то следует определить производный класс <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 Обратите внимание, что для класса существует только одно событие `ProgressChanged` или *имя_метода*`ProgressChanged` независимо от количества поддерживаемых им асинхронных методов. Чтобы различить изменения хода выполнения в нескольких одновременных операциях, клиенты должны использовать объект `userState`, который передается в метод *имя_метода*`Async`.  
  
 Возможны ситуации, при которых несколько операций поддерживают ход выполнения и каждая операция возвращает собственный индикатор хода выполнения. В этом случае одним событием `ProgressChanged` не обойтись и необходимо рассмотреть поддержку нескольких событий `ProgressChanged`. В этом случае используйте шаблон именования *имя_метода*`ProgressChanged` для каждого метода *имя_метода*`Async`.  
  
 Придерживайтесь семантики отчета о ходе выполнения, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>Возможная поддержка возврата добавочных результатов  
 Иногда асинхронная операция может возвращать добавочные результаты до своего завершения. Поддержку этого сценария можно реализовать различными способами. Ниже приведены некоторые примеры.  
  
### <a name="single-operation-class"></a>Класс с одной операцией  
 Если ваш класс поддерживает только одну асинхронную операцию и эта операция может возвращать добавочные результаты, выполните следующие действия.  
  
-   Расширить <xref:System.ComponentModel.ProgressChangedEventArgs> введите для переноса данных добавочных результатов и определите *имя_метода* `ProgressChanged` событий с помощью этих расширенных данных.  
  
-   Выдавайте это событие *имя_метода*`ProgressChanged` при появлении добавочного результата, который следует отобразить.  
  
 Это решение можно применять к классам с одной асинхронной операцией, так как в этом случае отсутствуют трудности с тем, что для одного и того же события возвращаются добавочные результаты для всех операций, как происходит в случае с событием *имя_метода*`ProgressChanged`.  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Класс с несколькими операциями, предоставляющий однородные добавочные результаты  
 В данном случае класс поддерживает несколько асинхронных методов, каждый из которых может возвращать добавочные результаты, и эти добавочные результаты имеют одинаковый тип данных.  
  
 Следуйте приведенной выше модели для классов с одной операцией, тем же <xref:System.EventArgs> структура будет работать для всех добавочных результатов. Определите событие `ProgressChanged` вместо события *имя_метода*`ProgressChanged`, так как оно применяется к нескольким асинхронным методам.  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Класс с несколькими операциями, предоставляющий неоднородные добавочные результаты  
 Если ваш класс поддерживает несколько асинхронных методов, которые возвращают данные различных типов, необходимо сделать следующее.  
  
-   Разделите отправляемые отчеты о добавочных результатах и отчеты о ходе выполнения.  
  
-   Определена отдельная *имя_метода* `ProgressChanged` событий с соответствующих <xref:System.EventArgs> для каждого асинхронного метода обрабатывать данные добавочных результатов этого метода.  
  
 Вызовите этот обработчик события в соответствующем потоке, как описано в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>Обработка выходных и ссылочных параметров в методах  
 Хотя на платформе .NET Framework в целом не рекомендуется использовать `out` или `ref`, это можно сделать при соблюдении некоторых правил.  
  
 Для данного синхронного метода *имя_метода*:  
  
-   параметры `out` метода *имя_метода* не должны быть частью метода *имя_метода*`Async`. Вместо этого они должны быть частью метода *имя_метода*`CompletedEventArgs` с тем же именем, что и у метода с эквивалентными параметрами *имя_метода* (при отсутствии более подходящего имени).  
  
-   Параметры `ref` метода *имя_метода* должны быть частью метода *имя_метода*`Async` и частью метода *имя_метода*`CompletedEventArgs` с тем же именем, что и у метода с эквивалентными параметрами *имя_метода* (при отсутствии более подходящего имени).  
  
 Например, если учитывать, что:  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 Асинхронный метод и его <xref:System.ComponentModel.AsyncCompletedEventArgs> класса будет выглядеть следующим образом:  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <xref:System.ComponentModel.AsyncCompletedEventArgs>  
 [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Определение, когда следует реализовать асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 [Многопоточное программирование с использованием асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
