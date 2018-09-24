---
title: Практическое руководство. Измерение производительности запросов PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd9e3a0ead62450e87225212f4fc6ecec6ec9489
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45749113"
---
# <a name="how-to-measure-plinq-query-performance"></a>Практическое руководство. Измерение производительности запросов PLINQ
В этом примере показано, как использовать класс <xref:System.Diagnostics.Stopwatch> для измерения времени, необходимого для выполнения запроса PLINQ.  
  
## <a name="example"></a>Пример  
 В этом примере для измерения времени, необходимого для выполнения запроса, используется пустой цикл `foreach` (`For Each` в Visual Basic). На практике цикл обычно содержит дополнительные этапы обработки, увеличивающие общее время выполнения запроса. Обратите внимание, что секундомер запускается только перед началом цикла, так как именно в это время начинается выполнение запроса. Если вам требуется более точное измерение, вместо `ElapsedMilliseconds` можно использовать свойство `ElapsedTicks`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Общее время выполнения служит полезным показателем в экспериментах с реализациями запроса, но не всегда раскрывает общую картину. Более глубокое и полное представление о взаимодействии потоков запроса друг с другом и с другими запущенными процессами можно получить, используя визуализатор параллелизма. Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="see-also"></a>См. также

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
