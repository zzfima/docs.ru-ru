---
title: "Garbage Collection | Microsoft Docs"
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
  - "memory, garbage collection"
  - "garbage collection, automatic memory management"
  - "GC [.NET Framework]"
  - "memory, allocating"
  - "common language runtime, garbage collection"
  - "garbage collector"
  - "cleanup operations"
  - "garbage collection"
  - "memory, releasing"
  - "common language runtime, automatic memory management"
  - "automatic memory management"
  - "runtime, automatic memory management"
  - "runtime, garbage collection"
  - "garbage collection, about"
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
caps.latest.revision: 36
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 36
---
# Garbage Collection
Сборщик мусора .NET Framework управляет выделением и освобождением памяти для приложения.  При каждом создании нового объекта среда CLR выделяет память для объекта из управляемой динамически распределяемой памяти \(кучи\).  Пока в управляемой куче имеется доступное адресное пространство, среда выполнения продолжает выделять пространство для новых объектов.  Но память имеет пределы.  В конечном счете, чтобы освободить некоторое количество памяти, сборщик мусора должен выполнить процедуру очистки.  Механизм оптимизации сборщика мусора определяет наилучшее время для выполнения сбора, основываясь на произведенных выделениях памяти.  В ходе выполнения очистки сборщик мусора отыскивает в управляемой куче объекты, которые более не используются приложением, и освобождает выделенную для них память.  
  
<a name="related_topics"></a>   
## Связанные разделы  
  
|Название|Описание|  
|--------------|--------------|  
|[Fundamentals of Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md)|Описание работы сборки мусора, выделения объектов в управляемой куче и других базовых понятий.|  
|[Garbage Collection and Performance](../../../docs/standard/garbage-collection/performance.md)|Описание проверок производительности, которые можно использовать для диагностики проблем сборки мусора и производительности.|  
|[Индуцированные коллекции](../../../docs/standard/garbage-collection/induced.md)|Описание выполнения сборки мусора.|  
|[Latency Modes](../../../docs/standard/garbage-collection/latency.md)|Описание режимов, которые определяют степень вмешательства сборщика мусора.|  
|[Optimization for Shared Web Hosting](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|Описание способов оптимизации сборки мусора на серверах, совместно используемых несколькими небольшими веб\-узлами.|  
|[Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md)|Описание методов, позволяющих определить приближение и завершение полной сборки мусора.|  
|[Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|Описание способа мониторинга использования процессора и памяти доменом приложения.|  
|[Weak References](../../../docs/standard/garbage-collection/weak-references.md)|Описание функциональных возможностей, которые позволяют сборщику мусора обрабатывать объект, разрешая при этом приложению получать доступ к этому объекту.|  
  
## Справочные сведения  
 <xref:System.GC?displayProperty=fullName>  
  
 <xref:System.GCCollectionMode?displayProperty=fullName>  
  
 <xref:System.GCNotificationStatus?displayProperty=fullName>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>  
  
 <xref:System.Object.Finalize%2A?displayProperty=fullName>  
  
 <xref:System.IDisposable?displayProperty=fullName>  
  
## См. также  
 [Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)