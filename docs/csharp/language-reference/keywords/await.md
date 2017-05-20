---
title: "await (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- await_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 3656141c32a04e3a32a2992185f4c418c6915482
ms.contentlocale: ru-ru
ms.lasthandoff: 03/24/2017

---
# <a name="await-c-reference"></a>await (Справочник по C#)
Оператор `await` применяется к задаче в асинхронном методе для приостановки выполнения метода до завершения выполнения ожидаемой задачи. Задача представляет выполняющуюся работу.  
  
 Асинхронный метод, в котором используется `await`, должен быть изменен с помощью ключевого слова [async](../../../csharp/language-reference/keywords/async.md). Такой метод, определенный с помощью модификатора `async` и обычно содержащий одно или несколько выражений `await`, называется *асинхронным методом*.  
  
> [!NOTE]
>  Ключевые слова `async` и `await` появились в Visual Studio 2012. Общие сведения об асинхронном программировании см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md).  
  
 Задача, к которой применяется оператор `await`, обычно является возвращаемым значением из вызова метода, реализующего [асинхронную модель на основе задач](http://go.microsoft.com/fwlink/?LinkId=204847). Примерами могут служить значения типа <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.  
  
 В приведенном ниже коде метод <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> возвращает `Task\<byte[]>`, `getContentsTask`. Задача является обещанием создать фактический массив байтов после завершения задачи. Оператор `await` применяется к `getContentsTask` для приостановки выполнения в `SumPageSizesAsync` до завершения `getContentsTask`. В то же время управление возвращается вызывающему объекту `SumPageSizesAsync`. Когда `getContentsTask` завершается, результатом выражения `await` является массив байтов.  
  
```csharp  
  
private async Task SumPageSizesAsync()  
{  
    // To use the HttpClient type in desktop apps, you must include a using directive and add a   
    // reference for the System.Net.Http namespace.  
    HttpClient client = new HttpClient();  
    // . . .  
    Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);  
    byte[] urlContents = await getContentsTask;  
  
    // Equivalently, now that you see how it works, you can write the same thing in a single line.  
    //byte[] urlContents = await client.GetByteArrayAsync(url);  
    // . . .  
}  
  
```  
  
> [!IMPORTANT]
>  Полный пример см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Вы можете скачать этот пример в разделе [Примеры кода для разработчиков](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) на веб-сайте Майкрософт. Этот пример представлен в проекте AsyncWalkthrough_HttpClient.  
  
 Как показано в предыдущем примере, если `await` применяется к результату вызова метода, который возвращает `Task<TResult>`, то типом выражения `await` является TResult. Если `await` применяется к результату вызова метода, который возвращает `Task`, то типом выражения `await` является void. В следующем примере демонстрируется это различие.  
  
```csharp  
// Keyword await used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// Keyword await used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  
  
```  
  
 Выражение `await` не блокирует поток, в котором оно выполняется. Вместо этого оно приводит к тому, что компилятор регистрирует остальную часть асинхронного метода как продолжение ожидаемой задачи. Затем управление возвращается в объект, вызывающий асинхронный метод. Когда задача завершается, она вызывает свое продолжение и выполнение асинхронного метода возобновляется с того момента, где оно было остановлено.  
  
 Выражение `await` может находиться только в теле немедленно включающего метода, лямбда-выражения или анонимного метода, помеченного модификатором `async`. Термин *await* служит как ключевое слово только в этом контексте. В другом месте он интерпретируется как идентификатор. Внутри метода, лямбда-выражения или анонимного метода выражение `await` не может использоваться в теле синхронной функции, в выражении запроса, в блоке [оператора lock](../../../csharp/language-reference/keywords/lock-statement.md) или в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) контексте.  
  
## <a name="exceptions"></a>Исключения  
 Большинство асинхронных методов возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Свойства возвращаемой задачи содержат сведения о ее состоянии и журнале, например завершена ли задача, вызвал ли асинхронный метод исключение или был отменен и каков окончательный результат. Оператор `await` обращается к этим свойствам.  
  
 Если вы ожидаете возвращающий задачу асинхронный метод, который вызывает исключение, то оператор `await` повторно создает это исключение.  
  
 Если вы ожидаете возвращающий задачу асинхронный метод, который отменяется, то оператор `await` повторно создает исключение <xref:System.OperationCanceledException>.  
  
 Одна задача, которая находится в состоянии сбоя, может отражать несколько исключений. Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>. Если вы ожидаете такую задачу, операция await повторно вызывает только одно из исключений. Однако невозможно предсказать, какие исключения создаются повторно.  
  
 Примеры обработки ошибок в асинхронных методах см. в разделе [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Пример  
 В следующем примере Windows Forms демонстрируется использование `await` в асинхронном методе `WaitAsynchronouslyAsync`. Сравните поведение этого метода с поведением `WaitSynchronously`. Без применения к задаче оператора `await` метод `WaitSynchronously` выполняется синхронно, несмотря на использование модификатора `async` в его определении и вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> в его теле.  
  
```csharp  
  
private async void button1_Click(object sender, EventArgs e)  
{  
    // Call the method that runs asynchronously.  
    string result = await WaitAsynchronouslyAsync();  
  
    // Call the method that runs synchronously.  
    //string result = await WaitSynchronously ();  
  
    // Display the result.  
    textBox1.Text += result;  
}  
  
// The following method runs asynchronously. The UI thread is not  
// blocked during the delay. You can move or resize the Form1 window   
// while Task.Delay is running.  
public async Task<string> WaitAsynchronouslyAsync()  
{  
    await Task.Delay(10000);  
    return "Finished";  
}  
  
// The following method runs synchronously, despite the use of async.  
// You cannot move or resize the Form1 window while Thread.Sleep  
// is running because the UI thread is blocked.  
public async Task<string> WaitSynchronously()  
{  
    // Add a using directive for System.Threading.  
    Thread.Sleep(10000);  
    return "Finished";  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Асинхронное программирование с использованием ключевых слов Async и Await](../../../csharp/programming-guide/concepts/async/index.md)   
 [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [async](../../../csharp/language-reference/keywords/async.md)
