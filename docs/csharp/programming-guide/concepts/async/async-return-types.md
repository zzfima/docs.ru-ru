---
title: "Асинхронные типы возвращаемых значений (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: d974e93c3c50a61889a9ed37ad5f68f7a131a538
ms.contentlocale: ru-ru
ms.lasthandoff: 03/24/2017

---
# <a name="async-return-types-c"></a>Асинхронные типы возвращаемых значений (C#)
Асинхронный метод может иметь три типа возвращаемого значения: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, и void. В Visual Basic тип возвращаемого значения void записывается как процедура [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md). Дополнительные сведения об асинхронных методах см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).  
  
 Каждый тип возвращаемого значения рассматривается в одном из следующих разделов, а полный пример, в котором используются все три типа, вы найдете в конце этого раздела.  
  
> [!NOTE]
>  Для выполнения этого примера на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.  
  
##  <a name="BKMK_TaskTReturnType"></a> Тип возвращаемого значения Task(T)  
 Тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> используется для асинхронного метода, содержащего оператор [return](../../../../csharp/language-reference/keywords/return.md) (C#), в котором операнд имеет тип `TResult`.  
  
 В следующем примере асинхронный метод `TaskOfT_MethodAsync` содержит оператор return, который возвращает целое число. Поэтому в объявлении метода должен указываться тип возвращаемого значения `Task<int>`.  
  
```csharp  
// TASK<T> EXAMPLE  
async Task<int> TaskOfT_MethodAsync()  
{  
    // The body of the method is expected to contain an awaited asynchronous  
    // call.  
    // Task.FromResult is a placeholder for actual work that returns a string.  
    var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
    // The method then can process the result in some way.  
    int leisureHours;  
    if (today.First() == 'S')  
        leisureHours = 16;  
    else  
        leisureHours = 5;  
  
    // Because the return statement specifies an operand of type int, the  
    // method must have a return type of Task<int>.  
    return leisureHours;  
}  
```  
  
 При вызове `TaskOfT_MethodAsync` из выражения await это выражение await извлекает целочисленное значение (значение `leisureHours`), хранящееся в задаче, которая возвращается `TaskOfT_MethodAsync`. Дополнительные сведения о выражениях await см. в разделе [await](../../../../csharp/language-reference/keywords/await.md).  
  
 В следующем коде вызывается и ожидается метод `TaskOfT_MethodAsync`. Результат назначается переменной `result1`.  
  
```csharp  
// Call and await the Task<T>-returning async method in the same statement.  
int result1 = await TaskOfT_MethodAsync();  
```  
  
 Чтобы лучше понять, как это происходит, отделите вызов метода `TaskOfT_MethodAsync` от применения `await`, как показано в следующем коде. Вызов метода `TaskOfT_MethodAsync`, который не ожидается немедленно, возвращает `Task<int>`, как и следовало ожидать из объявления метода. В данном примере эта задача назначается переменной `integerTask`. Поскольку `integerTask` является <xref:System.Threading.Tasks.Task%601>, он содержит свойство <xref:System.Threading.Tasks.Task%601.Result> типа `TResult`. В этом примере TResult представляет собой целочисленный тип. Когда `await` применяется к `integerTask`, выражение await вычисляет содержимое свойства <xref:System.Threading.Tasks.Task%601.Result%2A> переменной `integerTask`. Это значение присваивается переменной `result2`.  
  
> [!WARNING]
>  Свойство <xref:System.Threading.Tasks.Task%601.Result%2A> является свойством блокировки. При попытке доступа к нему до завершения его задачи поток, который в текущий момент активен, блокируется до того момента, пока задача не будет завершена, а ее значение не станет доступным. В большинстве случаев следует получать доступ к этому значению с помощью `await` вместо прямого обращения к свойству.  
  
```csharp  
// Call and await in separate statements.  
Task<int> integerTask = TaskOfT_MethodAsync();  
  
// You can do other work that does not rely on integerTask before awaiting.  
textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
int result2 = await integerTask;  
```  
  
 Операторы отображения в следующем коде проверяют, одинаковы ли значения переменной `result1`, переменной `result2` и свойства `Result`. Помните, что свойство `Result` является блокирующим свойством, и к нему не стоит обращаться до того, как его задача закончит ожидание.  
  
```csharp  
// Display the values of the result1 variable, the result2 variable, and  
// the integerTask.Result property.  
textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
```  
  
##  <a name="BKMK_TaskReturnType"></a> Тип возвращаемого значения Task  
 Асинхронные методы, не содержащие оператор return или содержащие оператор return, который не возвращает операнд, обычно имеют тип возврата <xref:System.Threading.Tasks.Task>. Это могут быть методы, возвращающие void, если они были написаны для синхронного выполнения. Если для асинхронного метода вы используете тип возвращаемого значения `Task`, вызывающий метод может использовать оператор await для приостановки выполнения вызывающего объекта до завершения вызванного асинхронного метода.  
  
 В следующем примере асинхронный метод `Task_MethodAsync` не содержит оператор return. Следовательно, вы указываете для метода тип возвращаемого значения `Task`, который позволяет ожидать `Task_MethodAsync`. Определение типа `Task` не включает свойство `Result` для хранения возвращаемого значения.  
  
```csharp  
// TASK EXAMPLE  
async Task Task_MethodAsync()  
{  
    // The body of an async method is expected to contain an awaited   
    // asynchronous call.  
    // Task.Delay is a placeholder for actual work.  
    await Task.Delay(2000);  
    // Task.Delay delays the following line by two seconds.  
    textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
    // This method has no return statement, so its return type is Task.    
}  
```  
  
 `Task_MethodAsync` вызывается и ожидается с помощью оператора await (вместо выражения await), похожего на оператор вызова для синхронного метода, возвращающего значение void. Применение оператора await в этом случае не возвращает значение.  
  
 В следующем коде вызывается и ожидается метод `Task_MethodAsync`.  
  
```csharp  
// Call and await the Task-returning async method in the same statement.  
await Task_MethodAsync();  
```  
  
 Как и в предыдущем примере <xref:System.Threading.Tasks.Task%601>, вы можете разделить вызов `Task_MethodAsync` от применения оператора await, как показывает следующий код. Однако следует помнить, что `Task` не содержит свойство `Result`, и при применении оператора await к `Task` никакое значение не создается.  
  
 В следующем коде вызов `Task_MethodAsync` отделяется от ожидания задачи, которая возвращает `Task_MethodAsync`.  
  
```csharp  
// Call and await in separate statements.  
Task simpleTask = Task_MethodAsync();  
  
// You can do other work that does not rely on simpleTask before awaiting.  
textBox1.Text += String.Format("\r\nApplication can continue working while the Task runs. . . .\r\n");  
  
await simpleTask;  
```  
  
##  <a name="BKMK_VoidReturnType"></a> Тип возвращаемого значения Void  
 В основном тип возвращаемого значения void используется в обработчиках событий, где требуется тип возвращаемого значения void. Тип возврата void также можно использовать для переопределения методов, возвращающих void, или для методов, выполняющих действия, которые можно классифицировать как "запустить и забыть". Тем не менее вы должны возвращать `Task` везде, где это возможно, поскольку нельзя ожидать асинхронный метод, возвращающий void. Любой вызывающий объект такого метода должен иметь возможность завершить свою работу, не дожидаясь завершения вызванного асинхронного метода, и он не должен зависеть ни от каких значений и исключений, создаваемых асинхронным методом.  
  
 Вызывающий объект асинхронного метода, возвращающего void, не может перехватывать исключения, создаваемые методом, и такие необработанные исключения могут привести к сбою приложения. Если исключение возникает в асинхронном методе, который возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>, исключение хранится в возвращенной задаче и повторно вызывается при ожидании задачи. Поэтому убедитесь, что любой асинхронный метод, который может вызвать исключение, имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> и что вызовы метода ожидаются.  
  
 Дополнительные сведения о перехвате исключений в асинхронных методах см. в разделе [try-catch](../../../../csharp/language-reference/keywords/try-catch.md).  
  
 Следующий код определяет асинхронный обработчик событий.  
  
```csharp  
// VOID EXAMPLE  
private async void button1_Click(object sender, RoutedEventArgs e)  
{  
    textBox1.Clear();  
  
    // Start the process and await its completion. DriverAsync is a   
    // Task-returning async method.  
    await DriverAsync();  
  
    // Say goodbye.  
    textBox1.Text += "\r\nAll done, exiting button-click event handler.";  
}  
```  
  
##  <a name="BKMK_Example"></a> Полный пример  
 Следующий проект Windows Presentation Foundation (WPF) содержит примеры кода из этого раздела.  
  
 Чтобы запустить проект, выполните следующие действия.  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  В категории **Установленные**, **Шаблоны** выберите Visual C#, а затем **Windows**. В списке типов проектов выберите **Приложение WPF**.  
  
4.  Введите `AsyncReturnTypes` в качестве имени проекта и нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
5.  В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .  
  
     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Открыть**.  
  
6.  В окне **XAML** MainWindow.xaml замените код на следующий.  
  
    ```csharp  
    <Window x:Class="AsyncReturnTypes.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     Простое окно, содержащее текстовое поле и кнопку, отобразится в окне **конструктора** для MainWindow.xaml.  
  
7.  В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.  
  
8.  Замените код в MainWindow.xaml.cs на следующий.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.Threading.Tasks;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Data;  
    using System.Windows.Documents;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    using System.Windows.Media.Imaging;  
    using System.Windows.Navigation;  
    using System.Windows.Shapes;  
  
    namespace AsyncReturnTypes  
    {  
        public partial class MainWindow : Window  
        {  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            // VOID EXAMPLE  
            private async void button1_Click(object sender, RoutedEventArgs e)  
            {  
                textBox1.Clear();  
  
                // Start the process and await its completion. DriverAsync is a   
                // Task-returning async method.  
                await DriverAsync();  
  
                // Say goodbye.  
                textBox1.Text += "\r\nAll done, exiting button-click event handler.";  
            }  
  
            async Task DriverAsync()  
            {  
                // Task<T>   
                // Call and await the Task<T>-returning async method in the same statement.  
                int result1 = await TaskOfT_MethodAsync();  
  
                // Call and await in separate statements.  
                Task<int> integerTask = TaskOfT_MethodAsync();  
  
                // You can do other work that does not rely on integerTask before awaiting.  
                textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
                int result2 = await integerTask;  
  
                // Display the values of the result1 variable, the result2 variable, and  
                // the integerTask.Result property.  
                textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
                textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
                textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
  
                // Task  
                // Call and await the Task-returning async method in the same statement.  
                await Task_MethodAsync();  
  
                // Call and await in separate statements.  
                Task simpleTask = Task_MethodAsync();  
  
                // You can do other work that does not rely on simpleTask before awaiting.  
                textBox1.Text += String.Format("\r\nApplication can continue working while the Task runs. . . .\r\n");  
  
                await simpleTask;  
            }  
  
            // TASK<T> EXAMPLE  
            async Task<int> TaskOfT_MethodAsync()  
            {  
                // The body of the method is expected to contain an awaited asynchronous  
                // call.  
                // Task.FromResult is a placeholder for actual work that returns a string.  
                var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
                // The method then can process the result in some way.  
                int leisureHours;  
                if (today.First() == 'S')  
                    leisureHours = 16;  
                else  
                    leisureHours = 5;  
  
                // Because the return statement specifies an operand of type int, the  
                // method must have a return type of Task<int>.  
                return leisureHours;  
            }  
  
            // TASK EXAMPLE  
            async Task Task_MethodAsync()  
            {  
                // The body of an async method is expected to contain an awaited   
                // asynchronous call.  
                // Task.Delay is a placeholder for actual work.  
                await Task.Delay(2000);  
                // Task.Delay delays the following line by two seconds.  
                textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
                // This method has no return statement, so its return type is Task.    
            }  
        }  
    }  
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
 <xref:System.Threading.Tasks.Task.FromResult%2A>   
 [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Поток управления в асинхронных программах (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [async](../../../../csharp/language-reference/keywords/async.md)   
 [await](../../../../csharp/language-reference/keywords/await.md)
