---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 71933d0be804fdf68b0dc602902343f2d88b8c82
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
Класс <xref:System.Threading.AutoResetEvent> предоставляет событие локального дескриптора ожидания, которое автоматически сбрасывается после создания, освободив один поток ожидания. Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle>. Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Освободив один поток в состоянии ожидания, система автоматически сбрасывает сигнальное состояние объекта <xref:System.Threading.AutoResetEvent>. Если ожидающих потоков нет, состояние объекта события остается сигнальным. <xref:System.Threading.AutoResetEvent> соответствует вызову Win32 `CreateEvent`, где указано значение `false` для аргумента `bManualReset`.  
  
 Пример использования <xref:System.Threading.AutoResetEvent> см. в описании [класса Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Дескрипторы ожидания](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
