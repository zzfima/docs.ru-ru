---
title: "How to: Use SpinLock for Low-Level Synchronization | Microsoft Docs"
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
  - "SpinLock, how to use"
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use SpinLock for Low-Level Synchronization
В следующем примере демонстрируется использование примитива <xref:System.Threading.SpinLock>.  
  
## Пример  
 В этом примере критический раздел выполняет минимальный объем работ, что подразумевает его эффективную работу с <xref:System.Threading.SpinLock>.  Увеличивая объем работы, небольшой объект повышает производительность <xref:System.Threading.SpinLock> в сравнении со стандартной блокировкой.  Однако при этом примитив SpinLock более ресурсоемкий в отличие от стандартной блокировки.  С помощью возможности профилирования с параллелизмом в средствах профилирования можно определить, какой тип блокировки обеспечивает лучшую производительность программы.  Для получения дополнительной информации см. [Визуализатор параллелизма](../Topic/Concurrency%20Visualizer.md).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 Использование примитива <xref:System.Threading.SpinLock> эффективно, если блокировка общего ресурса будет недолгой.  В таких случаях на компьютерах с многоядерными процессорами эффективным решением может стать прохождение заблокированным потоком нескольких циклов, пока блокировка не будет снята.  За счет цикличности поток не блокируется, этот процесс влияет на загрузку ЦП.  Примитив <xref:System.Threading.SpinLock> при определенных условиях остановит цикл, чтобы избежать неэффективной работы логических процессоров или инверсии приоритетов в системах с технологией Hyper\-Threading.  
  
 В этом примере используется класс <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>, для которого необходима синхронизация пользователей для многопоточного доступа.  Для приложений, предназначенных для .NET Framework версии 4, другим вариантом может стать использование объекта <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>, не требующего каких\-либо блокировок пользователей.  
  
 Обратите внимание на использование `false` \(`False` в Visual Basic\) при вызове <xref:System.Threading.SpinLock.Exit%2A>.  Это обеспечивает наилучшую производительность.  Для архитектуры IA64 задайте значение `true` \(`True`\), чтобы воспользоваться барьером памяти, который очищает буферы записи, обеспечивая таким образом доступность блокировки для завершения работы других потоков.  
  
## См. также  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)