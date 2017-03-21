---
title: "Асинхронные типы возвращаемых значений (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a>Асинхронные типы возвращаемых значений (Visual Basic)
Асинхронные методы имеют три возможные возвращаемые типы: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>и void.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> В Visual Basic, возвращаемый тип void записывается как [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) процедуры. Дополнительные сведения об асинхронных методах см. в разделе [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Каждый тип возвращаемого значения рассматривается в одном из следующих разделов, а полный пример, в котором используются все три типа, вы найдете в конце этого раздела.  
  
> [!NOTE]
>  Чтобы выполнить этот пример, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.  
  
##  <a name="BKMK_TaskTReturnType"></a>Возвращаемый тип Task(T)  
 <xref:System.Threading.Tasks.Task%601>Возвращаемый тип используется для асинхронного метода, который содержит [вернуть](../../../../visual-basic/language-reference/statements/return-statement.md) инструкции, в которой операнд имеет тип `TResult`.</xref:System.Threading.Tasks.Task%601>  
  
 В следующем примере `TaskOfT_MethodAsync` асинхронный метод содержит оператор return, который возвращает целое число. Таким образом, в объявлении метода необходимо указать тип возвращаемого значения `Task(Of Integer)`.  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 При `TaskOfT_MethodAsync` вызывается из в выражении await выражения await извлекает целочисленное значение (значение `leisureHours`), хранящегося в задачу, которая возвращается `TaskOfT_MethodAsync`. Дополнительные сведения о выражений ожидания см. в разделе [оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md).  
  
 Следующий код вызывает и ожидает метод `TaskOfT_MethodAsync`. Результат присваивается `result1` переменной.  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 Позволяет лучше понять, как это происходит, разделяя вызов `TaskOfT_MethodAsync` от применения `Await`, как показано в следующем коде. Вызов метода `TaskOfT_MethodAsync` , не возвращает ожидаемый немедленно `Task(Of Integer)`, как и следовало ожидать из объявления метода. Назначенные задачи `integerTask` переменной в примере. Поскольку `integerTask` — <xref:System.Threading.Tasks.Task%601>, он содержит <xref:System.Threading.Tasks.Task%601.Result>свойство типа `TResult`.</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601> В этом примере TResult представляет собой целочисленный тип. Когда `Await` применяется к `integerTask`, выражение await содержимого <xref:System.Threading.Tasks.Task%601.Result%2A>Свойства `integerTask`.</xref:System.Threading.Tasks.Task%601.Result%2A> Значение присваивается `result2` переменной.  
  
> [!WARNING]
>  <xref:System.Threading.Tasks.Task%601.Result%2A>Свойство является свойством блокировки.</xref:System.Threading.Tasks.Task%601.Result%2A> При попытке доступа к нему до завершения его задачи поток, который в текущий момент активен, блокируется до того момента, пока задача не будет завершена, а ее значение не станет доступным. В большинстве случаев следует доступа к значению с помощью `Await` вместо прямого доступа к свойству.  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 Убедитесь, что отображаемое инструкции в следующем коде значения `result1` переменной, `result2` переменной и `Result` свойства совпадают. Помните, что `Result` свойство является свойством блокировки и не должно осуществляться до задачи получено.  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <a name="BKMK_TaskReturnType"></a>Возвращаемый тип задачи  
 Асинхронные методы, не содержит оператор return или содержит оператор return, который обычно не возвращает операнд имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> Такие методы будут [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) процедуры, если они были написаны для выполнения в синхронном режиме. При использовании `Task` тип возвращаемого значения для асинхронного метода, можно использовать вызывающий метод `Await` оператор для приостановки вызывающего завершения до завершения вызванной асинхронного метода.  
  
 В следующем примере асинхронный метод `Task_MethodAsync` не содержит оператор return. Таким образом, укажите тип возвращаемого значения `Task` для метода, который позволяет `Task_MethodAsync` чтобы ожидать. Определение `Task` тип не содержит `Result` свойство для хранения возвращаемого значения.  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 `Task_MethodAsync`вызывается и ожидать при помощи оператора await вместо выражение await, аналогично вызывающий оператор для синхронной `Sub` или метода, возвращающего void. Применение `Await` оператор в этом случае не создает значение.  
  
 Следующий код вызывает и ожидает метод `Task_MethodAsync`.  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 Как в предыдущем <xref:System.Threading.Tasks.Task%601>пример, можно разделить вызов `Task_MethodAsync` от применения `Await` оператор, как показано в следующем коде.</xref:System.Threading.Tasks.Task%601> Однако следует помнить, что `Task` не имеет `Result` свойство, и что значение не создается, когда оператор await применяется к `Task`.  
  
 Следующий код отделяет вызова `Task_MethodAsync` из ожидает задачу, `Task_MethodAsync` возвращает.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
##  <a name="BKMK_VoidReturnType"></a>Возвращаемый тип void  
 Основное назначение `Sub` процедур заключается в обработчиках событий, где нет возвращаемого типа (называется типом возвращаемого значения void в других языках). Тип возврата void также можно использовать для переопределения методов, возвращающих void, или для методов, выполняющих действия, которые можно классифицировать как "запустить и забыть". Тем не менее, следует вернуть `Task` везде, где это возможно, поскольку невозможно ожидать асинхронного метода, возвращающего void. Любой вызывающий объект такого метода должен иметь возможность завершить свою работу, не дожидаясь завершения вызванного асинхронного метода, и он не должен зависеть ни от каких значений и исключений, создаваемых асинхронным методом.  
  
 Вызывающий объект асинхронного метода, возвращающего void, не может перехватывать исключения, создаваемые методом, и такие необработанные исключения могут привести к сбою приложения. Если исключение возникает в асинхронный метод, который возвращает <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>, исключение хранится в возвращенной задаче и повторно при ожидании задачи.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> Поэтому убедитесь, что любой асинхронный метод, который может вызвать исключение имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>и что вызовы метода будут ожидать.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 Дополнительные сведения о том, как перехватывать исключения в асинхронных методах см. в разделе [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Следующий код определяет асинхронный обработчик событий.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
##  <a name="BKMK_Example"></a>Полный пример  
 Следующий проект Windows Presentation Foundation (WPF) содержит примеры кода из этого раздела.  
  
 Чтобы запустить проект, выполните следующие действия.  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  В **установленные**, **шаблоны** категории, выберите **Visual Basic**, а затем выберите **Windows**. Выберите **приложение WPF** в списке типов проектов.  
  
4.  Введите `AsyncReturnTypes` как имя проекта, а затем выберите **ОК** кнопки.  
  
     Появится новый проект в **обозревателе решений**.  
  
5.  В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .  
  
     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений**, а затем выберите **откройте**.  
  
6.  В **XAML** окно MainWindow.XAML, замените код следующим кодом.  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     Появится простое окно, содержащее текстовое поле и кнопку в **разработки** окно MainWindow.xaml.  
  
7.  В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и выберите **Просмотр кода**.  
  
8.  Замените код в MainWindow.xaml.vb на приведенный далее.  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Должен появиться следующий результат.  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A>   
 [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [Async](../../../../visual-basic/language-reference/modifiers/async.md)   
 [Оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md)
