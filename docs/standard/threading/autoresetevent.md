---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7602a61a4403b7ab85015876823aa41e250b23de
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863313"
---
# <a name="autoresetevent"></a>AutoResetEvent
Класс <xref:System.Threading.AutoResetEvent> предоставляет событие локального дескриптора ожидания, которое автоматически сбрасывается после создания, освободив один поток ожидания. Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle>. Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Освободив один поток в состоянии ожидания, система автоматически сбрасывает сигнальное состояние объекта <xref:System.Threading.AutoResetEvent>. Если ожидающих потоков нет, состояние объекта события остается сигнальным. <xref:System.Threading.AutoResetEvent> соответствует вызову Win32 `CreateEvent`, где указано значение `false` для аргумента `bManualReset`.  
  
 Пример использования <xref:System.Threading.AutoResetEvent> см. в разделе <xref:System.Threading.Monitor>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Monitor>  
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [Работа с потоками](../../../docs/standard/threading/index.md)  
- [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
- [Дескрипторы ожидания](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
