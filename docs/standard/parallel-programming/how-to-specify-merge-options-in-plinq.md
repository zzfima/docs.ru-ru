---
title: "Практическое руководство. Задание параметров слияния в PLINQ"
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
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59ffff3019f10874bd2df977b80d46e903d13613
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Практическое руководство. Задание параметров слияния в PLINQ
Этот пример демонстрирует, как указать параметры слияния, которые будут применяться ко всем последующим операторам в запросе PLINQ. Параметры слияния не обязательно указывать явным образом, но иногда это может повысить производительность. Дополнительные сведения о параметрах слияния см. в разделе [Параметры слияния в PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. См. дополнительные сведения об [ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует поведение параметров слияния в простом сценарии, в котором ресурсоемкая функция применяется к каждому элементу неупорядоченного источника.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 В случаях, если вариант <xref:System.Linq.ParallelMergeOptions.AutoBuffered> приводит к нежелательной задержке перед получением первого элемента, попробуйте вариант <xref:System.Linq.ParallelMergeOptions.NotBuffered>, чтобы получать результаты быстрее и спокойнее.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.ParallelMergeOptions>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
