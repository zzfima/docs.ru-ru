---
title: "Практическое руководство. Реализация динамических разделов"
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
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9b08c387c9b10a9d6fa8728a7fce87a7894a37fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-implement-dynamic-partitions"></a>Практическое руководство. Реализация динамических разделов
Приведенный ниже пример демонстрирует, как реализовать пользовательский <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> с реализацией динамического секционирования, который можно использовать из некоторых перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и из PLINQ.  
  
## <a name="example"></a>Пример  
 Каждый раз, когда секция вызывает для перечислителя <xref:System.Collections.IEnumerator.MoveNext%2A>, этот перечислитель предоставляет ей один элемент списка. При работе с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> секция реализована в виде экземпляра <xref:System.Threading.Tasks.Task>. Поскольку запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизируется.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Здесь представлен пример блочного секционирования, в котором каждый блок состоит из одного элемента. Передавая несколько элементов на один запрос, вы снизите риск конфликтов блокировки и, возможно, увеличите производительность. Но использование больших блоков в определенный момент потребует дополнительной логики для балансировки нагрузки, чтобы все потоки оставались равномерно загруженными до полного завершения всех действий.  
  
## <a name="see-also"></a>См. также  
 [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Практическое руководство. Реализация разделителя для статического секционирования](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
