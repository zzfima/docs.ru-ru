---
title: "Практическое руководство. Отмена цикла Parallel.For или Parallel.ForEach"
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
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Практическое руководство. Отмена цикла Parallel.For или Parallel.ForEach
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> И <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> методы поддерживают отмену с помощью токенов отмены. Дополнительные сведения об отмене в целом. в разделе [отмены](../../../docs/standard/threading/cancellation-in-managed-threads.md). В параллельном цикле предоставить <xref:System.Threading.CancellationToken> методу в <xref:System.Threading.Tasks.ParallelOptions> параметра и заключает параллельный вызов в блок try-catch.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как отменить вызов <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Можно применить тот же подход к <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> вызова.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Если токен, который сигнализирует отмену совпадает с маркера, который указан в <xref:System.Threading.Tasks.ParallelOptions> экземпляра, то параллельного цикла вызовет один <xref:System.OperationCanceledException> на отмену. Если некоторые другой токен отмены, цикл создаст исключение <xref:System.AggregateException> с <xref:System.OperationCanceledException> как InnerException.  
  
## <a name="see-also"></a>См. также  
 [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
