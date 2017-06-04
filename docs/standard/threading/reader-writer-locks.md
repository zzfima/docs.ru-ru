---
title: "Reader-Writer Locks | Microsoft Docs"
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
  - "ReaderWriterLock class, about ReaderWriterLock class"
  - "threading [.NET Framework], ReaderWriterLock class"
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Reader-Writer Locks
Класс <xref:System.Threading.ReaderWriterLockSlim> разрешает одновременное чтение ресурса несколькими потоками, однако для записи в ресурс требуется блокировка взаимоисключающего доступа.  
  
 Класс <xref:System.Threading.ReaderWriterLockSlim> следует использовать в приложении для обеспечения синхронизации доступа к общему ресурсу между потоками.  Блокировки устанавливаются на сам объект <xref:System.Threading.ReaderWriterLockSlim>.  
  
 Как в любом механизме синхронизации, необходимо убедиться, что потоки не обходят блокировку, предоставленную <xref:System.Threading.ReaderWriterLockSlim>.  Одним способом подобного обеспечения является разработка класса, который инкапсулирует общий ресурс.  Этот класс должен предоставлять элементы, которые получают доступ к закрытому общему ресурсу и используют закрытый объект <xref:System.Threading.ReaderWriterLockSlim> для синхронизации.  См. пример, приведенный для класса <xref:System.Threading.ReaderWriterLockSlim>.  <xref:System.Threading.ReaderWriterLockSlim> достаточно эффективен для синхронизации отдельных объектов.  
  
 Приложение должно быть создано так, чтобы уменьшить время операций чтения и записи.  Длительные операции записи отрицательно сказываются на пропускной способности, поскольку блокировка записи является взаимоисключающей.  Длительные операции чтения блокируют ожидающие средства записи, и если хотя бы один поток ожидает доступа для записи, потоки, запросившие доступ для чтения, также будут заблокированы.  
  
> [!NOTE]
>  У [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] имеется две блокировки ввода\-вывода, <xref:System.Threading.ReaderWriterLockSlim> и <xref:System.Threading.ReaderWriterLock>.  Рекомендуется использовать <xref:System.Threading.ReaderWriterLockSlim> для всех новых проектов.  Класс <xref:System.Threading.ReaderWriterLockSlim> похож на класс <xref:System.Threading.ReaderWriterLock>, но использует упрощенные правила рекурсии и повышения или понижения уровня состояния блокировки.  Класс <xref:System.Threading.ReaderWriterLockSlim> позволяет избежать многих случаях потенциальной взаимоблокировки.  Кроме того, производительность <xref:System.Threading.ReaderWriterLockSlim> гораздо выше, чем производительность <xref:System.Threading.ReaderWriterLock>.  
  
## См. также  
 <xref:System.Threading.ReaderWriterLockSlim>   
 <xref:System.Threading.ReaderWriterLock>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)