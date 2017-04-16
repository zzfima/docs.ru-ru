---
title: "Managed Threading | Microsoft Docs"
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
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Managed Threading
При разработке приложения для компьютеров с одним или несколькими процессорами может потребоваться, чтобы приложение обеспечивало взаимодействие с пользователем, даже если это приложение в настоящий момент занято другими действиями.  Одним из способов, обеспечивающих взаимодействие приложения и пользователя в процессе обработки данным приложением других событий, является использование нескольких потоков выполнения.  Поскольку в этом разделе представлены основные принципы работы с потоками, внимание будет сосредоточено на принципах управляемых потоков и их использовании.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], многопоточное программирование значительно упростилось благодаря введению классов <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> и <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), новых классов параллельных коллекций в пространстве имен <xref:System.Collections.Concurrent?displayProperty=fullName> и новой модели программирования, построенной по принципу управления задачами, а не потоками.  Для получения дополнительной информации см. [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## В этом подразделе  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)  
 Обзор управляемых потоков, а также обсуждение случаев использования нескольких потоков.  
  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 Описание способов создания, запуска, приостановки, возобновления и отмены потоков.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Обсуждение уровней синхронизации, способов предотвращения зависаний и состояний гонки, а также использования однопроцессорных и многопроцессорных систем и других вопросов, связанных с потоками.  
  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)  
 Описание управляемых классов, используемых для синхронизации работы потоков, и данных объектов, взаимодействующих с разными потоками; обзор потоков из группы потоков.  
  
## Ссылка  
 <xref:System.Threading>  
 Классы, которые применяются для использования и синхронизации управляемых потоков.  
  
 <xref:System.Collections.Concurrent>  
 Классы коллекции, которые могут безопасно использоваться несколькими потоками.  
  
 <xref:System.Threading.Tasks>  
 Классы для создания и планирования задач параллельной обработки.  
  
## Связанные подразделы  
 [Домены приложений](../../../docs/framework/app-domains/application-domains.md)  
 Общие сведения о доменах приложений и их использовании в среде CLI.  
  
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)  
 Описывает преимущества и основные операции асинхронного ввода и вывода.  
  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Общие сведения об асинхронном программировании.  
  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Объяснение способа вызова методов в потоках из пула потоков с помощью встроенных функциональных возможностей делегатов.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 Описание библиотек параллельного программирования, упрощающих использование нескольких потоков в приложениях.  
  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 Описание системы параллельного выполнения запросов для использования преимуществ, предоставляемых наличием нескольких процессоров.