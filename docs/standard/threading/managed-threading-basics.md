---
title: Основы управляемых потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: bec769043ab630b37609bed12302ceff5b90474a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139231"
---
# <a name="managed-threading-basics"></a>Основы управляемых потоков

Первые пять тем этого раздела помогут вам понять, в каких случаях уместно применять управляемые потоки, и предоставят описания их основных компонентов. Сведения о классах, которые предоставляют дополнительные возможности, вы найдете в статьях [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md) и [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Остальные темы этого раздела посвящены дополнительным возможностям, включая взаимодействие управляемых потоков с операционной системой Windows.  
  
> [!NOTE]
> На платформе .NET Framework 4, библиотека параллельных задач и PLINQ предоставляют интерфейсы API для поддержки параллелизма задач и данных в многопоточных программах. Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>В этом разделе

 [Потоки и работа с потоками](../../../docs/standard/threading/threads-and-threading.md)  
 Преимущества и недостатки использования нескольких потоков, а также описание сценариев, в которых целесообразно создавать потоки или использовать пул потоков.  
  
 [Исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Описание поведения необработанных исключений в потоках для разных версий платформы .NET Framework с особым вниманием к тем ситуациям, в которых они приведут к завершению работы приложения.  
  
 [Синхронизация данных для многопоточности](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Описание стратегий синхронизации данных в классах, которые следует применять при работе с несколькими потоками.  
  
 [Основные и фоновые потоки](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Описание различий между основными и фоновыми потоками.  
  
 [Управляемые и неуправляемые потоки в Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Описание соотношений между управляемыми и неуправляемыми потоками, список управляемых эквивалентов для работы с API-интерфейсами потоков в Windows, описание взаимодействий между подразделениями COM и управляемыми потоками.  
  
 [Локальное хранилище потока: статические поля потока и области данных](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Описание механизмов хранения для отдельных потоков.  
  
## <a name="reference"></a>Справочник

 <xref:System.Threading.Thread>  
 Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описание безопасного подхода к многопоточности при работе с объектами пользовательского интерфейса.  
  
## <a name="related-sections"></a>Связанные разделы

 [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Описание управляемых классов, которые применяются для синхронизации действий в нескольких потоках.  
  
 [Рекомендации по работе с потоками](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Описание распространенных проблем с многопоточностью и стратегий для предотвращения проблем.  
  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)  
 Описание библиотеки параллельных задач и PLINQ, которые существенно упрощают создание асинхронных и многопоточных приложений .NET Framework.
