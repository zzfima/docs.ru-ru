---
title: "Реализация асинхронной модели, основанной на событиях | Microsoft Docs"
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
  - "асинхронная модель на основе событий"
  - "ProgressChangedEventArgs - класс"
  - "BackgroundWorker - компонент"
  - "события [платформа .NET Framework], асинхронные"
  - "асинхронная модель"
  - "AsyncOperationManager - класс"
  - "работа с потоками [платформа .NET Framework], асинхронные функции"
  - "асинхронные компоненты [платформа .NET Framework]"
  - "AsyncOperation - класс"
  - "AsyncCompletedEventArgs - класс"
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Реализация асинхронной модели, основанной на событиях
При создании класса с некоторыми операциями, которые могут привести к значительным задержкам, рассмотрите возможность предоставления асинхронных функциональных возможностей посредством реализации [Обзор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Асинхронная модель на основе событий предоставляет стандартизированный способ упаковки класса, поддерживающего асинхронные функции. Если реализуется с помощью вспомогательных классов, например <xref:System.ComponentModel.AsyncOperationManager>, класс будет правильно работать в любой модели приложения, включая [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], приложения Windows Forms и консольных приложений.  
  
 Пример реализации асинхронной модели, основанной на событиях, в разделе [как: реализация компонента, который поддерживает асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Для простых асинхронных операций может оказаться <xref:System.ComponentModel.BackgroundWorker> подходящий компонент. Дополнительные сведения о <xref:System.ComponentModel.BackgroundWorker>, в разделе [Практическое руководство: выполнение операции в фоновом режиме](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
 Ниже перечислены функции, основанной на событиях асинхронной модели, описанных в этом разделе.  
  
-   Возможности для реализации асинхронной модели, основанной на событиях  
  
-   Именование асинхронных методов  
  
-   Дополнительная поддержка отмены  
  
-   При необходимости поддерживать свойство IsBusy  
  
-   При необходимости обеспечения поддержки отчета о ходе выполнения  
  
-   Дополнительное Предоставление поддержки для возврата добавочных результатов  
  
-   Обработка Out и Ref параметрам в методах  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Возможности для реализации асинхронной модели, основанной на событиях  
 Рассмотрите возможность реализации асинхронной модели, основанной на событиях при:  
  
-   Клиенты вашего класса не требуется <xref:System.Threading.WaitHandle> и <xref:System.IAsyncResult> объектов, доступных для асинхронных операций, это означает, что опроса и <xref:System.Threading.WaitHandle.WaitAll%2A> или <xref:System.Threading.WaitHandle.WaitAny%2A> потребуется строится на клиенте.  
  
-   Вы хотите асинхронных операций, управляемых с помощью клиента с помощью модели знакомые события и делегата.  
  
 Любая операция является кандидатом на асинхронную реализацию, но следует учитывать те предполагается длительные задержки. Наиболее допустимы операции, в которых клиенты вызова метода и уведомление о завершении, без дальнейшего вмешательства. Также допустимы операции, которые работают постоянно, периодически уведомляя клиентов о ходе выполнения, добавочных результатов или изменения состояния.  
  
 Дополнительные сведения об определении времени поддержки асинхронной модели, основанной на событиях см. в разделе [решить, когда следует реализовать асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).  
  
## <a name="naming-asynchronous-methods"></a>Именование асинхронных методов  
 Для каждого синхронного метода *ИмяМетода* для которого необходимо предоставить асинхронный эквивалент:  
  
 Определение *ИмяМетода* `Async` метод:  
  
-   Возвращает `void`.  
  
-   Принимает те же параметры, что *ИмяМетода* метод.  
  
-   Принимает несколько вызовов.  
  
 Дополнительно определить *ИмяМетода* `Async` перегрузку, идентичен *ИмяМетода*`Async`, но с дополнительным параметром, зависящим от объекта вызывается `userState`. Выполните это, если следует управлять несколькими параллельными вызовами метода, в этом случае `userState` значение будут доставляться обратно все обработчики событий, чтобы различать вызовы метода. Можно также выбрать для этого просто как место для размещения пользовательского состояния для последующего извлечения.  
  
 Для каждого отдельного *ИмяМетода* `Async` сигнатуру метода:  
  
1.  Определите следующее событие в том же классе как метод:  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  Определить следующий делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs>. Они скорее всего будет определяться, вне самого класса, но в то же пространство имен.  
  
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
  
    -   Убедитесь, что *ИмяМетода* `CompletedEventArgs` предоставляет свои члены как свойства только для чтения, а не полей, как поля предотвращают привязку данных.  
  
    -   Не определяйте любые <xref:System.ComponentModel.AsyncCompletedEventArgs>-производные классы для методов, которые не дают результатов. Просто используйте экземпляр <xref:System.ComponentModel.AsyncCompletedEventArgs> сам.  
  
        > [!NOTE]
        >  Это приемлемо, когда это возможно и уместно, чтобы повторно использовать делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs> типов. В этом случае именование не будет согласовываться с именем метода, поскольку данный делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs> не будут привязаны к одному методу.  
  
## <a name="optionally-support-cancellation"></a>Дополнительная поддержка отмены  
 Если пользовательский класс будет поддерживать отмену асинхронных операций, отмену должен предоставляться клиенту, как описано ниже. Обратите внимание, что существуют две точки принятия решения, которые необходимо разрешить, прежде чем определять поддержку отмены:  
  
-   Класс, включая возможные добавления к нему, имеет только одну асинхронную операцию, поддерживающую отмену?  
  
-   Можно ли асинхронные операции, поддерживающие отмену, обрабатывать несколько операций ожидания? То есть, принимает *ИмяМетода* `Async` метод `userState` параметра, и допускающие несколько вызовов до завершения какого-либо?  
  
 Ответы на эти два вопроса в приведенной ниже таблице можно используйте для определения должен использовать метод отмены подписи.  
  
### <a name="visual-basic"></a>Visual Basic  
  
||Поддерживается несколько одновременных операций|Только одна операция единовременно|  
|------|------------------------------------------------|----------------------------------|  
|Одна асинхронная операция во всем классе|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|Несколько асинхронных операций в классе|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>C#  
  
||Поддерживается несколько одновременных операций|Только одна операция единовременно|  
|------|------------------------------------------------|----------------------------------|  
|Одна асинхронная операция во всем классе|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|Несколько асинхронных операций в классе|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 Если определить `CancelAsync(object userState)` метод, клиенты должны быть внимательны при выборе значений состояния, чтобы различать все асинхронные методы, вызванные для объекта, а не только все вызовы отдельного асинхронного метода.  
  
 Решение об именовании версии одной асинхронной операцией *ИмяМетода* `AsyncCancel` основан на возможности более быстрого обнаружения метода в среде разработки, такой как IntelliSense в Visual Studio. Это группирует связанные элементы и отличает их от других членов, которые не работают с асинхронными функциональными возможностями. Если предполагается, что могут существовать дополнительные асинхронных операций добавлены в последующих версиях, рекомендуется определить `CancelAsync`.  
  
 Не определяйте несколько методов из приведенной выше таблицы в том же классе. Не будет иметь смысла или он будет загромождать интерфейс класса с увеличением числа методов.  
  
 Эти методы обычно возвращают немедленно, и операция может или не может отменить на самом деле. В обработчике событий для *ИмяМетода* `Completed` событий, *ИмяМетода* `CompletedEventArgs` объект содержит `Cancelled` поле, которое клиенты могут использовать для определения, произошла ли Отмена.  
  
 Придерживайтесь семантике отмены, описанной в [советы и рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-support-the-isbusy-property"></a>При необходимости поддерживать свойство IsBusy  
 Если ваш класс поддерживает несколько одновременных вызовов, рассмотрите возможность предоставления `IsBusy` свойство. Это позволяет разработчикам определять ли *ИмяМетода* `Async` метод выполняется без перехвата исключения из *ИмяМетода* `Async` метод.  
  
 Соблюдать `IsBusy` семантику описано в [советы и рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>При необходимости обеспечения поддержки отчета о ходе выполнения  
 Часто желательно для отчета о состоянии асинхронной операции во время его работы. Асинхронная модель на основе событий предоставляет рекомендации для этого.  
  
-   При необходимости определите событие возникает при асинхронной операции и вызывается в соответствующем потоке. <xref:System.ComponentModel.ProgressChangedEventArgs> объект передает индикатор выполнения целочисленный, который должен быть в диапазоне от 0 до 100.  
  
-   Назовите это событие следующим образом:  
  
    -   `ProgressChanged`Если класс имеет несколько асинхронных операций (или ожидается, будет содержать несколько асинхронных операций в будущих версиях);  
  
    -   *MethodName* `ProgressChanged` класс содержит одну асинхронную операцию.  
  
     Этот выбор имен соответствует выбору, для метода отмены, как описано в разделе дополнительной поддержке отмены.  
  
 Это событие следует использовать <xref:System.ComponentModel.ProgressChangedEventHandler> сигнатуре делегата и <xref:System.ComponentModel.ProgressChangedEventArgs> класса. Кроме того, если можно предоставить более доменный индикатор хода выполнения (для экземпляра, количество прочитанных байтов и общее количество байтов в операции загрузки), то следует определить класс, производный от <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 Обратите внимание, что только один `ProgressChanged` или *ИмяМетода* `ProgressChanged` события для класса, независимо от количества поддерживаемых им асинхронных методов. Клиенты должны использовать `userState` объект, передаваемый в *ИмяМетода* `Async` методы для различения обновлений хода выполнения в нескольких одновременных операциях.  
  
 Возможны ситуации, в которых несколько операций поддерживают ход выполнения и каждая возвращает собственный индикатор хода выполнения. В этом случае одна `ProgressChanged` событий не подходит, и следует рассмотреть возможность поддержки нескольких `ProgressChanged` события. В этом случае используйте шаблон именования *ИмяМетода* `ProgressChanged` для каждого *ИмяМетода* `Async` метод.  
  
 Придерживайтесь семантике отчета о ходе выполнения описанных [советы и рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>Дополнительное Предоставление поддержки для возврата добавочных результатов  
 Иногда асинхронная операция может возвратить добавочные результаты до завершения. Существует ряд параметров, которые могут использоваться для поддержки этого сценария. Ниже приведены некоторые примеры.  
  
### <a name="single-operation-class"></a>Класс с одной операцией  
 Если ваш класс поддерживает только одну асинхронную операцию и эта операция может возвращать добавочные результаты, затем:  
  
-   Расширить <xref:System.ComponentModel.ProgressChangedEventArgs> введите для доставки данных добавочных результатов и определите *ИмяМетода* `ProgressChanged` событий с помощью этих расширенных данных.  
  
-   Вызвать это *ИмяМетода* `ProgressChanged` событие, если имеется добавочный результат для отчета.  
  
 Это решение применимо специально к классу с одной асинхронной операцией, так как нет никаких проблем с тем же событием добавочных результатов по «всем операциям», как *ИмяМетода* `ProgressChanged` событием.  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Класс несколькими операциями, предоставляющий однородные добавочные результаты  
 В этом случае ваш класс поддерживает несколько асинхронных методов, каждый из которых может возвращать добавочные результаты, а эти добавочные результаты имеют одинаковый тип данных.  
  
 Следуйте приведенной выше модели для классов с одной операцией, тем же <xref:System.EventArgs> структура будет работать для всех добавочных результатов. Определение `ProgressChanged` событий вместо *ИмяМетода* `ProgressChanged` событие, так как оно применимо к нескольким асинхронным методам.  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Класс с несколькими операциями с разнородными добавочных результатов  
 Если ваш класс поддерживает несколько асинхронных методов, каждый из которых возвращает другой тип данных, необходимо:  
  
-   Отдельные добавочных результатах и отчет о ходе выполнения.  
  
-   Определить отдельные *ИмяМетода* `ProgressChanged` событий с соответствующих <xref:System.EventArgs> для каждого асинхронного метода обрабатывать данные добавочных результатов этого метода.  
  
 Вызовите этот обработчик события в соответствующем потоке, как описано в [советы и рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>Обработка Out и Ref параметрам в методах  
 Хотя использование `out` и `ref` , как правило, не рекомендуется в .NET Framework, ниже приведены правила, если они присутствуют, выполните:  
  
 Синхронного метода *ИмяМетода*:  
  
-   `out`параметры для *ИмяМетода* не должно быть частью *ИмяМетода*`Async`. Вместо этого они должны быть частью *ИмяМетода* `CompletedEventArgs` с тем же именем, как его параметра-эквивалента в *ИмяМетода* (если не существует более подходящего имени).  
  
-   `ref`параметры для *ИмяМетода* должны отображаться как часть *ИмяМетода*`Async`и как часть *ИмяМетода* `CompletedEventArgs` с тем же именем, как его параметра-эквивалента в *ИмяМетода* (если не существует более подходящего имени).  
  
 Например если:  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 Асинхронный метод и его <xref:System.ComponentModel.AsyncCompletedEventArgs> класс будет выглядеть следующим образом:  
  
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
 [Практическое руководство: реализация компонента, который поддерживает асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Практическое руководство: выполнение операции в фоновом режиме](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Практическое руководство: реализация формы, в которой фоновая операция](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Определение, когда следует реализовать асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)   
 [Многопоточное программирование с использованием асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Советы и рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)