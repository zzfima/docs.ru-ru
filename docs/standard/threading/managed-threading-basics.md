---
title: "Managed Threading Basics | Microsoft Docs"
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
  - "multiple threads"
  - "threading [.NET Framework], multiple threads"
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Managed Threading Basics
Первые пять тем этого раздела посвящены использованию управляемых потоков и содержат описания некоторых основных средств.  Сведения о классах, предоставляющих дополнительные функциональные возможности, см. в разделах [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) и [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Остальные темы данного раздела посвящены описанию дополнительных возможностей, включая взаимодействие управляемых потоков с операционной системой Windows.  
  
> [!NOTE]
>  В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] библиотека параллельных задач и PLINQ предоставляют интерфейсы API для параллельного выполнения задач и обработки данных в многопотоковых программах.  Для получения дополнительной информации см. [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## В этом подразделе  
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)  
 Преимущества и недостатки использования нескольких потоков; сценарии, в которых можно создавать потоки, используя группу потоков.  
  
 [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Описание поведения неуправляемых исключений в потоках для различных версий платформы .NET Framework, в частности ситуации, в которых эти исключения приводят к закрытию приложения.  
  
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Описание принципов работы, используемых для синхронизации данных, при работе с несколькими потоками.  
  
 [Состояния управляемых потоков](../../../docs/standard/threading/managed-thread-states.md)  
 Описание основных состояний потоков и способов определения, работает ли поток.  
  
 [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Описание различий между основными и фоновыми потоками.  
  
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Обсуждение взаимоотношений между управляемыми и неуправляемыми потоками; управляемые эквиваленты потоков для API потоков Windows; обсуждение взаимодействия управляемых потоков и апартаментов COM.  
  
 [Thread.Suspend, Garbage Collection, and Safe Points](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Описание приостановки работы потока и сборки мусора.  
  
 [Thread Local Storage: Thread\-Relative Static Fields and Data Slots](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Описание механизмов хранения потока.  
  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Описывает, как асинхронные или долго выполняемые синхронные операции могут быть отменены с помощью токена отмены.  
  
## Ссылка  
 <xref:System.Threading.Thread>  
 Справочная документация по классу **Thread**, который представляет управляемый поток, созданный неуправляемым кодом или в управляемом приложении.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описание безопасного способа реализации многопоточности вместе с объектами пользовательского интерфейса.  
  
## Связанные подразделы  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Описание управляемых классов, используемых для синхронизации действий нескольких потоков.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Описание частых проблем, связанных с многопоточностью, и стратегии по их предотвращению.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 Описание библиотеки параллельных задач и PLINQ, которые существенно облегчают работу по созданию асинхронных и многопотоковых приложений, основывающихся на платформе .NET Framework.