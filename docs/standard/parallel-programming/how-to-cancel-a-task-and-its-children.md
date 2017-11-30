---
title: "Практическое руководство. Отмена задачи и ее дочерних элементов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374068694a3aa9724905964717dc5e77c09fc0ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Практическое руководство. Отмена задачи и ее дочерних элементов
Этих примерах показано, как выполнять следующие задачи:  
  
1.  Создание и запуск задаче с возможностью отмены.  
  
2.  Передача токена отмены пользовательскому делегату и при необходимости экземпляру задачи.  
  
3.  Обратите внимание и ответить на запрос отмены в пользовательском делегате.  
  
4.  При необходимости Обратите внимание, в вызывающем потоке, выполнение задачи было отменено.  
  
 Вызывающий поток не завершает задачу принудительно; он только сообщает о запросе отмены. Если задача уже выполняется, именно пользовательский делегат рассмотрение запроса и реагировать соответствующим образом. При поступлении запроса отмены до запуска задачи пользовательский делегат никогда не выполняется, и объект задачи переходит в состояние Canceled.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как завершить <xref:System.Threading.Tasks.Task> и его дочерних элементов в ответ на запрос отмены. Здесь также показано, что при завершении пользовательского делегата путем создания исключения <xref:System.Threading.Tasks.TaskCanceledException> вызывающий поток может дополнительно использовать метод <xref:System.Threading.Tasks.Task.Wait%2A> или метод <xref:System.Threading.Tasks.Task.WaitAll%2A> для ожидания завершения задач. В этом случае необходимо использовать блок `try/catch` для обработки исключений в вызывающем потоке.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> Класс полностью интегрирован с моделью отмены, который основан на <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> и <xref:System.Threading.CancellationToken?displayProperty=nameWithType> типов. Дополнительные сведения см. в разделе [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md) и [отмены задачи](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [Асинхронное программирование на основе задач](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [Присоединенные и отсоединенные дочерние задачи](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
