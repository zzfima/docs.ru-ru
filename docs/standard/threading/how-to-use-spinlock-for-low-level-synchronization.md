---
title: Практическое руководство. SpinLock и низкоуровневая синхронизация
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
ms.openlocfilehash: ad254cb6208bff868e5fc689c502b7ddcc175ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137954"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Практическое руководство. SpinLock и низкоуровневая синхронизация

В следующем примере демонстрируется использование <xref:System.Threading.SpinLock>. В этом примере критический раздел выполняет минимальный объем работы, что делает его хорошим кандидатом для <xref:System.Threading.SpinLock>. При небольшом увеличении работы производительность <xref:System.Threading.SpinLock> повышается по сравнению со стандартной блокировкой. При этом в определенный момент SpinLock может оказаться дороже стандартной блокировки. Чтобы увидеть, какой тип блокировки обеспечивает наибольшую производительность в вашей программе, воспользуйтесь функцией профилирования параллелизма. Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock> может пригодиться, если блокировка общего ресурса будет непродолжительной. В подобных случаях на многоядерных компьютерах полезно запустить заблокированный поток на несколько циклов, пока блокировка не будет снята. За счет цикличности поток не блокируется, а значит ресурсы процессора активно используются. При определенных условиях <xref:System.Threading.SpinLock> остановит цикл, чтобы избежать истощения ресурсов логических процессоров или инверсии приоритетов в системах с технологией гиперпоточности.  
  
 Этот пример использует класс <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, который требует синхронизации пользователей для многопоточного доступа. В приложениях, предназначенных для .NET Framework версии 4, есть возможность использовать <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, который не требует блокировок пользователя.  
  
 Обратите внимание на использование `false` (`False` в Visual Basic) в вызове <xref:System.Threading.SpinLock.Exit%2A?displayProperty=nameWithType>. Это обеспечивает оптимальную производительность. Укажите `true` (`True` в Visual Basic) для архитектур IA64, чтобы воспользоваться барьером памяти, который очищает буферы записи, обеспечивая таким образом блокировку для завершения работы других потоков.  
  
## <a name="see-also"></a>См. также раздел

- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)
- [Оператор lock (C#)](../../csharp/language-reference/keywords/lock-statement.md)
- [Оператор SyncLock (Visual Basic)](../../visual-basic/language-reference/statements/synclock-statement.md)
