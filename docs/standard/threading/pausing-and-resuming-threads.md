---
title: "Приостановка и возобновление потоков"
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
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a>Приостановка и возобновление потоков
Наиболее распространенными способами синхронизации действий потоков являются блокировка и освобождение потоков или блокировка объектов или областей кода. Подробнее об этих механизмах фиксации и блокировки см. в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Также можно организовать перевод потоков в спящий режим. Если потоки заблокированы или находятся в спящем режиме, можно использовать <xref:System.Threading.ThreadInterruptedException> для вывода потоков из состояния ожидания.  
  
## <a name="the-threadsleep-method"></a>Метод Thread.Sleep  
 Вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> метод приводит к немедленной блокировке количество миллисекунд или интервал времени, который передается методу текущего потока и выдает оставшуюся часть своего интервала времени в другой поток. По истечении этого интервала времени спящий поток возобновляет выполнение.  
  
 Поток не может вызвать метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> для другого потока.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>представляет статический метод, который всегда вызывает текущий поток в спящий режим.  
  
 Вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> со значением <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> вынуждает поток в спящий режим, пока будет прерван другим потоком, который вызывает <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> методом в потоке находится в спящем режиме или до его завершения путем вызова его <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> метод.  В следующем примере показаны оба метода прерывания спящего потока.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Прерывание потоков  
 Можно прервать ожидающий поток путем вызова <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> метод для заблокированного потока для вызова <xref:System.Threading.ThreadInterruptedException>, которое выводит поток из вызова блокировки. Поток должен перехватить исключение <xref:System.Threading.ThreadInterruptedException> и выполнить соответствующие действия для продолжения работы. Если поток пропускает исключение, среда выполнения перехватывает его и останавливает поток.  
  
> [!NOTE]
>  Если целевой поток не заблокирован при вызове метода <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, поток не прерывается до блокировки. Если поток никогда не блокируется, он может завершиться, не будучи прерванным.  
  
 Если ожидание является управляемым, методы <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> и <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> незамедлительно выводят поток из спящего режима. Если ожидание является неуправляемым (например, вызов Win32 неуправляемого [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) функции), ни <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> , ни <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> может занять управлять потоком до его возврата или входа в управляемый код. В управляемом коде это поведение выглядит следующим образом:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> выводит поток из состояния ожидания, в котором он может находиться, и приводит к созданию исключения <xref:System.Threading.ThreadInterruptedException> в целевом потоке.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>выводит поток из состояния ожидания, он может находиться в и вызывает <xref:System.Threading.ThreadAbortException> исключение в потоке. Подробнее см. в разделе [Уничтожение потоков](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
