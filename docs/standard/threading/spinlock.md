---
title: "SpinLock | Microsoft Docs"
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
  - "synchronization primitives, SpinLock"
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# SpinLock
Структура <xref:System.Threading.SpinLock> представляет собой низкоуровневый взаимоисключающий примитив синхронизации, который выполняет цикл в ожидании получения блокировки.  На многоядерных компьютерах в случае, когда при небольшой загрузке процессора предполагается, что период ожидания будет недолгим, <xref:System.Threading.SpinLock> может оказаться значительно эффективнее в сравнении с иными разновидностями блокировок.  Однако рекомендуется использовать <xref:System.Threading.SpinLock>, только если результаты профилирования показывают, что метод <xref:System.Threading.Monitor?displayProperty=fullName> или методы <xref:System.Threading.Interlocked> значительно снижают быстродействие программы.  
  
 <xref:System.Threading.SpinLock> способен получить временной интервал в потоке, даже если еще не получал блокировки.  Такая функциональность предусмотрена для предотвращения инверсии приоритетов потоков и для обеспечения работоспособности сборщика мусора.  При использовании <xref:System.Threading.SpinLock> время удержания потоком блокировки должно быть минимальным; ни один поток не должен блокировать, пока удерживает блокировку.  
  
 Поскольку SpinLock является типом значения, в случае, когда стоит задача, чтобы оба экземпляра ссылались на одну и ту же блокировку, его необходимо передавать по ссылке явным образом.  
  
 Дополнительные сведения об использовании этого типа см. в разделе <xref:System.Threading.SpinLock?displayProperty=fullName>.  Пример см. в разделе [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock> допускает использование режима *отслеживания* *потока*, который можно использовать на этапе разработки для отслеживания потока, который удерживает блокировку в течение определенного времени.  Режим отслеживания потока чрезвычайно полезен при отладке, однако в окончательной версии программы его лучше отключить, поскольку данный режим может отрицательно сказаться на производительности.  Для получения дополнительной информации см. [How to: Enable Thread\-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## См. также  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)