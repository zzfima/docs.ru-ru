---
title: Справочник по C#. Оператор await
ms.custom: seodec18
ms.date: 05/22/2017
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 2f6fb9fb8c29013165298c186ec072aa1e750ab9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602304"
---
# <a name="await-c-reference"></a>await (Справочник по C#)
Оператор `await` применяется к задаче в асинхронном методе для вставки точки приостановки выполнения метода до завершения выполнения ожидаемой задачи. Задача представляет выполняющуюся работу.  
  
Оператор `await` можно использовать только в асинхронном методе, измененном с использованием ключевого слова [async](./async.md). Такой метод, определенный с помощью модификатора `async` и обычно содержащий одно или несколько выражений `await`, называется *асинхронным методом*.  
  
> [!NOTE]
> Ключевые слова `async` и `await` появились в версии C# 5. Общие сведения об асинхронном программировании см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md).  
  
Задача, к которой применяется оператор `await`, обычно является возвращаемым значением из вызова метода, реализующего [асинхронную модель на основе задач](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md). К ним относятся методы, возвращающие объекты <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> и <xref:System.Threading.Tasks.ValueTask%601>.  

В следующем примере метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> возвращает `Task<byte[]>`. Задача является обещанием создать фактический массив байтов после завершения задачи. Оператор `await` приостанавливает выполнение до тех пор, пока не завершится работа метода <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>. В то же время управление возвращается вызывающему объекту `GetPageSizeAsync`. После завершения выполнения задачи выражение `await` вычисляется как массив байтов.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]  

> [!IMPORTANT]
> Полный пример см. в [руководстве по получению доступа к Интернету с помощью модификатора Async и оператора Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Вы можете скачать этот пример в разделе [Примеры кода для разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) на веб-сайте Майкрософт. Этот пример представлен в проекте AsyncWalkthrough_HttpClient.  
  
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
  
Выражение `await` может находиться только в теле включающего метода, лямбда-выражения или анонимного метода, помеченного модификатором `async`. Термин *await* служит как ключевое слово только в этом контексте. В другом месте он интерпретируется как идентификатор. Внутри метода, лямбда-выражения или анонимного метода выражение `await` не может использоваться в теле синхронной функции, в выражении запроса, в блоке [оператора lock](./lock-statement.md) или в [небезопасном](./unsafe.md) контексте.  
  
## <a name="exceptions"></a>Исключения  
Большинство асинхронных методов возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Свойства возвращаемой задачи содержат сведения о ее состоянии и журнале, например завершена ли задача, вызвал ли асинхронный метод исключение или был отменен и каков окончательный результат. Оператор `await` обращается к этим свойствам путем вызова методов для объекта, возвращенного методом `GetAwaiter`.  
  
Если вы ожидаете возвращающий задачу асинхронный метод, который вызывает исключение, то оператор `await` повторно создает это исключение.  
  
Если вы ожидаете возвращающий задачу асинхронный метод, который отменяется, то оператор `await` повторно создает исключение <xref:System.OperationCanceledException>.  
  
Одна задача, которая находится в состоянии сбоя, может отражать несколько исключений. Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Если вы ожидаете такую задачу, операция await повторно вызывает только одно из исключений. Однако невозможно предсказать, какие исключения создаются повторно.  
  
Примеры обработки ошибок в асинхронных методах см. в разделе [try-catch](./try-catch.md).  
  
## <a name="example"></a>Пример  
В следующем примере возвращается общее число символов на страницах, URL-адреса которых были переданы в качестве аргументов командной строки. В этом примере вызывается метод `GetPageLengthsAsync`, помеченный с использованием ключевого слова `async`. В свою очередь, метод `GetPageLengthsAsync` использует ключевое слово `await` для ожидания вызовов метода <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=nameWithType>.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]  

В предыдущем примере используется C# 7.1 с поддержкой [ метода `async` `Main`](../../programming-guide/main-and-command-args/index.md). Так как более ранние версии C# не поддерживают точки входа приложения, которые возвращают <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>, нельзя применить модификатор `async` к методу `Main` и реализовать ожидание вызова метода `GetPageLengthsAsync`. В этом случае вы можете извлечь значение свойства <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>, чтобы обеспечить ожидание методом `Main` завершения асинхронной операции. Для задач, которые не возвращают значение, можно вызвать метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. Ознакомьтесь со сведениями о том, [как выбрать версию языка C#](../configure-language-version.md).

## <a name="see-also"></a>См. также

- [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md)
- [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и оператора Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [async](./async.md)
