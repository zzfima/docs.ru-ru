---
title: "Основы управляемых потоков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a>Основы управляемых потоков
Первые пять тем этого раздела поможет вам определить, когда для использования управляемых потоков и содержат описания некоторых основных средств. В классах, которые предоставляют дополнительные возможности Подробнее [возможности](../../../docs/standard/threading/threading-objects-and-features.md) и [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Остальные темы данного раздела посвящены описанию дополнительных возможностей, включая взаимодействие управляемых потоков с операционной системой Windows.  
  
> [!NOTE]
>  В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], библиотека параллельных задач и PLINQ предоставляют интерфейсы API для задачи и данных параллелизма в многопоточных программах. Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Потоки и работа с потоками](../../../docs/standard/threading/threads-and-threading.md)  
 Преимущества и недостатки использования нескольких потоков и описаны сценарии, в которых может создавать потоки или использовать потоки из пула потоков.  
  
 [Исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Описание поведения необработанного исключения в потоках для различных версий платформы .NET Framework, в частности случаев, в котором они приведут к завершению работы приложения.  
  
 [Синхронизация данных для многопоточности](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Описывает стратегии для синхронизации данных в классах, которые будут использоваться с несколькими потоками.  
  
 [Состояния управляемых потоков](../../../docs/standard/threading/managed-thread-states.md)  
 Описание состояния основных потоков и объясняется, как определить, выполняется ли поток.  
  
 [Основные и фоновые потоки](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Описание различий между потоками переднего плана и фона.  
  
 [Управляемые и неуправляемые потоки в Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Рассматривается связь между управляемыми и неуправляемыми потоками, перечислены управляемые эквиваленты для работы с потоками API-интерфейсы Windows и описывает взаимодействие подразделения COM и управляемыми потоками.  
  
 [Метод Thread.Suspend, сборка мусора и безопасные точки](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Представляет коллекцию поток приостановки и сборке мусора.  
  
 [Локальное хранилище потока: статические поля потока и области данных](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Описывает механизмы хранения потока.  
  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Описывает, как асинхронных или долго выполняющихся синхронных операций может быть отменено с помощью токена отмены.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Threading.Thread>  
 Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Предоставляет безопасный способ реализации многопоточности вместе с объектами пользовательского интерфейса.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Описывает управляемые классы, используемые для синхронизации действий нескольких потоков.  
  
 [Рекомендации по работе с потоками](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Описание распространенных проблем с многопоточность и стратегии для предотвращения проблем.  
  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)  
 Описание библиотеки параллельных задач и PLINQ, которые существенно упрощают работу по созданию асинхронных и многопотоковых приложений .NET Framework.
