---
title: Асинхронный вызов синхронных методов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- asynchronous programming, delegates
- asynchronous delegates
- AsyncWaitHandle property
- callback methods
- calling synchronous methods in asynchronous manner
- WaitHandle class, code examples
- asynchronous programming, status polling
- polling asynchronous operation status
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
- waiting for asynchronous calls
- status information [.NET Framework], asynchronous operations
ms.assetid: 41972034-92ed-450a-9664-ab93fcc6f1fb
ms.openlocfilehash: 06df584f0120fbd4978e18647854a3ee844a2095
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73105128"
---
# <a name="calling-synchronous-methods-asynchronously"></a>Асинхронный вызов синхронных методов

В .NET Framework можно асинхронно вызывать любой метод. Для этого необходимо определить делегат с той же сигнатурой, что и у вызываемого метода. Среда CLR автоматически определяет для этого делегата методы `BeginInvoke` и `EndInvoke` с нужными сигнатурами.

> [!NOTE]
> Асинхронные вызовы делегатов, в частности методы `BeginInvoke` и `EndInvoke` , не поддерживаются в платформе .NET Compact Framework.

Асинхронный вызов инициируется с помощью метода `BeginInvoke` . Он имеет все те же параметры, что и метод, который нужно выполнить асинхронно, а также два дополнительных необязательных параметра. Первый параметр является делегатом <xref:System.AsyncCallback> , который ссылается на метод, вызываемый при завершении асинхронного вызова. Второй параметр — это определяемый пользователем объект, который передает данные в метод обратного вызова. Метод`BeginInvoke` выполняет возврат данных немедленно, без ожидания завершения асинхронного вызова. Метод`BeginInvoke` возвращает объект <xref:System.IAsyncResult>, который можно использовать для отслеживания выполнения асинхронного вызова.

Метод `EndInvoke` извлекает результаты асинхронного вызова. Его можно вызвать в любое время после вызова метода `BeginInvoke`. Если асинхронный вызов не завершен, метод `EndInvoke` блокирует вызывающий поток до завершения вызова. Список параметров метода `EndInvoke` включает параметры `out` и `ref` (`<Out>` `ByRef` и `ByRef` в Visual Basic) метода, который требуется вызвать асинхронно, а также значение <xref:System.IAsyncResult>, возвращаемое методом `BeginInvoke`.

> [!NOTE]
> Функция IntelliSense в Visual Studio показывает параметры `BeginInvoke` и `EndInvoke`. Если вы не используете Visual Studio или похожий инструмент либо если используется C# вместе с Studio, см. статью [Асинхронная модель программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) с описанием параметров, определенных для этих методов.

В приведенных в этой статье примерах кода демонстрируется четыре основных способа использования методов `BeginInvoke` и `EndInvoke` для выполнения асинхронных вызовов. После вызова метода `BeginInvoke` можно выполнять следующие действия.

- Выполнить какие-либо операции, а затем вызвать метод `EndInvoke` для блокировки потока, пока не будет завершен вызов.

- Получить объект <xref:System.Threading.WaitHandle> с помощью свойства <xref:System.IAsyncResult.AsyncWaitHandle%2A?displayProperty=nameWithType> , использовать метод <xref:System.Threading.WaitHandle.WaitOne%2A> для блокировки выполнения до получения сигнала <xref:System.Threading.WaitHandle> , а затем вызвать метод `EndInvoke`.

- Периодически опрашивать интерфейс <xref:System.IAsyncResult> , возвращаемый методом `BeginInvoke` , для определения момента завершения асинхронного вызова, а затем вызвать метод `EndInvoke`.

- Передать в метод `BeginInvoke`делегат для метода обратного вызова. Этот метод выполняется для потока <xref:System.Threading.ThreadPool> после завершения асинхронного вызова. Метод обратного вызова вызывает метод `EndInvoke`.

> [!IMPORTANT]
> Независимо от выбранного варианта необходимо всегда использовать для завершения асинхронного вызова метод `EndInvoke` .

