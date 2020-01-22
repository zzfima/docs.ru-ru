---
title: Практическое руководство. Повышение скорости выполнения небольших тел циклов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 29d7fa8200ddd972c1a5c98ea6f30a7c8ff732e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139751"
---
# <a name="how-to-speed-up-small-loop-bodies"></a>Практическое руководство. Повышение скорости выполнения небольших тел циклов
Когда цикл <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> имеет небольшое тело, он может выполняться значительно медленнее, чем эквивалентный последовательный цикл, такой как цикл [for](../../csharp/language-reference/keywords/for.md) в C# и цикл [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) в Visual Basic. Снижение производительности происходит вследствие нагрузки, связанной с секционированием данных и стоимостью вызова делегата в каждой итерации цикла. Для разрешения таких сценариев класс <xref:System.Collections.Concurrent.Partitioner> предоставляет метод <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, который позволяет выполнять последовательный цикл для тела делегата, чтобы делегат вызывался только один раз для каждой секции, а не по разу в каждой итерации. Дополнительные сведения см. в разделе [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Подход, продемонстрированный в данном примере, полезно использовать в тех случаях, когда цикл выполняет минимальный объем работ. Когда работа начнет потреблять больше вычислительных ресурсов, возможно, вы получите такую же или более высокую производительность с помощью цикла <xref:System.Threading.Tasks.Parallel.For%2A> или <xref:System.Threading.Tasks.Parallel.ForEach%2A> с разделителем по умолчанию.  
  
## <a name="see-also"></a>См. также

- [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [Итераторы (C#)](../../csharp/programming-guide/concepts/iterators.md)
- [Итераторы (Visual Basic)](../../visual-basic/programming-guide/concepts/iterators.md)
- [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
