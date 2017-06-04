---
title: "Pausing and Resuming Threads | Microsoft Docs"
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
  - "resuming threads"
  - "threading [.NET Framework], pausing"
  - "pausing threads"
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Pausing and Resuming Threads
Наиболее распространенными способами синхронизации действий потоков являются блокировка и освобождение потоков или блокировка объектов или областей кода.  Подробнее об этих механизмах фиксации и блокировки см. в разделе [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Также можно организовать перевод потоков в спящий режим.  Если потоки заблокированы или находятся в спящем режиме, можно использовать <xref:System.Threading.ThreadInterruptedException> для вывода потоков из состояния ожидания.  
  
## Метод Thread.Sleep  
 Вызов метода <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> приводит к немедленной блокировке текущего потока на определенное количество миллисекунд, переданное в метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>, вследствие чего остаток времени предоставляется другому потоку.  Поток не может вызвать метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> для другого потока.  
  
 Вызов метода <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> с аргументом <xref:System.Threading.Timeout.Infinite?displayProperty=fullName> переводит поток в спящий режим, в котором он находится до тех пор, пока не будет прерван другим потоком, который вызовет метод <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>, или перегрузкой <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>.  
  
## Прерывание потоков  
 Ожидающий поток можно прервать путем вызова <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> для заблокированного потока, чтобы было создано исключение <xref:System.Threading.ThreadInterruptedException>, которое выводит поток из вызова блокировки.  Поток должен перехватить исключение <xref:System.Threading.ThreadInterruptedException> и выполнить соответствующие действия для продолжения работы.  Если поток пропускает исключение, среда выполнения перехватывает его и останавливает поток.  
  
> [!NOTE]
>  Если целевой поток не заблокирован при вызове метода <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>, поток не прерывается до блокировки.  Если поток никогда не блокируется, он может завершиться, не будучи прерванным.  
  
 Если ожидание является управляемым, методы <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> и <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> незамедлительно выводят поток из спящего режима.  Если ожидание является неуправляемым \(например, при вызове функции Win32 `WaitForSingleObject` с помощью вызова неуправляемого кода\), методы <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> и <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> не могут управлять потоком до его возврата или входа в управляемый код.  В управляемом коде это поведение выглядит следующим образом:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> выводит поток из состояния ожидания, в котором он может находиться, и приводит к созданию исключения <xref:System.Threading.ThreadInterruptedException> в целевом потоке.  
  
-   Метод <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> аналогичен методу <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> за исключением того, что он создает исключение <xref:System.Threading.ThreadAbortException> в потоке.  Подробнее см. в разделе [Уничтожение потоков](../../../docs/standard/threading/destroying-threads.md).  
  
## Приостановка и возобновление \(устарело\)  
 Класс <xref:System.Threading.Thread> включает два метода, <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> и <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>, позволяющие приостановить и возобновить поток.  Однако использовать эти методы не рекомендуется.  
  
> [!IMPORTANT]
>  Начиная с .NET Framework версии 2.0 методы <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> и <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> считаются устаревшими и будут удалены в будущих выпусках.  
>   
>  Методы <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> и <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>, как правило, не используются в приложениях, и их не следует путать с механизмами синхронизации.  Так как методы <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> и <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> не учитывают взаимодействие контролируемого потока, они оказывают сильное влияние и могут вызвать серьезные ошибки в приложении, такие как взаимоблокировки \(например, если вы приостанавливаете поток, владеющий ресурсом, который необходим другому потоку\).  
  
 Для повышения производительности некоторым приложениям требуется управлять приоритетами потоков.  Для этого следует использовать свойство <xref:System.Threading.Thread.Priority%2A?displayProperty=fullName> вместо <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadInterruptedException>   
 <xref:System.Threading.ThreadAbortException>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)