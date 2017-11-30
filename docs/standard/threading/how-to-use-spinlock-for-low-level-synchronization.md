---
title: "Практическое руководство. SpinLock и низкоуровневая синхронизация"
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Практическое руководство. SpinLock и низкоуровневая синхронизация
В следующем примере демонстрируется использование <xref:System.Threading.SpinLock>.  
  
## <a name="example"></a>Пример  
 В этом примере критический раздел выполняет минимальный объем работы, который вполне подходит для <xref:System.Threading.SpinLock>. Увеличивая работы небольшую повышает производительность <xref:System.Threading.SpinLock> по сравнению со стандартной блокировкой. При этом в определенный момент SpinLock может оказаться дороже стандартной блокировки. Чтобы увидеть, какой тип блокировки обеспечивает наибольшую производительность в вашей программе, воспользуйтесь функцией профилирования параллелизма. Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>может оказаться полезным при блокировку на ресурс общего доступа не будет сохраняться очень много. В подобных случаях на многоядерных компьютерах полезно запустить заблокированный поток на несколько циклов, пока блокировка не будет снята. За счет цикличности поток не блокируется, а значит ресурсы процессора активно используются. <xref:System.Threading.SpinLock>остановит цикл при определенных условиях, чтобы избежать неэффективной работы логических процессоров или инверсии приоритетов в системах с технологией Hyper-Threading.  
  
 В этом примере используется <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> класс, для которого необходима синхронизация пользователей для многопоточного доступа. В приложениях, предназначенных для .NET Framework версии 4, другой вариант — использовать <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, который не требует никаких блокировок пользователя.  
  
 Обратите внимание на использование `false` (`False` в Visual Basic) в вызове <xref:System.Threading.SpinLock.Exit%2A>. Это обеспечивает оптимальную производительность. Укажите архитектуры `true` (`True`)on IA64, чтобы воспользоваться барьером памяти, который очищает буферы записи, обеспечивая таким образом блокировку для завершения работы других потоков.  
  
## <a name="see-also"></a>См. также  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
