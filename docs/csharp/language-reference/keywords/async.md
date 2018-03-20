---
title: "async (справочник по C#)"
ms.date: 05/22/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2ddbd0f7268dd5dae4095d661cf800b5b481cbbd
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="async-c-reference"></a>async (справочник по C#)
Модификатор `async` позволяет указать, что метод, [лямбда-выражение](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) или [анонимный метод](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) является асинхронным. Если этот модификатор используется в методе или выражении, они называются *асинхронными методами*. Ниже приводится пример асинхронного метода с именем `ExampleMethodAsync`: 
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  
 
Если вы только начали заниматься асинхронным программированием или не понимаете, как в асинхронном методе используется ключевое слово `await` для выполнения потенциально долгой работы без блокировки потока вызывающего объекта, ознакомьтесь с общими сведениями в статье [Асинхронное программирование с использованием ключевых слов Async и Await](../../../csharp/programming-guide/concepts/async/index.md). Следующий код размещается внутри асинхронного метода и вызывает метод <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>: 
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
Асинхронный метод выполняется синхронным образом до тех пор, пока не будет достигнуто первое выражение `await`, после чего метод приостанавливается, пока не будет завершена ожидаемая задача. В то же время управление возвращается в вызывающий объект метода, как показано в примере в следующем разделе.  
  
Если метод, который изменяется ключевым словом `async`, не содержит выражения или оператора `await`, метод выполняется синхронно. Компилятор выводит предупреждения обо всех асинхронных методах, не содержащих операторы `await`, поскольку такая ситуация может указывать на ошибку. См. раздел [Предупреждение компилятора (уровень 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).  
  
 Ключевое слово `async` — это контекстно-зависимо ключевое слово, которое является ключевым словом, когда оно изменяет метод, лямбда-выражение или анонимный метод. Во всех других контекстах он интерпретируется как идентификатор.  
  
## <a name="example"></a>Пример  
В следующем примере показана структура и поток управления между обработчиком асинхронных событий `StartButton_Click` и асинхронным методом `ExampleMethodAsync`. В результате выполнения этого асинхронного метода возвращается число символов на веб-странице. Код подходит для приложения Windows Presentation Foundation (WPF) или приложения для Магазина Windows Presentation Foundation (WPF), которые создаются в Visual Studio; см. комментарии к коду для настройки приложения.  

Этот код можно выполнить в Visual Studio как приложение Windows Presentation Foundation (WPF) или приложение Магазина Windows. Вам понадобятся элементы управления типа "Кнопка" (`StartButton`) и "Текстовое поле" (`ResultsTextBox`). Не забудьте задать имена и обработчик, чтобы получить код следующего вида:  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
Выполнение кода в виде приложения WPF:  

- Вставьте этот код в класс `MainWindow` в MainWindow.xaml.cs.  
- Добавьте ссылку на System.Net.Http.  
- Добавьте директиву `using` для System.Net.Http.  
  
Выполнение кода в виде приложения Магазина Windows:  
- Вставьте этот код в класс `MainPage` в MainPage.xaml.cs.  
- Добавьте директивы using для System.Net.Http и System.Threading.Tasks.  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
>  Дополнительные сведения о задачах и коде, который выполняется во время ожидания задачи, см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../../../csharp/programming-guide/concepts/async/index.md). Полный пример приложения WPF, в котором используются аналогичные элементы, см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
## <a name="return-types"></a>Типы возвращаемых значений  
Асинхронные методы могут иметь следующие типы возвращаемых значений:

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- [void](../../../csharp/language-reference/keywords/void.md): следует использовать только для обработчиков событий.
- Начиная с версии 7, в языке C# поддерживаются любые типы с доступным методом `GetAwaiter`. Одной из таких реализаций является тип `System.Threading.Tasks.ValueTask<TResult>`. Доступ к нему осуществляется посредством пакета NuGet `System.Threading.Tasks.Extensions`. 

Асинхронный метод не может объявлять параметры [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), а также иметь [ссылочное возвращаемое значение](../../programming-guide/classes-and-structs/ref-returns.md), но он может вызывать методы с такими параметрами.  
  
`Task<TResult>` указывается в качестве возвращаемого типа асинхронного метода, если оператор [return](../../../csharp/language-reference/keywords/return.md) метода задает операнд типа `TResult`. Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении. То есть вызов метода возвращает `Task`, однако когда `Task` завершен, любое выражение `await`, которое ожидает `Task`, возвращает значение `void`.  
  
Возвращаемый тип `void` используется в основном для определения обработчиков событий, которые требуют этого возвращаемого типа. Вызывающий объект асинхронного метода, возвращающего `void`, не может ожидать его и перехватывать создаваемые методом исключения.  

Начиная с версии C# 7 возвращается другой тип, как правило, тип значений, с методом `GetAwaiter`, что позволяет свести к минимуму объем выделяемой памяти в разделах кода с критическими требованиями к производительности. 

Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../../../csharp/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [await](../../../csharp/language-reference/keywords/await.md)  
 [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md)
