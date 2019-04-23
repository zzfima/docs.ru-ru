---
title: Управляемая поточность
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6447cd37e4718093acfb3a0e2db053c13a027d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62015147"
---
# <a name="managed-threading"></a>Управляемая поточность
При разработке для компьютеров как с одним, так и с несколькими процессорами, необходимо, чтобы приложение обеспечивало наиболее эффективное взаимодействие с пользователем, даже если в приложении выполняются другие задачи. Использование нескольких потоков выполнения — это один из способов обеспечить в приложении возможность реагирования на действия пользователя при одновременном использовании процессора для выполнения задач между появлением или даже во время появления событий пользователя. Хотя в этом разделе приведены основные сведения о потоковом выполнении, здесь также рассматриваются принципы работы управляемых потоков и их использование.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] многопоточное программирование значительно упростилось благодаря классам <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), новым классам параллельных коллекций из пространства имен <xref:System.Collections.Concurrent?displayProperty=nameWithType> и новой модели программирования, которая вместо потоков использует концепцию задач. Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Основы управляемых потоков](../../../docs/standard/threading/managed-threading-basics.md)  
 Обзор управляемых потоков и случаев использования нескольких потоков.  
  
 [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)  
 Описание способов создания, запуска, приостановки, возобновления и отмены потоков.  
  
 [Рекомендации по работе с потоками](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Обсуждение уровней синхронизации, способов предотвращения взаимоблокировки и состояния гонки и других проблем, связанных с многопоточностью.  
  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 Описание управляемых классов, которые можно использовать для синхронизации действий потоков и данных объектов, доступных в разных потоках, а также обзор пула потоков.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Threading>  
 Содержит классы для использования и синхронизации управляемых потоков.  
  
 <xref:System.Collections.Concurrent>  
 Содержит классы коллекций, которые могут безопасно использоваться несколькими потоками.  
  
 <xref:System.Threading.Tasks>  
 Содержит классы для создания и планирования задач параллельной обработки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Домены приложений](../../../docs/framework/app-domains/application-domains.md)  
 Общие сведения о доменах приложений и их использовании в Common Language Infrastructure.  
  
 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 Описывает преимущества и основные операции асинхронного ввода и вывода.  
  
 [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))  
 Предоставляет общие рекомендации по асинхронному программированию в .NET.  
  
 [Асинхронный вызов синхронных методов](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Описание способов вызова методов в потоках пула потоков с помощью встроенных функций делегатов.  
  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)  
 Описание библиотек параллельного программирования, упрощающих использование нескольких потоков в приложениях.  
  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 Описание системы для выполнения запросов в параллельном режиме, позволяющей воспользоваться преимуществами нескольких процессоров.
