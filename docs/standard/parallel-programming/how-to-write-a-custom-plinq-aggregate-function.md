---
title: "Практическое руководство. Написание пользовательской агрегатной функции PLINQ"
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
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 210e9913ab3eba636ff99b7610df05655246f4eb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Практическое руководство. Написание пользовательской агрегатной функции PLINQ
Этот пример демонстрирует, как использовать метод <xref:System.Linq.ParallelEnumerable.Aggregate%2A> для применения пользовательской функции агрегирования к исходной последовательности.  
  
> [!WARNING]
>  Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. См. дополнительные сведения об [ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 Следующий пример вычисляет стандартное отклонение для последовательности целых чисел.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 В этом примере используется перегрузка стандартного оператора запроса Aggregate, уникального для PLINQ. Эта перегрузка принимает дополнительный <xref:System.Func%603?displayProperty=nameWithType> в качестве третьего входного параметра. Этот делегат объединяет результаты из всех потоков и выполняет окончательный расчет на основе объединенных результатов. В этом примере он складывает суммы из всех потоков.  
  
 Если тело лямбда-выражения состоит из одного выражения, то возвращаемое значение делегата <xref:System.Func%602?displayProperty=nameWithType> принимает значение этого выражения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
