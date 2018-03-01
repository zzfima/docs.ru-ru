---
title: "Практическое руководство. Синхронизация параллельных операций с барьером"
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
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 616229abed93c6793b392724d038d8f9160cd6ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Практическое руководство. Синхронизация параллельных операций с барьером
В следующем примере показано, как синхронизировать параллельные задачи с помощью объекта <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Пример  
 Следующая программа подсчитывает количество итераций (или этапов), необходимых для того, чтобы каждый из двух потоков одновременно нашел свое частичное решение, используя алгоритм перемешивания слов. В каждом потоке перемешиваются свои слова, а затем операция барьера после этапа сравнивает два результата и проверяет, правильно ли собрано полное предложение.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Объект <xref:System.Threading.Barrier> приостанавливает параллельное выполнение отдельных задач, пока все задачи не достигнут этого барьера. Это полезно в тех случаях, когда параллельная операция имеет четко определенные этапы, по каждому из которых требуется синхронизация между задачами. В нашем примере операция осуществляется в два этапа. На первом этапе каждая задача заполняет данными свой сегмент буфера. Каждая задача, которая завершает заполнение своего сегмента, сообщает барьеру о готовности и переходит в режим ожидания. Когда все задачи отправят барьеру сигналы, блокировка снимается и начинается второй этап. Этот барьер нужен для того, чтобы каждая задача на втором этапе получила доступ ко всем данным, созданным до этого момента. Без этого барьера первая задача, выполнившая свою работу, может начать чтение из буферов, которые еще не заполнены другими задачами. Этот подход позволяет синхронизировать любое количество этапов.  
  
## <a name="see-also"></a>См. также  
 [Структуры данных для параллельного программирования](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
