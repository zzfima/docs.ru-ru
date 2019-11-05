---
title: Приостановка и прерывание потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interrupting threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
ms.openlocfilehash: 3020694b93479d5f1d64d31c203f8fe033a10320
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129007"
---
# <a name="pausing-and-interrupting-threads"></a>Приостановка и прерывание потоков

Наиболее распространенными способами синхронизации действий потоков являются блокировка и освобождение потоков или блокировка объектов или областей кода. Подробнее об этих механизмах фиксации и блокировки см. в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Также можно организовать перевод потоков в спящий режим. Если потоки заблокированы или находятся в спящем режиме, можно использовать <xref:System.Threading.ThreadInterruptedException> для вывода потоков из состояния ожидания.  
  
## <a name="the-threadsleep-method"></a>Метод Thread.Sleep

 Вызов метода <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> приводит к немедленной блокировке текущего потока на определенное количество миллисекунд, переданное этому методу, вследствие чего остаток среза времени передается другому потоку. По истечении этого интервала времени спящий поток возобновляет выполнение.  
  
 Поток не может вызвать метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> для другого потока.  Статический метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> всегда переводит текущий поток в спящий режим.  
  
 Вызов метода <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> с аргументом <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> переводит поток в спящий режим до того момента, пока он не будет прерван другим потоком путем вызова метода <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> или завершен путем вызова метода <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  В следующем примере показаны оба метода прерывания спящего потока.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Прерывание потоков

 Ожидающий поток можно прервать, вызвав метод <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> для заблокированного потока. Это действие создает исключение <xref:System.Threading.ThreadInterruptedException>, которое выводит поток из вызова блокировки. Поток должен перехватить исключение <xref:System.Threading.ThreadInterruptedException> и выполнить соответствующие действия для продолжения работы. Если поток пропускает исключение, среда выполнения перехватывает его и останавливает поток.  
  
> [!NOTE]
> Если целевой поток не заблокирован при вызове метода <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, поток не прерывается до блокировки. Если поток никогда не блокируется, он может завершиться, не будучи прерванным.  
  
 Если ожидание является управляемым, методы <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> и <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> незамедлительно выводят поток из спящего режима. Если ожидание является неуправляемым (как, например, вызов неуправляемого кода функции Win32 [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject)), то методы <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> и <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> не могут управлять потоком, пока он не вернется в управляемый код или не вызовет управляемый код. В управляемом коде это поведение выглядит следующим образом:  
  
- <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> выводит поток из состояния ожидания, в котором он может находиться, и приводит к созданию исключения <xref:System.Threading.ThreadInterruptedException> в целевом потоке.  
  
- <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> выводит поток из состояния ожидания, в котором он может находиться, и приводит к созданию исключения <xref:System.Threading.ThreadAbortException> в этом потоке. Подробнее см. в разделе [Уничтожение потоков](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadInterruptedException>
- <xref:System.Threading.ThreadAbortException>
- [Работа с потоками](../../../docs/standard/threading/index.md)
- [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)
- [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
