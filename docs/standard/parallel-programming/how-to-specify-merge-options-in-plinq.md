---
title: Практическое руководство. Задание параметров слияния в PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8914d3c443971f73e6f3fa366c26567bae60dbe1
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189471"
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

- <xref:System.Linq.ParallelMergeOptions>  
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
