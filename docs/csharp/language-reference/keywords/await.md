---
title: "await (Справочник по C#)"
ms.date: 05/22/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23a3299492c538963e9a5dceaadc81a44d386b19
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="await-c-reference"></a>await (Справочник по C#)
Оператор `await` применяется к задаче в асинхронном методе для вставки точки приостановки выполнения метода до завершения выполнения ожидаемой задачи. Задача представляет выполняющуюся работу.  
  
Оператор `await` можно использовать только в асинхронном методе, измененном с использованием ключевого слова [async](../../../csharp/language-reference/keywords/async.md). Такой метод, определенный с помощью модификатора `async` и обычно содержащий одно или несколько выражений `await`, называется *асинхронным методом*.  
  
> [!NOTE]
>  Ключевые слова `async` и `await` появились в версии C# 5. Общие сведения об асинхронном программировании см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md).  
  
Задача, к которой применяется оператор `await`, обычно является возвращаемым значением из вызова метода, реализующего [асинхронную модель на основе задач](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md). К ним относятся методы, возвращающие объекты <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> и `System.Threading.Tasks.ValueType<TResult>`.  

  
 В следующем примере метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> возвращает `Task<byte[]>`. Задача является обещанием создать фактический массив байтов после завершения задачи. Оператор `await` приостанавливает выполнение до тех пор, пока не завершится работа метода <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>. В то же время управление возвращается вызывающему объекту `GetPageSizeAsync`. После завершения выполнения задачи выражение `await` вычисляется как массив байтов.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]  

> [!IMPORTANT]
>  Полный пример см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Вы можете скачать этот пример в разделе [Примеры кода для разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) на веб-сайте Майкрософт. Этот пример представлен в проекте AsyncWalkthrough_HttpClient.  
  
Как показано в предыдущем примере, если `await` применяется к результату вызова метода, который возвращает `Task<TResult>`, то типом выражения `await` является `TResult`. Если `await` применяется к результату вызова метода, который возвращает `Task`, то типом выражения `await` является `void`. В следующем примере демонстрируется это различие.  
  
```csharp  
// await keyword used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// await keyword used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  

// await keyword used with a method that returns a ValueTask<TResult>.
TResult result = await AsyncMethodThatReturnsValueTaskTResult();
```  
  
Выражение `await` не блокирует поток, в котором оно выполняется. Вместо этого оно приводит к тому, что компилятор регистрирует остальную часть асинхронного метода как продолжение ожидаемой задачи. Затем управление возвращается в объект, вызывающий асинхронный метод. Когда задача завершается, она вызывает свое продолжение и выполнение асинхронного метода возобновляется с того момента, где оно было остановлено.  
  
Выражение `await` может находиться только в теле включающего метода, лямбда-выражения или анонимного метода, помеченного модификатором `async`. Термин *await* служит как ключевое слово только в этом контексте. В другом месте он интерпретируется как идентификатор. Внутри метода, лямбда-выражения или анонимного метода выражение `await` не может использоваться в теле синхронной функции, в выражении запроса, в блоке [оператора lock](../../../csharp/language-reference/keywords/lock-statement.md) или в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) контексте.  
  
## <a name="exceptions"></a>Исключения  
Большинство асинхронных методов возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Свойства возвращаемой задачи содержат сведения о ее состоянии и журнале, например завершена ли задача, вызвал ли асинхронный метод исключение или был отменен и каков окончательный результат. Оператор `await` обращается к этим свойствам путем вызова методов для объекта, возвращенного методом `GetAwaiter`.  
  
Если вы ожидаете возвращающий задачу асинхронный метод, который вызывает исключение, то оператор `await` повторно создает это исключение.  
  
Если вы ожидаете возвращающий задачу асинхронный метод, который отменяется, то оператор `await` повторно создает исключение <xref:System.OperationCanceledException>.  
  
Одна задача, которая находится в состоянии сбоя, может отражать несколько исключений. Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Если вы ожидаете такую задачу, операция await повторно вызывает только одно из исключений. Однако невозможно предсказать, какие исключения создаются повторно.  
  
Примеры обработки ошибок в асинхронных методах см. в разделе [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Пример  
В следующем примере возвращается общее число символов на страницах, URL-адреса которых были переданы в качестве аргументов командной строки. В этом примере вызывается метод `GetPageLengthsAsync`, помеченный с использованием ключевого слова `async`. В свою очередь, метод `GetPageLengthsAsync` использует ключевое слово `await` для ожидания вызовов метода <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=nameWithType>.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]  

Поскольку использование ключевых слов `async` и `await` в точках входа приложения не поддерживается, атрибут `async` нельзя применить к методу `Main`, а также нельзя реализовать ожидание вызова метода `GetPageLengthsAsync`. Чтобы реализовать ожидание методом `Main` завершения асинхронной операции, можно извлечь значение свойства <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>. Для задач, которые не возвращают значение, можно вызвать метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. 

## <a name="see-also"></a>См. также  
[Асинхронное программирование с использованием ключевых слов Async и Await](../../../csharp/programming-guide/concepts/async/index.md)   
[Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
[async](../../../csharp/language-reference/keywords/async.md)
