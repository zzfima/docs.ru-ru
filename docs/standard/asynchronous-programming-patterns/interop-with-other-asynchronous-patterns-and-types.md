---
title: Взаимодействие с другими асинхронными шаблонами и типами
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: 981c13c68eaf1eb0c19f95eb1b097935ea02a16d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159758"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a>Взаимодействие с другими асинхронными шаблонами и типами
В .NET Framework 1.0 появился шаблон <xref:System.IAsyncResult> , также известный как [Асинхронная модель программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)или шаблон `Begin/End` .  В .NET Framework 2.0 добавлен [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  Начиная с платформы .NET Framework 4 [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) заменяет APM и EAP, но при этом предоставляет возможность легко строить процедуры миграции с более ранних шаблонов.  
  
 В этом разделе:  
  
- [Задачи и APM](#APM) ([от APM к TAP](#ApmToTap) или [от TAP к APM](#TapToApm))  
  
- [Задачи и EAP](#EAP)  
  
- [Задачи и дескрипторы ожидания](#WaitHandles) ([от дескрипторов ожидания к TAP](#WHToTap) или [от TAP к дескрипторам ожидания](#TapToWH))  
  
<a name="APM"></a>
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a>Задачи и асинхронная модель программирования (APM)  
  
<a name="ApmToTap"></a>
### <a name="from-apm-to-tap"></a>от APM к TAP  
 Так как шаблон [Асинхронная модель программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) сильно структурирован, можно довольно легко создавать оболочки для предоставления реализации APM в качестве реализации TAP. На деле платформа .NET Framework начиная с версии .NET Framework 4 включает вспомогательные процедуры в форме перегрузок методов <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> для реализации этого преобразования.  
  
 Рассмотрим класс <xref:System.IO.Stream> и его методы <xref:System.IO.Stream.BeginRead%2A> и <xref:System.IO.Stream.EndRead%2A> , которые представляют аналог APM для синхронного метода <xref:System.IO.Stream.Read%2A> :  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 Можно использовать метод <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> для реализации оболочки TAP этой операции следующим образом.  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 Эта реализация похожа на следующее:  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
<a name="TapToApm"></a>
### <a name="from-tap-to-apm"></a>от TAP к APM  
 Если существующая инфраструктура предполагает использование шаблона APM, также может потребоваться использовать реализацию TAP там, где ожидается реализация APM.  Поскольку задачи можно создавать, а класс <xref:System.Threading.Tasks.Task> реализует интерфейс <xref:System.IAsyncResult>, для этого можно использовать простую вспомогательную функцию. В следующем коде используется расширение класса <xref:System.Threading.Tasks.Task%601> , но можно использовать почти такую же функцию для неуниверсальных задач.  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 Теперь рассмотрим случай, когда есть следующая реализация TAP:  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 При этом необходимо предоставить следующую реализацию APM:  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 В следующем примере показана одна миграция на APM:  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
<a name="EAP"></a>
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a>Задачи и асинхронная модель, основанная на событиях  
 Создание оболочки для реализации [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) сложнее создания оболочки для шаблона APM, так как шаблон EAP имеет несколько вариантов и менее структурирован, чем шаблон APM.  В качестве демонстрации следующий код создает оболочку метода `DownloadStringAsync` .  `DownloadStringAsync` принимает универсальный код ресурса (URI), создает событие `DownloadProgressChanged` во время скачивания, чтобы периодически передавать данные о ходе загрузки, а когда загрузка завершена, создает событие `DownloadStringCompleted` .  Конечным результатом является строка, содержащая оглавление страницы по указанному URI.  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
<a name="WaitHandles"></a>
## <a name="tasks-and-wait-handles"></a>Задачи и дескрипторы ожидания  
  
<a name="WHToTap"></a>
### <a name="from-wait-handles-to-tap"></a>от дескрипторов ожидания к TAP  
 Хотя дескрипторы ожидания не реализуют асинхронную модель, опытные разработчики могут использовать класс <xref:System.Threading.WaitHandle> и метод <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> для асинхронных уведомлений, когда задан дескриптор ожидания.  Можно создать оболочку метода <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> для создания альтернативы синхронного ожидания на основе задач для дескриптора ожидания:  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 С помощью этого метода можно использовать существующие реализации <xref:System.Threading.WaitHandle> в асинхронных методах.  Например, если необходимо регулировать количество асинхронных операций, которые выполняются в определенный момент времени, можно использовать семафор (объект <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> ).  Можно отрегулировать число операций, выполняемых параллельно, до *N* путем инициализации счетчика семафора равным *N*, выполняя на нем ожидание каждый раз, когда необходимо выполнить операцию, и освобождая его после завершения операции.  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 Можно также создать асинхронный семафор, который не зависит от дескрипторов ожидания и вместо этого работает только с задачами. Для этого используются методы, описанные в разделе [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md) для построения структур данных на основе <xref:System.Threading.Tasks.Task>.  
  
<a name="TapToWH"></a>
### <a name="from-tap-to-wait-handles"></a>от TAP к дескрипторам ожидания  
 Как упоминалось ранее, класс <xref:System.Threading.Tasks.Task> реализует <xref:System.IAsyncResult>, и эта реализация предоставляет свойство <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> , которое возвращает дескриптор ожидания, задаваемое при завершении <xref:System.Threading.Tasks.Task> .  Можно получить <xref:System.Threading.WaitHandle> для <xref:System.Threading.Tasks.Task> следующим образом:  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a>См. также раздел

- [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))
- [Реализация асинхронной модели на основе задач](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