## <a name="defining-the-test-method-and-asynchronous-delegate"></a>Определение метода проверки и асинхронного делегата
 В приведенных ниже примерах кода показаны различные способы асинхронного вызова одного и того же длительно выполняющегося метода `TestMethod`. Метод `TestMethod` отображает сообщение в консоли, указывающее на начало выполнения, бездействует в течение нескольких секунд и завершается. В методе`TestMethod` имеется параметр `out` для демонстрации порядка добавления таких параметров в сигнатуры методов `BeginInvoke` и `EndInvoke`. Таким же способом можно обрабатывать параметры `ref` .

 В следующем примере кода показано определение `TestMethod` и делегата `AsyncMethodCaller` , который может использоваться для асинхронного вызова `TestMethod` . Чтобы скомпилировать эти примеры кода, необходимо включить определения для метода `TestMethod` и делегата `AsyncMethodCaller` .

 [!code-cpp[AsyncDelegateExamples#1](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/TestMethod.cpp#1)]
 [!code-csharp[AsyncDelegateExamples#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/TestMethod.cs#1)]
 [!code-vb[AsyncDelegateExamples#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/TestMethod.vb#1)]

## <a name="waiting-for-an-asynchronous-call-with-endinvoke"></a>Ожидание асинхронного вызова с использованием EndInvoke
 Самым простым способом асинхронного вызова метода является запуск выполнения метода посредством вызова метода `BeginInvoke` делегата, выполнения каких-либо действий в основном потоке и последующего вызова метода `EndInvoke` . Метод`EndInvoke` может блокировать вызывающий поток, поскольку он не возвращает значение до завершения асинхронного вызова. Этот подход хорошо использовать с файловыми и сетевыми операциями.

> [!IMPORTANT]
> Поскольку метод `EndInvoke` может заблокировать поток, его ни в коем случае нельзя вызывать из потоков, обслуживающих пользовательский интерфейс.

 [!code-cpp[AsyncDelegateExamples#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/EndInvoke.cpp#2)]
 [!code-csharp[AsyncDelegateExamples#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/EndInvoke.cs#2)]
 [!code-vb[AsyncDelegateExamples#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/EndInvoke.vb#2)]

## <a name="waiting-for-an-asynchronous-call-with-waithandle"></a>Ожидание асинхронного вызова с использованием WaitHandle
 Объект <xref:System.Threading.WaitHandle> можно получить с помощью свойства <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult> , возвращаемого методом `BeginInvoke`. Объект <xref:System.Threading.WaitHandle> получает сигнал после завершения асинхронного вызова; его можно дождаться путем вызова метода <xref:System.Threading.WaitHandle.WaitOne%2A> .

 При использовании объекта <xref:System.Threading.WaitHandle>можно выполнять дополнительные операции до или после завершения асинхронного вызова, но до вызова метода `EndInvoke` для получения результатов.

> [!NOTE]
> При вызове метода `EndInvoke`дескриптор ожидания не закрывается автоматически. Если удалить все ссылки на дескриптор ожидания, системные ресурсы будут освобождены при удалении дескриптора ожидания сборщиком мусора. Чтобы освободить системные ресурсы сразу после завершения использования дескриптора ожидания, удалите его, вызвав метод <xref:System.Threading.WaitHandle.Close%2A?displayProperty=nameWithType> . При явном удалении ненужных объектов сборщик мусора работает более эффективно.

 [!code-cpp[AsyncDelegateExamples#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/waithandle.cpp#3)]
 [!code-csharp[AsyncDelegateExamples#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/waithandle.cs#3)]
 [!code-vb[AsyncDelegateExamples#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/WaitHandle.vb#3)]

## <a name="polling-for-asynchronous-call-completion"></a>Опрос завершения асинхронного вызова
 Свойство <xref:System.IAsyncResult.IsCompleted%2A> объекта <xref:System.IAsyncResult> , возвращаемого методом `BeginInvoke` , можно использовать для отслеживания завершения асинхронного вызова. Это можно делать, когда асинхронный вызов выполнен из потока, обслуживающего пользовательский интерфейс. Опрос завершения позволяет вызывающему потоку продолжить выполнение при асинхронном вызове для потока <xref:System.Threading.ThreadPool> .

 [!code-cpp[AsyncDelegateExamples#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/polling.cpp#4)]
 [!code-csharp[AsyncDelegateExamples#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/polling.cs#4)]
 [!code-vb[AsyncDelegateExamples#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/polling.vb#4)]

## <a name="executing-a-callback-method-when-an-asynchronous-call-completes"></a>Выполнение метода обратного вызова при завершении асинхронного вызова
 Если поток, инициировавший асинхронный вызов, не обязательно должен быть потоком, обрабатывающим результаты вызова, после завершения асинхронного вызова можно выполнить метод обратного вызова. Метод обратного вызова выполняется для потока <xref:System.Threading.ThreadPool> .

 Чтобы использовать метод обратного вызова, необходимо передать в метод `BeginInvoke` делегат <xref:System.AsyncCallback> , который представляет метод обратного вызова. Кроме того, можно передать объект, содержащий данные, которые будут использоваться методом обратного вызова. В методе обратного вызова параметр <xref:System.IAsyncResult>, который является единственным параметром метода обратного вызова, можно привести к типу объекта <xref:System.Runtime.Remoting.Messaging.AsyncResult> . После этого свойство <xref:System.Runtime.Remoting.Messaging.AsyncResult.AsyncDelegate%2A?displayProperty=nameWithType> можно будет использовать для получения делегата, с помощью которого инициирован вызов, чтобы можно было вызвать метод `EndInvoke`.

 Примечания к примеру.

- Параметр `threadId` метода `TestMethod` является параметром `out` (`<Out>` `ByRef` в Visual Basic), поэтому его входные значения никогда не используются методом `TestMethod`. При вызове метода `BeginInvoke` ему передается фиктивная переменная. Если параметр `threadId` является параметром `ref` (`ByRef` в Visual Basic), переменная должна быть полем уровня класса, чтобы ее можно было передавать методам `BeginInvoke` и `EndInvoke`.

- Данные о состоянии передаются методу `BeginInvoke` в виде строки форматирования, используемой методом обратного вызова для форматирования выходного сообщения. Поскольку данные о состоянии передаются в виде типа <xref:System.Object>, перед использованием их необходимо привести к нужному типу.

- Обратный вызов выполняется в потоке <xref:System.Threading.ThreadPool> . Потоки<xref:System.Threading.ThreadPool> — это фоновые потоки, которые не смогут обеспечить работоспособность приложения при завершении основного потока, поэтому основной поток в приведенном примере должен дождаться завершения обратного вызова.

 [!code-cpp[AsyncDelegateExamples#5](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/callback.cpp#5)]
 [!code-csharp[AsyncDelegateExamples#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/callback.cs#5)]
 [!code-vb[AsyncDelegateExamples#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/callback.vb#5)]

## <a name="see-also"></a>См. также

- <xref:System.Delegate>
- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
