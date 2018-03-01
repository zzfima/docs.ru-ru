---
title: "Практическое руководство. Реализация разделителя для статического секционирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 125bef8d43e16c120e88250a4d9d5a4ff3f63dba
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Практическое руководство. Реализация разделителя для статического секционирования
Следующий пример демонстрирует реализацию простого пользовательского разделителя для PLINQ, который выполняет статическое секционирование. Поскольку этот разделитель не поддерживает динамические секции, его нельзя использовать в <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Эта конкретная реализация разделителя может работать быстрее, чем стандартный разделитель по диапазонам для таких источников данных, в которых требуется большое время на обработку каждого элемента.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Секции в этом примере создаются, исходя из предположения о линейном увеличении времени обработки для каждого элемента. В реальных ситуациях обычно нельзя так просто спрогнозировать время обработки. Если вы используете статический разделитель для конкретного источника данных, попробуйте оптимизировать формулу разделения для этого источника, добавить логику балансировки нагрузки или использовать блочное секционирование. Примеры таких подходов представлены в статье [Практическое руководство. Реализация динамических секций](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>См. также  
 [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
