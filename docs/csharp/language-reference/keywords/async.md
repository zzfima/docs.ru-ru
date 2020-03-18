---
title: Справочник по C#. Модификатор async
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 92e94d6fe1c07ab5cd8f29d040401a737a1db78e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173657"
---
# <a name="async-c-reference"></a>async (справочник по C#)

Модификатор `async` позволяет указать, что метод, [лямбда-выражение](../../programming-guide/statements-expressions-operators/lambda-expressions.md) или [анонимный метод](../operators/delegate-operator.md) является асинхронным. Если этот модификатор используется в методе или выражении, они называются *асинхронными методами*. Ниже приводится пример асинхронного метода с именем `ExampleMethodAsync`:
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  

Если вы только начали заниматься асинхронным программированием или не понимаете, как в асинхронном методе используется [оператор `await`](../operators/await.md) для выполнения потенциально долгой работы без блокировки потока вызывающего объекта, ознакомьтесь с общими сведениями в статье [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md). Следующий код размещается внутри асинхронного метода и вызывает метод <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
Асинхронный метод выполняется синхронным образом до тех пор, пока не будет достигнуто первое выражение `await`, после чего метод приостанавливается, пока не будет завершена ожидаемая задача. В то же время управление возвращается в вызывающий объект метода, как показано в примере в следующем разделе.  
  
Если метод, который изменяется ключевым словом `async`, не содержит выражения или оператора `await`, метод выполняется синхронно. Компилятор выводит предупреждения обо всех асинхронных методах, не содержащих операторы `await`, поскольку такая ситуация может указывать на ошибку. См. раздел [Предупреждение компилятора (уровень 1) CS4014](../compiler-messages/cs4014.md).  
  
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
> Дополнительные сведения о задачах и коде, который выполняется во время ожидания задачи, см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../../programming-guide/concepts/async/index.md). Полный пример приложения WPF, в котором используются аналогичные элементы, см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
## <a name="return-types"></a>Типы возвращаемых данных  
Асинхронные методы могут иметь следующие типы возвращаемых значений:

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- [void](../builtin-types/void.md). Методы `async void` обычно рекомендуются для кода, отличного от обработчиков событий, поскольку вызывающие объекты не могут `await` эти методы и должны реализовать другой механизм уведомления об успешном завершении или ошибках.
- Начиная с версии 7.0 в языке C# поддерживаются любые типы с доступным методом `GetAwaiter`. Одной из таких реализаций является тип `System.Threading.Tasks.ValueTask<TResult>`. Доступ к нему осуществляется посредством пакета NuGet `System.Threading.Tasks.Extensions`.

Асинхронный метод не может объявлять параметры [in](./in-parameter-modifier.md), [ref](./ref.md) или [out](./out-parameter-modifier.md), а также иметь [ссылочное возвращаемое значение](../../programming-guide/classes-and-structs/ref-returns.md), но он может вызывать методы с такими параметрами.  
  
`Task<TResult>` указывается в качестве возвращаемого типа асинхронного метода, если оператор [return](./return.md) метода задает операнд типа `TResult`. Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении. То есть вызов метода возвращает `Task`, однако когда `Task` завершен, любое выражение `await`, которое ожидает `Task`, возвращает значение `void`.  
  
Возвращаемый тип `void` используется в основном для определения обработчиков событий, которые требуют этого возвращаемого типа. Вызывающий объект асинхронного метода, возвращающего `void`, не может ожидать его и перехватывать создаваемые методом исключения.  

Начиная с версии C# 7.0, возвращается другой тип, обычно тип значения, с методом `GetAwaiter`, что позволяет свести к минимуму операции выделения памяти в разделах кода с критическими требованиями к производительности.

Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../../programming-guide/concepts/async/async-return-types.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [await](../operators/await.md)
- [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md)
