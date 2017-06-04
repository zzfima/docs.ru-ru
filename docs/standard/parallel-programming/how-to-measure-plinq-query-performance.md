---
title: "How to: Measure PLINQ Query Performance | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, how to measure performance"
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Measure PLINQ Query Performance
В этом примере показано, как использовать класс <xref:System.Diagnostics.Stopwatch>, чтобы измерить время, необходимое для выполнения запроса PLINQ.  
  
## Пример  
 В этом примере для измерения времени, необходимого для выполнения запроса, используется пустой цикл `foreach` \(`For Each` в Visual Basic\).  В реальном коде цикл обычно содержит шаги дополнительной обработки, которые добавляются к общему времени выполнения запроса.  Обратите внимание, что секундомер запускается непосредственно перед началом цикла, поскольку именно в это время начинается выполнение запроса.  Если требуется более точное измерение, можно использовать свойство `ElapsedTicks` вместо свойства `ElapsedMilliseconds`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Общее время выполнения является полезной метрикой при экспериментах с реализациями запроса, но оно не всегда показывает общую картину.  Чтобы получить более глубокое и подробное представление о взаимодействии потоков запроса друг с другом и с другими запущенными процессами, используйте визуализатор параллелизма.  Для получения дополнительной информации см. [Визуализатор параллелизма](../Topic/Concurrency%20Visualizer.md).  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)