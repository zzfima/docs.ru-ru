---
title: Практическое руководство. Отмена задачи и ее дочерних элементов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 4e0e783a4dfe3bf3a55795d7baef461369d7405a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73134207"
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Практическое руководство. Отмена задачи и ее дочерних элементов
В следующих примерах показано выполнение таких задач:  
  
1. Создание и запуск задачи с возможностью отмены.  
  
2. Передача маркера отмены пользовательскому делегату, и дополнительно — экземпляру задачи.  
  
3. Перехват запросов на отмену и реагирование на них в пользовательском делегате.  
  
4. Опциональное оповещение вызывающего потока об отмене задачи.  
  
 Вызывающий поток не может принудительно завершить задачу. Он только передает ей запрос на отмену. Если задача уже выполняется, то именно пользовательский делегат получает такой запрос и принимает соответствующие меры. Если запрос на отмену поступает до запуска задачи, пользовательский делегат даже не выполняется и объект задачи сразу переходит в состояние Canceled (Отменено).  
  
## <a name="example"></a>Пример  
 В этом примере показано, как завершить операцию <xref:System.Threading.Tasks.Task> и ее дочерние элементы в ответ на запрос отмены. Здесь также показано, что при завершении пользовательского делегата путем создания исключения <xref:System.Threading.Tasks.TaskCanceledException> вызывающий поток может дополнительно использовать метод <xref:System.Threading.Tasks.Task.Wait%2A> или метод <xref:System.Threading.Tasks.Task.WaitAll%2A> для ожидания завершения задач. В этом случае необходимо использовать блок `try/catch` для обработки исключений в вызывающем потоке.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 Класс <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> полностью интегрирован с моделью отмены, основанной на типах <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> и <xref:System.Threading.CancellationToken?displayProperty=nameWithType>. Дополнительные сведения см. в статьях [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md) и [Отмена задач](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Асинхронное программирование на основе задач](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [Присоединенные и отсоединенные дочерние задачи](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)
- [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
