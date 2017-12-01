---
title: "Практическое руководство. Задание режима выполнения в PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Практическое руководство. Задание режима выполнения в PLINQ
В этом примере показано, как для принудительного пропуска его эвристику по умолчанию и параллелизации запроса независимо от формы запроса PLINQ.  
  
> [!WARNING]
>  Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ предназначен для использования возможностей параллелизации. Однако не все запросы выигрывать от параллельной обработки. Например если запрос содержит отдельный пользовательский делегат, который выполняет мало работы, запрос обычно выполняется быстрее последовательно. Это потому, что нагрузка, вызванная выполнения параллелизации требуется дороже, чем ускорение работы, которая получается. Таким образом PLINQ не выполнять автоматическую параллелизацию каждого запроса. Во-первых, он проверяет в форме запроса и различные операторы, входящих в него. На основании этого анализа PLINQ в режиме выполнения по умолчанию может потребоваться выполнить некоторые или все запрос последовательно. Однако в некоторых случаях может быть известно больше о запросе, чем PLINQ способен определить на основе анализа. Например вы знаете, что делегат является весьма затратным, и что запрос будет определенно выигрыш от параллелизации. В таких случаях можно использовать <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> метод и укажите <xref:System.Linq.ParallelExecutionMode.ForceParallelism> значение для указания PLINQ всегда выполнял запрос параллельно.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте и вставьте этот код в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) и вызовите метод из `Main`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
