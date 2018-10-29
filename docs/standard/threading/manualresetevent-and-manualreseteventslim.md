---
title: Классы ManualResetEvent и ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85d0c5c291743c6daac549e15d479fcf332235c
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452827"
---
# <a name="manualresetevent-and-manualreseteventslim"></a>Классы ManualResetEvent и ManualResetEventSlim
Класс <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> представляет событие локального дескриптора ожидания, которое необходимо сбросить вручную после создания сигнала. Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Основную документацию по использованию и функциональным возможностям событий ручного сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Объект <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> сохраняет активный статус, пока не будет вызван его метод <xref:System.Threading.ManualResetEvent>. Пока сообщается состояние объекта, любое количество ожидающих потоков или потоков, ожидающих события после сигнала, может освободиться.
  
 В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] вы можете использовать класс <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, чтобы повысить производительность, если периоды ожидания будут очень короткими, а событие не выходит за рамки процесса. <xref:System.Threading.ManualResetEventSlim> использует цикличную работу в режиме занятости в течение короткого промежутка времени, пока ожидает перехода события в сигнальное состояние. Если периоды ожидания короткие, цикличность может стоить гораздо дешевле, чем ожидание с использованием соответствующих дескрипторов. Однако, если состояние события не изменяется в течение заданного периода времени, <xref:System.Threading.ManualResetEventSlim> применяет обычный дескриптор ожидания событий.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [AutoResetEvent](autoresetevent.md)  
- [SpinWait](spinwait.md)  
- [Классы Semaphore и SemaphoreSlim](semaphore-and-semaphoreslim.md)
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)  
- [Работа с потоками](index.md)  
