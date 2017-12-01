---
title: "Классы ManualResetEvent и ManualResetEventSlim"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>Классы ManualResetEvent и ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Класс представляет событие дескриптора ожидания, которое необходимо сбросить вручную после получения сигнала. Этот класс представляет специальное использование базового класса, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Основную документацию по использованию и функциональным возможностям событий ручного сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Объект <xref:System.Threading.ManualResetEvent> объект получает сигнал до его <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> вызывается метод. Пока сообщается состояние объекта, любое количество ожидающих потоков или потоков, ожидающих события после сигнала, может освободиться. <xref:System.Threading.ManualResetEvent>соответствует Win32 `CreateEvent` вызвать, указав `true` для `bManualReset` аргумент.  
  
 В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> класса для повышения производительности, когда предполагается, что времена ожидания будут очень короткими, а события не пересекает границы процессов. <xref:System.Threading.ManualResetEventSlim> использует цикличную работу в режиме занятости в течение короткого промежутка времени, пока ожидает перехода события в сигнальное состояние. Если периоды ожидания короткие, цикличность может стоить гораздо дешевле, чем ожидание с использованием соответствующих дескрипторов. Тем не менее, если событие не сигнализирует за определенный период времени, <xref:System.Threading.ManualResetEventSlim> обращается к стандартному дескриптору ожидания события.  
  
## <a name="see-also"></a>См. также  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Дескрипторы ожидания](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Классы Semaphore и SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
